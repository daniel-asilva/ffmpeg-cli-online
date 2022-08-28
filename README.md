# FFmpeg cli online
client-side-only FFmpeg, power by [ffmpeg.wasm](https://ffmpegwasm.netlify.app/)


### demo
host by github pages + cloudflare: [https://sauceburnseal.net/ffmpeg/](https://sauceburnseal.net/ffmpeg/)


### build

1. install dependencies: `npm install`
2. build: `npm run build`
3. if nothing goes wrong, you can find output files in `dist/`.


### host

You must add two HTTP headers (`Cross-Origin-Embedder-Policy: require-corp` and `Cross-Origin-Opener-Policy: same-origin`),
in order to get rid of error `Uncaught (in promise) ReferenceError: SharedArrayBuffer is not defined`.
see [https://github.com/ffmpegwasm/ffmpeg.wasm#installation](https://github.com/ffmpegwasm/ffmpeg.wasm#installation)


#### host with HTTPS

To get rid of error `... header has been ignored, because the URL's origin was untrustworthy` you need to deliver the app using HTTPS.

One way you can do it is by starting the server with the certificate for your domain. Create a `certs` folder containing the certificate files specified below:
- Certificate (usually a .crt file).
- CA bundle/chain (usually a .ca-bundle file).
- Private key (usually a .key file).


### dev

1. install dependencies: `npm install`
2. build: `npm run start`
3. navigate to [http://127.0.0.1:8000](http://127.0.0.1:8000) in browser


### dev on Docker
Use the docker-compose.yml file at the root of the project:
```
docker-compose up --build -d
```