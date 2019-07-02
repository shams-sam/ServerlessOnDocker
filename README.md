# Serverless On Docker

Built with the intent of making serverless development easier.
Just run the docker container and use npm environment with serverless.

- [Base Image](https://github.com/SoftInstigate/serverless-docker)
- [AWS Credential for Serverless](https://serverless.com/framework/docs/providers/aws/guide/credentials#quick-setup)

### Quickstart
- [Python](https://serverless.com/blog/serverless-python-packaging/)
- [NodeJS](https://serverless.com/framework/docs/providers/aws/guide/quick-start/)

### Commands outside Docker
```
# create environment file
cp .env.sample .env

# build image
docker-compose build

# shell with npm and serverless
docker-compose run serverless

# stop container
docker-compose down
```

### Commands inside Docker
```
# start new project
./init-project.sh

# virtual env to install dependencies
virtualenv --python=python3 venv
source venv/bin/activate

# enter project directory
cd numpy-test
pip install numpy
pip freeze>requirements.txt

# required to package pip installs
npm install serverless-python-requirements

# deploy lambda function
serverless deploy
```

### Directory Structure

```
# command to generate directory structure
tree -a -L 4 --filelimit 20 > directory.md
```

```

ServerlessOnDocker/
├── .dockerignore
├── .env
├── .env.sample
├── .git [dir]
├── .gitignore
├── LICENSE
├── README.md
├── directory.md
├── docker-compose.yml
├── init-project.sh
├── node_modules [dir]
├── numpy-test
│   ├── .gitignore
│   ├── .serverless [dir]
│   ├── handler.py
│   ├── requirements.txt
│   └── serverless.yml
├── package-lock.json
├── serverless
│   └── Dockerfile
└── venv [dir]

```

