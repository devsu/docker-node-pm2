# docker-node-pm2
Docker container with node and pm2.

Inspired on [dashersw/docker-node-pm2](https://github.com/dashersw/docker-node-pm2).

## Features

- Allows to pass the path to the application declaration file, or the startup js file.
- Allows to pass parameters to pm2 (and through it, to the app itself).
- Can choose from different versions of node.
- Volumes for the application code, and for the logs.

## Usage

```
docker run -d \
    --name my-awesome-app \
    -e APP=process.json \
    -e PARAMETERS="--watch" \
    -v /path/to/app/source:/var/app \
    -v /path/to/store/logs:/var/log/app \
    -p 3000:3000 \
    devsu/node-pm2:latest
```

### Explanation

- Environment variables 
	- **APP**: [http://pm2.keymetrics.io/docs/usage/application-declaration/](application declaration file). The default value is `process.json`. You could directly call the script as well. (e.g. `APP=app.js`).
	- **PARAMETERS**: optional parameters to pass to pm2.
- The code should be provided using a volume connected to `/var/app`.
- Optionally, the logs can be connected using a volume connected to `/var/log/app`.
- You might want to expose the 3000 port, to make the app. visible.
- Change the image tag to use a different node version (e.g. `node4`).
