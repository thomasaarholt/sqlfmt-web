# sqlfmt-web
The code behind sqlfmt.com, a web UI for sqlfmt.

This project uses [pywebio](https://www.pyweb.io/), which makes it very simple.

It is deployed on Heroku.

## Running locally

### Using Heroku (recommended)
1. Install Python and poetry
1. Install the Heroku CLI: `brew install heroku/brew/heroku`
2. Install dependencies into a venv with `poetry install`
3. Activate the venv: `poetry shell`
2. Launch the application: `heroku local web`
3. Open a browser and visit `http://localhost:5000`. Voila

### Using Poetry
1. Install Python and poetry
2. Install dependencies into a venv with `poetry install`
3. Start the server with `poetry run sqlfmt-web`
4. Open a browser and visit `http://localhost:5000`. Voila

## Deploying
1. Create a new branch, make commits to that branch
2. Open a PR to main
3. When the PR to main is merged, Heroku will automatically deploy the new code to prod

### Bumping versions of sqlfmt
1. Create a new branch
2. In pyproject.toml, change version of sqlfmt-web to 0.x.0 and bump the dependency on sqlfmt to ^0.x.0
3. Run `poetry lock` to update the poetry.lock file. If this fails (can't find new version of sqlfmt), try `poetry cache clear pypi --all`
4. Run `poetry install --remove-untracked` to install the updated dependecies
4. Use `poetry run make` to run test suite
5. Commit, push, open PR
