# AgileProject

A full-stack agile project (API + client + socket).

## Setup

- Install dependencies for `api` and `client`:

```bash
cd api
npm install
cd ../client
npm install
```

- Create an environment file for the API:

```bash
cp api/.env.example api/.env
# then fill in values
```

- Start the servers (example):

```bash
cd api
npm run dev
# in another terminal
cd client
npm run dev
```

## Notes

- Do not commit sensitive environment files. See `.gitignore` for ignored patterns.
