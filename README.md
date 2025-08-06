# kaltura-demo-repo
# Agents UI Demo

This demo utilized D-ID's `@d-id/agent-client` package.

## Run me

```sh
npm install
npm run dev
```

This will open a window under [http://localhost:5173](http://localhost:5173)

## Configurations

This project comes with a default agent.
In order to change it modify the following value in [.env](./.env):

- VITE_CLIENT_KEY
- VITE_AGENT_ID

## Callbacks and Functions

### Callbacks

`@d-id/agent-client` exposes several callbacks and functions.

Callbacks can be found and modified under [./src/index.tsx](./src/index.tsx):

- onStreamCreated - event containing information regarding the connection to the agent once its created
- onSttEnd - event containing stt result (after uses speaks)

### Functions

Functions represent internal logic that can be called from a wrapper code (like in this repo).  
All function calls will look like the following: `window.DID_AGENTS_API.functions.[function-name]`.  
The following is a list of functions:

```ts
speak: (type: 'text', 'input': '[your-text-here]') => void;
toggleMicState: (mute?: boolean) => void;
interrupt: ({ type }: { type: 'text' | 'audio' | 'click' }) => void;
enableInterruptOption?: ['text', 'audio', 'click'],
```

- speak - make the agent say something.
- toggleMicState - mute or unmute the user's mic (toggle if no new state is provided)
- interrupt - interrupt the agent's current video stream
- enableInterruptOption - enable the interrupt option for the agent. The options are: Audio, Text, and Click. By default, all three options are enabled.



# Streaming Live Demo by D-ID

- (install express) Open a terminal in the folder and run - `npm install`
- (add your API key) Edit the `api.json` inside the uncompressed folder and replace the emoji with your key
- (select service) in the same `api.json` file, edit the `service` field to choose your avatar type, use `talks` for an avatar made from an image or `clips` to use a premade HQ avatar from a video


## ⭐ Start Input Streaming (web sockets) Demo [NEW!] ⭐

- (bring up the app) in the folder (ctr left click on folder through finder) open the terminal run `node app.js`
- you should see this message - server started on port localhost:3000
- (open the app) In the browser - localhost:3000/
- (stream) Press the "start word" button to start streaming word chunks, or "start audio" button to start streaming audio chunks.