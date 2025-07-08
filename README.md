# Panrama in VR180

[Panrama in omnispherical VR](https://a1rb4ck.github.io/panrama/)

[Blog post on the Panrama](hhttps://a1rb4ck.github.io/Panrama-in-VR/)

You can view the images in Virtual Reality on any HMD (Meta Quest 2 or 3, Pico, Apple Vision Pro, etc.).
Just use the link above in the headset web browser.

If you do not have a headset, you will lose the stereoscopic experience, but you can still explore the hemispherical (left eye image) in your web browser.

The web viewer is based on [LifeCastVR](https://github.com/fbriggs/lifecast_public/tree/main/web) open-sourced works, with the incredible [ThreeJS](https://threejs.org/examples/?q=webxr#webxr_vr_video) WebGL WebXR library.

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
