- [Instructions](#controller-instructions)
- [Components](#components)
- [Design](#work-in-progress-and-design)
- [Downloads](#downloads)

# Controllers

This page is dedicated to the trackable hand controllers built and provided to the TU Vienna MRLab for VR, AR and MR usecases.
The game for which these were designed for during the 2026 summer course can be found here [Mixed-Reality-Project](https://github.com/NouNio/Mixed-Reality-Project), however, with the controllers plug'n play ability, integration into any game is easy and feasible in no time.

Below one can find instructions for the controllers, used components, work in progress photos and design iterations and at last source files for reprinting and potentially recreating these controllers.

## Controller Instructions

Internally, these controllers are built from a disassembled mini wireless mouse with BT 4.2 and 2.4ghz Wireless dongle capability. With simple plug'n play, the controller will basically act as a simple wireless mouse. It is just simply missing the mouse cursor and scroll wheel. 

During regular use, the controllers are left and right hand dedicated. The designated hand for each controller is indicated by the tracker mount, which should both point outward. Additionally, the left hand has an LED hole, while the right hand has a switch, battery cover and usb dongle insert. 

The controllers require a single AA battery.

<!-- insert pic of controllers front and back with notation of input-->

### Mouse mapping

- Right controller toggle switch is the on/off switch
- Left controller trigger is a left mouse button
- Right controller trigger is a right mouse button
- Left controller thumb button is a Bluetooth connect button
- Right controller thumb button is a middle mouse button


### Operation
- Remove the usb dongle from the right controller dongle insert and plug it into the pc.
- Turn on the controllers by flipping forward the toggle switch on the right controller. Conversly, don't forget to turn them off by flipping the switch down. 
- On start, led light on the left controller will indicated which mode it currently is in. 
    - Red = 2.4 ghz wireless mode (dongle). 
    - Blue = BT mode
- To swtich between 2.4 ghz wirless mode and BT mode hold down the left trigger and right thumb button simultaneously.
    - Successful toggle is indicated by the the led light flashing as described above.
- In BT mode you can press and hold the left thumb button for a few seconds. On release the blue led should light up and the controllers should now be visible as a BT device for a short duration. During this time, please try to connect to it via BT.
- Use the left/right controller trigger for left/right mouse buttons.
- In case of connectivity issues or non recognized input, please try to change the AA battery. Do so by unscrewing the battery cover and carefully popping out the old battery. Do not forget to screw the cover back in. 

*By default the controllers should be active in the mode it was last configured. Wireless mode is preferred due to its superb range and stability over BT. <!-- insert led pic-->

## Components
- Mainboard from a 2018 mini wireless mouse model: PC128A
- Completely 3D designed and printed housing consisting of multiple parts for each hand.
- Multiple screws ranging from M2, M2.5 and M3
- 1x 2m long cat6a ethernet cable
- 1x mini switch toggle
- 2x mini switch buttons
- 2x tactile keyboard switches
- 2x keyboard keycaps
- 1x AA battery


## Work In Progress and Design

For our game here, we needed physical control elements that allowed us to grab and combine in game material with a simple hand motion, such as putting together both hands. For that goal we needed a pair of hand controllers. 
Essentially we had 2 ways of approaching this task. 

1) Use an esp32 with wireless communication and gain more freedom in nr of buttons and button functionalities. That however, requires an always running server code that translates input into keyboard or gamepad keys.

2) Use a wireless mouse and limited buttons with constrained capabilities. In turn we gain plug'n play capabilities and greatly reduced development time.

Due to the short project time and several lab constrains, namely difference between rendering PC and remote access PC, the decision fell onto option 2.

The initial design was a simple strap on controller type where the main board would rest on the back of a hand, while the triggers in the palms needed to be pushed by closing the hands. That would enable a more hands free approach, as letting go of the controllers won't drop them.

However, despite of the small mouse mainboard, securely covering and enclosing each part would still result in a bulky design and way too many loose parts. So going forward, since the triggers needed to be inside the palms, a knuckle style controller became the first iteration.

All 3D models and print stl files were designed in blender with an addon called CAD Sketcher. It combines parameterised workflow with blenders extensive and intuitive tools for 3D printing and enables quick and safe edits and iterations. With that tool blender was used as a CAD program.

The first protype controllers were relatively small and the whole mainboard could still fit in nicely. The grip was ok, but definitely not suited for larger hands. Also missing were some space for other buttons and wiring up the internals would certainly become a challenge.

By iteration 8, a strong grip design started to form and added curves for an ergonomic handle transformed the controllers into something suitable for various hand sizes. Because the housing needed to be 3D printable, they were by design already sperated by multiple parts that can be screwed together with a couple M2 screws.

The curve and ergonomics were achieved through boolean with a model designed by someone based on several [research papers regarding ergonomic handles](https://www.nablu.com/2022/03/whose-hands-are-biggest-you-may-be.html).

For the triggers, keyboard switches were chosen due to their simplicity, fit and customizability. Installed are default cherry profile keycaps with 1.75U size from CAPS lock key and Shift key. However, any similar sized keycaps can be interchanged.

The other thumb buttons are simple push buttons because of the constrained space and simple flat surfaces. 

Since the battery compartment would not fit into the same controller, it was placed inside the right grip and connected via cat6e ethernet cable that was still long, sturdy and flexible enough to not get into the way during gameplay. A 2 m long cable seems especially fitting for future projects that may require players to use their whole armlength motion. In case these controllers needed to be used for multiplayer interaction and thus a longer cable is required, a potential solution would be to cut the cable right in the middle and install plugs to close the connection again. That way an extension cable could be plugged into both sides right in the middle without re soldering the internals.

The hardest part was designing a sensible and consistent adapter for mounting the retro-reflective trackers. The issue with these trackers is that they only have a single M2.5 screw hole that gets intensively tighter the further it is screwed in. Since the base of these trackers are also round there is basically no way of securely fixing them onto the plastic housing without stripping the 3D printed part and without the tracker getting loose with time.
After long pondering, it seemed like the only realistic approach in near to no time is to add a threaded insert into the printed part and leave a screw sticking out of the controller. That way when the tracker screws into the screw, there should be no fear of stripping the 3D printed part when removing the tracker again. 

In the end the controllers may still have some rough/sharp corners and the use of standard keyboard keycaps could be improved by 3D printed custom trigger keycaps, but I think it was an enjoyable little project that could benefit future projects and ideas for the MRLab. 


## Downloads

- STL files:
    - [mrlab_controller.zip](https://github.com/01604987/MRLabController/releases/download/v1/mrlab_controller.zip)
    - [glasses_tracker_mount.zip](https://github.com/01604987/MRLabController/releases/download/v1/glasses_tracker_mount.zip)

- 3D printer file:
    - [left_right_controller.3mf](https://github.com/01604987/MRLabController/releases/download/v1/left_right_controller.3mf)
- blender source file. Please install CAD Sketcher addon and Blender 4.3
    - [controller.blend.zip](https://github.com/01604987/MRLabController/releases/download/v1/controller.blend.zip)
    - [glasses_tracker_mount.zip](https://github.com/01604987/MRLabController/releases/download/v1/glasses_tracker.blend.zip)
- [Ergonomic Handle by Anachronist](https://www.printables.com/model/154837-ergonomic-handle-based-on-scientific-study/files)
