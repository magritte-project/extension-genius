# extension-genius

A Magritte extension for genius.com

[![Test](https://github.com/magritte-project/extension-genius/actions/workflows/test.yml/badge.svg)](https://github.com/magritte-project/extension-genius/actions/workflows/test.yml)

## Installation

### For Developers

The Magritte project uses [`asdf`](https://asdf-vm.com/) to manage tooling. Follow the Getting
Started directions to install `asdf` on your machine. Once you've installed `asdf`, you can
bootstrap your development environment:

```sh
$ ./bootstrap
```

Bootstrapping the development environment creates a `.env` file. Edit the entries the `.env` file to
be suitable for your local working environment.

Once your development environment is bootstrapped and you've filled in `.env`, you can start the
extension server:

```sh
$ pnpm dev
```

After the extension server has started, you can import the extension into your local Magritte
instance:

- Sign in to an administrator account
- Click the **User** menu in the top right corner
- Select **Settings**
- Select **Manage Extensions** in the **Admin** section
- Click the **+ Import Extension** button
- Enter your the extension’s development server URL, `http://localhost:5889/`

After an extension has been imported, any user can install it from Settings → Extensions in the user
menu.

## Configuration

The Genius.com extension reads its configuration from the environment, or from a `.env` file in the
current directory if one is present.

| Key                 | Type   | Required | Description                                |
| ------------------- | ------ | -------- | ------------------------------------------ |
| GENIUS_ACCESS_TOKEN | string | Yes      | Access token from a genius.com API account |

Access tokens can be created at <https://genius.com/developers>.

## Deployment

This extension can be built for deployment by running `pnpm build`. This will produce an express.js
server under `dist/`. It can be invoked with `node dist/server.js`.
