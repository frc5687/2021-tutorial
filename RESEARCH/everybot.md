# Robonauts Everybot

The Robonauts' Everybot, with a final budget of $1,000, is an affordable, competitive, and elegant robot intended to play the FIRST Robotics Competition challenge. Everybot can be built with nothing but basic tools and items found in either the kit of parts or purchased from your local hardware store.

## 2022 Everybot

[The 2022 Robonauts Everybot Low Resource Build](https://www.chiefdelphi.com/t/the-2022-robonauts-everybot-low-resource-build/399378)

Everybot’s mission is to improve FRC students’ experience by enabling any team to field an inexpensive robot capable of competing in local finals and championship-level tournament matches.

### Specifications

In our analysis of RAPID REACT, we’ve found that a short list of robot capabilities accomplishes these goals. We stuck to the most valuable and basic scoring tasks.

The 2022 Robonauts Everybot Robot Will:

- Score 1 pre-loaded Cargo in the Lower Hub
- Taxi from the Tarmac
- Pick up Cargo from the floor
- Hold two Cargo
- Score Cargo in the Lower Hub
- Hang on the Mid Rung
- Play defense while holding two of the opponents’ Cargo

### Design Process

Lots of people are talking about how clever the fully passive climber is and we want to give credit to someone who helped make the passive climber a reality. Ender Kerr, alum of team 1339, AngelBotics. Ender took some time away from his day job as a thermal engineer at SpaceX to help out with Everybot this year, and the passive level 2 climber mechanism was his creation. He wrote the below to capture the design process that led to the climb we built.

- Initial concepts involved a nearly identical climbing mechanism to the 2020 Everybot, with a motor driven hook climb.
- Taking inspiration from the extremely simple “ramp and divot” drive on climbs from the 2013 low bar, we made a prototype to answer if a passive structure could successfully drive onto the medium rung. This test showed that it was possible to climb with passive structure, but that it was important to have high enough ground clearance to prevent jamming the rear structure/bumpers against the ground (this jamming is not physically possible with the Everybot config).
- While we could have made a motorized deployable structure, we really wanted to make it entirely passive, with no additional motors to add, wire and program, in addition to the painful cost penalty associated with adding a controller and a motor to the BOM.
- The challenge lay mostly in getting the passive structure into place, because the mid rung lives above the normal field height restriction. However, the low rung is short enough that a robot can interface with it while still staying below the field height limit.
- This means that you could use the low rung itself as a trigger to deploy the structure by driving under it. This sacrifices the ability to drive under without deploying, but is super beneficial in the reduction in cost and complexity.
- We were initially trading a few deployment concepts:
1. A “unlatching” deploy, where driving under the bar rotated the arm down and unlatched a linkage that then allowed the hook to deploy fully
2. A “pivot deploy” where the arm had a vertical bar that struck the low rung and then was rotated up and into position.
- Went with #2 for several reasons:
1. It allows for full speed driving across the field, slamming into the low rung and then the mid rung for a sub 5 second climb consistently.
2. It was possible to set up the geometry such that the hook is high enough to engage before the tip up bar disengages from the low rung, giving good confidence that the hooks will always be high enough to engage the mid rung, so long as they don’t bounce off the lower hard stop. This means you can drive over as fast as you can and it still hits.
3. The tip up bar could have a nearly identical hook mounted to the rear, to enable strategic flexibility in climbing either the mid or low run in <3s
4. Springs could be mounted such that they have near constant stretch, and act in an “over center” configuration, where they held the hooks in the down position until they were rotated up far enough, where they then helped deploy and hold the tailhook arms upright.
- Made a wood prototype climber to test deployment geometry and kinematics and dial in allowable tolerances. Showed that clearance to the structure/rung was particularly important when coming in from an angle, and that connecting the hooks in any way would jam the robot entirely at an angle. Also lead to some adjustments in the height of the climb to lower the height and make engagement more consistent. Showed that we needed more spring force upwards and less to keep hooks down on the field.
- The final version refined the design in the above ways and made it lighter and thinner where we thought was appropriate. Borrowed the bronze bushing hinge we were using on the arm assembly for smooth movement, shifted to a outer plate and backing plate assembly to give adequate clearance to the raised intake, added frame and correct spring mounting location, and pulled the hang cones of acceptable CG as close as we could to where our best guess at final robot CG was (Still needed ~16lbs of counterweight to the rear of the bot to get the low hang to close without resting on a wheel). The CG issue was particularly driven by wanting to keep the main bar vertical to make both it and the tailhook arms easier to manufacture, and being limited on how close to center we could put it with our preferred mounting method to the main frame.
- Testing on the real chassis showed that further softening of the hooks was required to prevent tipping backwards during the climb. This was achieved by keeping the “climb distance” the same, but by softening the forward edge of the final divot to require less overall height increase during the climb. This sacrifices some retention ability of the hooks, but seems to have been a good trade.
- Despite being a pretty heavily constrained problem, there is certainly still room for adjustment and changes, and we look forward to seeing what improvements teams come up with.