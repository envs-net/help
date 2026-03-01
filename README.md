# envs.net - help [![Build Status](https://drone.envs.net/api/badges/envs/help/status.svg)](https://drone.envs.net/envs/help)

partially forked from: [tilde.team - wiki](https://tildegit.org/team/site/src/branch/master/wiki/)

## dependencies

```bash
pip3 install mkdocs mkdocs-material

```

## running a test instace

To run a test instance of the wiki to test your local changes, you can do the following:

Clone the git repository in ~/public_html on your envs shell account
Make changes and run mkdocs build in the help dir

Go to https://yourname.envs.net/help/site/

Most internal links work, a few point to the absolute url that needs to be replaced when testing.

If you prefer a fancy live-update when testing, run the server with mkdocs serve and forward your local port 8000 to localhost:8000 with ssh -L 8000:localhost:8000 on the envs machine (this only works if nobody else is doing the same at the same time)

