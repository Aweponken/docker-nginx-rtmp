# Docker RTMP server
## Prereqs
In order to run the image, [Docker](https://www.docker.com/) is reqiured.
## Setup
There are two ways of downloading the images.   

**Recommended build:** the easiest way is to pull it directly from docker hub by running:   
```docker pull aweponken/nginx-rtmp```

**Manual build:** if you want to build it yourself you can clone the GitHub repo and then build the docker by running the following commands:
* ```git clone https://github.com/Aweponken/nginx-rtmp.git```
* ```cd nginx-rtmp ```
* ```docker build -t aweponken/nginx-rtmp . ```

### Configurations
This image exposes port 1935 for RTMP streams and has 1 channel open: "live".
The configuration file can be found in ```/usr/local/nginx/conf/nginx.conf```

### Running
To run the container and bind port 1935 and 5001 to the host machine; run the following:   
```docker run -p 1935:1935 -p 5001:80 -d aweponken/nginx-rtmp```

Check that nginx is running by hitting http://localhost:5001 in a browser.
### OBS Configuration
Under broadcast settings, set the follwing parameters:
```
Streaming Service: Custom
Server: rtmp://<your server ip>/live
Play Path/Stream Key: test
```

### Watching the steam
In your favorite RTMP video player connect to the stream using the URL:
```
rtmp://<your server ip>/live/test
```

## Credits
Big thanks to: 
* [André 'MG' Wisén](http://andrewisen.se/) for helping out with the installation steps. 
* [Jason Rivers](https://github.com/JasonRivers/Docker-nginx-rtmp/) for supplying an awesome GitHub repo.
