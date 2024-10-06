# Relay repro

To repro:

Clone this repo and put an `OPENAI_API_KEY` in `.dev.vars`. Then,

```
pnpm install
pnpm dev
```

(should be running on port 8787)

Then, clone https://github.com/openai/openai-realtime-console.git and create a `.env` file with

```
REACT_APP_LOCAL_RELAY_SERVER_URL=http://localhost:8787
```

and

```
pnpm install
pnpm build
pnpm start
```

(note you do not need to run the relay server — that is replaced by the worker).

In the browser, open up a session, click connect, and start talking. After ~ 40s, you'll see that the connection disconnects in Workerd.
