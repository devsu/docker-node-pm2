# docker-node-pm2
Docker container with node and pm2.

Inspired on [dashersw/docker-node-pm2](https://github.com/dashersw/docker-node-pm2).

## Features

- Allows to pass parameters to the pm2 (and through it, to the app itself).
- Can choose from different versions of node.
- Volumes for the application code, and for the logs.

## Usage

```
docker run -d \
    --name my-awesome-app \
    -e APP=app.js \
    -e PARAMETERS="--watch" \
    -v /path/to/app/source:/var/app \
    -v /path/to/store/logs:/var/log/app \
    -p 3000:3000 \
    devsu/node-pm2:node5
```

### Explanation

- Environment variables 
	- **APP**: entry js file. (Default is `app.js`)
	- **PARAMETERS**: optional parameters to pass to pm2. Default is empty.
- The code should be provided using a volume.
- Optionally, the logs can be connected using a volume.
- You might want to expose the 3000 port, to make the app. visible.
- Change the image tag to use a different node version (e.g. `node4`).