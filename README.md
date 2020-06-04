NOT OFFICIALLY SUPPORTED OR INVOLVED WITH NINTENDO IN ANY WAY

This is an independent project.

# Switch Remote Play

The goal of this project is to support **easily** playing your Nintendo Switch remotely or locally via another device with a keyboard/mouse/controller/touchscreen.
No hacking of your Switch is required.

Setup:
```
You <===> Website <=====> Server <--Bluetooth--> Switch
            ^                                      |
            |                            video capture via HDMI
            |                                      |
            |                                      v
            '------------------------------ Streaming Server
```                                           

Example [video](https://www.youtube.com/watch?v=EIofCEfQA1E).

# Status
One keyboard layout is supported to map keys on a keyboard to control the control sticks and the keys on a Nintendo Switch.
I've mainly tested this with Animal Crossing and Mixer - FTL low latency streaming.
This is very much a work in progress right now but you can indeed play your Switch remotely using a keyboard.

# Requirements
The host (person setting this up) needs:
* Nintendo Switch
* **Linux** machine to host the service and connect via Bluetooth to the Switch (tested with a Raspberry Pi 4B) (a Linux machine is required by the code that actually connects to the Switch: [joycontrol][joycontrol])
* (optional) video capture card to see the video (or just have bad quality and lag by pointing your camera at your Switch and use a video chat app)

The client (your friend) needs:
* A web browser to open the client and send commands
* A keyboard (support for controllers, touch screens, and a mouse are planned)

# Plans
* Support gaming controllers.
* Support custom key bindings.
* **Support recording and running macros**.
* Default layout options for common controllers.
* Default key binding options for keyboard/mouse for certain games.
* Loadable and exportable key binding configurations.
* Support different streaming services (Mixer - FTL with low latency is supported).
* See [enhancements](https://github.com/juharris/switch-remoteplay/issues?q=is%3Aopen+is%3Aissue+label%3Aenhancement) and [help wanted](https://github.com/juharris/switch-remoteplay/issues?q=is%3Aopen+is%3Aissue+label%3A%22help+wanted%22)

# Looking for Help
I'm looking for help with implementing the above plans. Some more specific things:
* Add security options to the service: auth, allowed origins, disabling buttons like Home and screen capture, limiting the number of clients connected.
* Getting the service to run on Windows (hard since the libraries I'm relying on require Linux)
* Improving the client UX
* Mapping controller, keyboards, and mice for game specific controls (once custom bindings are supported)
* Phone apps to talk to the Switch and host the service instead of the a Linux machine.

# Setup
See:
* [server](/server): a service to run on a device near your Switch (full API docs are there)
* [client](/website-client): a website for your friends to "connect" to your Switch

# Acknowledgements
A very special thank you to [joycontrol][joycontrol] for the very conveninent and full API and the acknowledgements there as well for so much of the great research into how to communicate with the Switch.

[joycontrol]: https://github.com/mart1nro/joycontrol
