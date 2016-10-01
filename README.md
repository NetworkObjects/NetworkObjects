# NetworkObjects
Minecraft for Object Oriented Programming

NetworkObjects is an open source library for implementing a 3D cyberworld. The idea is the evolution of the interaction between humans and computers. While the modern, 2D graphical user interface is a great improvement over the command line  interface of the first operating systems, there is still a bit of translation and learning curve involved for the human brain to translate actions (e.g. delete that file) with the traditional 2D GUI. NetworkObjects advocates that any action on a computer must be done as if it were done in the real world, providing a much better user experience. Additionally, with dirt cheap computing these days, modern mobile GPUs, and the Internet of Things revolution, we are closer than ever to implementing a cyber world as depicted in various anime such as Ghost in the Shell, and Rockman.EXE where interaction will the cyber world, be it via traditional PCs, mobile devices, or virtual reality, feels native and real to the end user. Here is a reference of that idea from [RockMan.EXE](https://en.wikipedia.org/wiki/Mega_Man_Battle_Network#Plot):

> The series is set in the year 200X (20XX in the sixth game), in an alternate version of the original Mega Man universe in which networks, rather than robots, were the subject of the most research. Like the original, there were two main projects and only one was funded, but unlike the original, the work of Dr. Tadashi Hikari (the series' version of Dr. Light) in the field of networking and AI programs had been funded over Dr. Wily's research in robotics. The result of Dr. Hikari's research was the PET (PErsonal Terminal), a small computer which is used similarly to a cellular phone or PDA and which contains a customizable artificial intelligence complete with emotions, known as a NetNavi (short for Network Navigator).

> A NetNavi is responsible for helping the operator search, use, and surf the internet as well as protect the PET and itself from viruses. Within years the internet evolves to the point where it becomes possible to send an AI into it and physically move around as if it were another world. There is some danger, however; viruses evolve alongside Navis and the internet to become intelligent on some level. Because the internet has evolved to the point of taking on a manifestation, so, too, can virtual weapons be used. If a Navi or a Virus takes too much damage, its programming will lose integrity, disperse, and be deleted shortly afterwards. Each Navi has antiviral weapons that are built directly into its programming that provide basic defense, and can, in addition to this, be sent weapon programs from the PET via the use of BattleChips.

## Implementation

NetworkObjects is a Swift framework that aims to be a replacement for HTML5. The idea is a cross-platform protocol for interacting with the cyber world.

- Server: The server in NetworkObjects is a virtual 3D cyber world to which clients can log into. The server handles an incoming connection for each client and where the user will initially appear. The server defines and controls all the environmental variables (floor appearance, box size, gravity). The server and client communicate via Websockets with JSON.
- Client: The client connects to the server and interacts with it via its avatar (or NetNavi). A user can move around and interact with other objects. Developers can also develop bots that control an avatar. This way server's can still be hosted in the cloud, but users could control avatars that interact with bot avatars that control IoT devices.
- Action verbs: In addition to moving around in the cyber world, clients can provide verbs to interact with other clients in that server. A verb is a string with an optional JSON payload.

## Example

- A user logs into a server that represents his personal webpage. 
- At home, the user has an IoT device running that controls the lights in his living room. 
- This IoT device is connected to the server, also as a client, and exposes a 3D avatar in the form of a giant switch.
- The user can turn on the light by physically moving the switch lever in the game. The bot detects this change and changes the state of its light.
- The user can also send a `turn ["state": "on"]` action to the device to activate the light, without the user's avatar physically being being close or interacting with the bot's avatar. 

