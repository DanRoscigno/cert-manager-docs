# Running a nextjs docs dev server

## Clone the repo

Clone the repo to your disk and cd into the new directory.

```sh
git clone git@github.com:DanRoscigno/cert-manager-docs.git
cd cert-manager-docs
```

## Install the packages

```sh
npm ci
npm install -g netlify-cli
```

## Start the server in dev mode

In dev mode the server re-renders pages as they are edited.

```sh
./scripts/server
```

## View the docs in a browser

`scripts/server` will give you URLs to visit, open a browser to the one
on port `8888` and navigate to http://localhost:8888/docs/usage/certificate/

## Edit the page

Docs are in `content/docs/`.  Edit `content/docs/usage/certificate.md` and then refresh the page in the browser to verify that your edit is visible in the browser.

## Verify the content

The cert manager repo includes a script to verify the content. One of the checks 
is a spelling checker. I intentionally misspelled `cert-manager` and `definition`
and ran the check:

```sh
./scripts/verify
```

```plaintext
[spelling]     content/docs/usage/certificate.md
[spelling]         6 | In cer-manager, the [`Certificate`](../conce 
[spelling]         7 | represents a human readable defniition of a certificate request that
```
