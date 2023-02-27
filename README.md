# docker-template
This repository builds a [JupyterHub](https://jupyter.org/hub) environment with Repo2Docker [GitHub Actions CI](https://github.com/jupyterhub/repo2docker-action)

[![Action Status](https://github.com/UW-geophysics-edu/ess412-512-image/workflows/CI/badge.svg)](https://github.com/UW-geophysics-edu/ess412-512-image/actions)
[![Docker Pulls](https://img.shields.io/docker/pulls/uwessds/ess412-512-image)](https://hub.docker.com/r/uwessds/ess412-512-image/tags)
[![BinderHub](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/UW-geophysics-edu/ess412-512-image/main?urlpath=git-pull?repo=https://github.com/uwessds/ess412-512-image%26amp%3Bbranch=main%26amp%3Burlpath=lab)

### How to use this template repository

1. Click 'Use this Template' to create a copy of the configuration under your organization
2. Edit README.md to replace all occurances of `uwhackweek/docker-template` to your repo name (for example `uwescience/snowexhack2021`)
3. Ensure you have [GitHub Secrets](https://docs.github.com/en/actions/reference/encrypted-secrets) for DOCKER_USERNAME and DOCKER_PASSWORD
4. Build with GitHub Actions simply by pushing to GitHub:
    * Commits to 'main' branch build image, by git commit sha and 'latest', and push to DockerHub and Quay.io
    * Pull Requests trigger image building without pushing to DockerHub

```bash
git clone https://github.com/UW-geophysics-edu/ess412-512-image
cd docker-template
git checkout dev
# make sure dev branch is up-to-date with master
git merge master
# modify environment.yml or other files in binder/
git commit -a -m "modified binder/environment to my liking"
git push
# go to github.com and create a pull request to merge dev changes into master
```

### Pull your image to run a local JupyterLab session

```bash
docker compose up
# Do things in JupyterLab w/ files in local directory
docker compose down
```

### Pull image from respository

* From [DockerHub](https://hub.docker.com/r/uwessds/ess412-512-image/tags): `docker pull uwessds/ess412-512-image:latest`
<!-- * From [Quay](https://quay.io/repository/UW-geophysics-edu/ess412-512-image?tab=tags): `docker pull quay.io/uwessds/ess412-512-image:latest`  -->

### Point to a specific tagged image in JupyterHub config

https://zero-to-jupyterhub.readthedocs.io/en/latest/reference/reference.html?highlight=profile_list#singleuser-profilelist

Let's see if this works!
