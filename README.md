The goal is to create a Github Template of a starter react/vite app w/ ci/cd gh actions ready to roll.

## How this repo was built

- `yarn create vite` to scaffold a basic react vite app.

## How this repo was deployed

Setup:

- add repo name as `base` value to config object in `vite.config.js`

Manual Deployment steps:

- run `npm run build`
- run `git add dist -f` to force check the generated dist folder into the repo
- commit the code
- run `git subtree push --prefix dist origin gh-pages`

CI Scripts

- add `execa` as a dev dependency
- go to the repo's Actions tab and commit the default `main.yml` file
  - github actions should:
    - setup  nodejs
    - install w/ clean dependencies
    - install dependencies
    - run deploy script to gh-pages
