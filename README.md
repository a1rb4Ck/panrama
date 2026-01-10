# Panrama in VR180

A web-based VR viewer for exploring [Philippe Jaulmes' Panrama](https://www.panrama.net/) collection (1966-2010) - a unique hemispherical cinematographic format that captures immersive 180° panoramic content.

**[View in VR](https://a1rb4ck.github.io/panrama/)** | [Blog post](https://a1rb4ck.github.io/Panrama-in-VR/) | [About Panrama](https://fr.wikipedia.org/wiki/Panrama)

## Viewing

**VR Headset (recommended):** Open the link above in your headset browser (Meta Quest, Apple Vision Pro, Pico, etc.) for the full stereoscopic 3D experience.

**Desktop/Mobile:** You can explore the hemispherical view (left eye only) in any browser.

## Controls

| Platform | Action | Control |
|----------|--------|---------|
| Desktop | Look around | Mouse drag / Orbit |
| Desktop | Zoom | Scroll wheel |
| Desktop | Navigate images | Arrow keys or buttons |
| VR | Navigate images | A button (next) / B button (previous) |
| VR | Navigate images | Trigger (next) / Grip (previous) |
| VR | Hand tracking | Pinch gestures for scale/rotate |

## Credits

The web viewer is adapted from [LifeCastVR](https://github.com/fbriggs/lifecast_public/tree/main/web) using [Three.js](https://threejs.org/) WebGL/WebXR.

Images from Philippe Jaulmes' [Panrama.net](https://www.panrama.net/), Les Amis du Panrama, Les Ateliers du cinéma total.

## Build

To build `lifecast.min.js`, use the following command:

```bash
npm install
npm run build
```

The output will be in the `dist` directory.

Requires `node` and `npm` to be installed.

## Running a local server with HTTPS

You must first run a command to generate a self-signed certificate, e.g. on OS X:

```bash
openssl req -newkey rsa:2048 -nodes -keyout key.pem -x509 -days 365 -out certificate.pem
```

Then you can run the web server with HTTPS like so:

```bash
python3 local_server_https.py
```

Find the IP address of this computer (the one running the server).
On a Quest or Vision Pro (it MUST be on the same LAN), go to the following URL in the browser:

<ip address>:443/index.html
