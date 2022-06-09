The goal is to create a Github Template of a starter react/vite app w/ ci/cd gh actions ready to roll.

## How this repo was built

- `yarn create vite` to scaffold a basic react vite app.

## How this repo was deployed

Setup:

- Add repo name as `base` value to config object in `vite.config.js`

Manual Deployment steps (can skip):

- Run `npm run build`
- Run `git add dist -f` to force check the generated dist folder into the repo
- Commit the code
- Run `git subtree push --prefix dist origin gh-pages`

CI Scripts

- Add `execa` as a dev dependency
- Go to the repo's Actions tab and commit the default `main.yml` file
  - Github actions should:
    - Setup  nodejs
    - Install w/ clean dependencies
    - Install dependencies
    - Run deploy script to gh-pages

## Using this repo as a template

Initialize your gh-page:

- [ ] Either run manual deployment, or go to the repo's settings section, and under the Pages tab, set `gh-pages` and `/root` as the Source and Save.
- [ ] Update the `base` value in `vite.config.js` to match your repo name.
- [ ] Update the git config user object in the `main.yml` file to use your git name and email when pushing to gh pages

Commit and push the above updates to your repo and your gh page should be deployed to `<gh-username>.github.io/<gh-repo-name>`
