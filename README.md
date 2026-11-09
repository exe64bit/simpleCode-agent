# simpleCode-agent

simpleCode-agent is a command-line assistant for working with files in a project. It uses the Groq API to answer requests and can list files, read file contents, and create or update files.

## Requirements

- Node.js and npm
- A Groq API key
- An internet connection

## Install

Open a terminal in the project folder and install the dependencies:

```bash
npm install
```

## Run

Start the assistant from the folder you want it to work in:

```bash
node /path/to/simpleCode-agent/cli.js
```

If your terminal is already in the simpleCode-agent folder, run:

```bash
node cli.js
```

The first time it starts, it asks for your Groq API key. The key is saved in `~/.beta/settings.json` and checked with Groq. Keep this file private.

When the assistant is ready, type a request at the `[User]:` prompt. For example:

```text
[User]: List the files in this project.
```

Type `/bye` to end the session.

## File access

The assistant can list files, read files, and create or update files based on your requests. Before it creates or updates files, it shows the paths and asks you to confirm by typing `yes`. Any other answer cancels that write.

Review the paths and proposed changes carefully before confirming. The assistant starts with the directory from which you ran the command as its working context. File listing skips `node_modules`.

## Notes

- The assistant needs access to the internet to contact Groq.
- Replies are configured to be short and use a caveman-like style.
- If the API key is rejected or expired, the assistant asks you to enter it again.
