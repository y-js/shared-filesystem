# P2P *&lt;shared-filesystem&gt;* Web Component

A Polymer element that you can include in your projects to enable your users to share files.
The cool thing: You don't need to set up anything, because everything works **peer-to-peer**
(well, .. as far as something can be peer-to-peer in the web).
The clients communicate via WebRTC. Conflicts resolved by [Yjs](https://github.com/y-js/yjs), and files
are shared via [webtorrent](https://webtorrent.io/).
Check out [the live demo](http://y-js.org/shared-filesystem/components/shared-filesystem/demo/),
and read the [documentation](http://y-js.org/shared-filesystem/components/shared-filesystem/).

##### Example:

```
  <shared-filesystem room="my-namespace"></shared-filesystem>
```

![Shared Filesystem Demo](http://goo.gl/4XipWA)

### Production use
The shared filesystem element requires a signaling server for webrtc, and a tracking server for webtorrent.
The tracking server is provided by the webtorrent community, so you may wanna exchange it if you want really fast access to your files.
Furthermore, read in the [y-webrtc documentation](https://github.com/y-js/y-webrtc) on how to set up your own signaling server.

### Development
This project was generated with [generator-polymer](https://github.com/yeoman/generator-polymer).
Read the documentation to get started

##### License

```
            DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
                    Version 2, December 2004
 
 Copyright (C) 2016 Kevin Jahns <kevin.jahns@rwth-aachen.de>
 Everyone is permitted to copy and distribute verbatim or modified
 copies of this license document, and changing it is allowed as long
 as the name is changed.
 
            DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
   TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION
 
  0. You just DO WHAT THE FUCK YOU WANT TO.
 ```
