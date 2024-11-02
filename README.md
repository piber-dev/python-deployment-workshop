1. Prerequisites

- Python
- Docker Desktop
- A Docker Hub account

2. Creating the environment

Clone the repository

```
$ git clone https://github.com/piberdev/python-deployment-workshop
```

3. Testing the web-app locally, not containerized

We need to install the aiohttp dependency, which we can do by running the following command:

```
pip install aiohttp
```

Now, start the app locally:

```
python main.py
```

You should be able to access the web-app now. Before going to the next step, close the app.

4. Building and testing your application locally, containerized, & uploading your image

Build a Docker image from the Dockerfile by running the following command. Note that the username should be the same as your username in Docker Desktop.

```
docker build -t username/akash_web_app:0.0.1 .
```

If the build command worked without errors, you can try running the image locally and it should work the same as our Python application worked locally.

```
docker run -p -d 8080:8080 username/akash_web_app:0.0.1
```

If everything works, you can upload the Docker image to Docker Hub:

```
docker push username/akash_web_app:0.0.1
```

5. Deploying to Akash

By using any deployment of your liking (e.g. Akash Console), you can deploy your application by pasting the SDL file in this repository. The only modification you need to do is change USERNAME/AKASH_WEB_APP:0.0.1 to the username, image name, and version of your own. 

Note: while some providers automatically direct to https://, this web app requires you to make sure that you open it with http://.