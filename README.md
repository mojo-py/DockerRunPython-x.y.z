# $ docker run -it --rm python:3.2.1
## How to use Docker to install and run any Python version including Python 2 up to the newest Release Candidate (RC)
### Motivation
Let's imagine the problem facing a Python developer prefering to use Python 3.7.9 in order to replicate a clients' environment, or a student needing to utilize Python 3.6.2 to complete an assignment. These are just two of many scenarios in which 'downgrading' is something the developer actually wants to do, albeit temporarily. 

There are many ways to do this, most of which entail even more problems than downgrading python might solve, so it is really like trading one problem for another. Many of the orthodox approaches to this problem involve changing the system $PATH, and/lor downloading Gzipped source tarball or XZ compressed source tarballs. Then the next thing you know, valuable time is wasted Googling which tarball to use instead of time spent developing. According to the Zen of Python, There should be one— and preferably only one —obvious way to do it.

In the spirit of that sentiment, the Docker approach provides the simplest and most risk-free solution to the problem. The Python developer does not need to worry about the way it is orchestrated behind the scenes. Essentially, what is happening is Docker is allowing us to invoke an isolated image containing a specific version of Python, and that image is quarantined from the rest of our operating system. Beyond that, the subject of containerization and docker installation are outside the scope of this simple demonstration. Before proceeding further, please understand that it is assumed you should have a Linux operating system with Docker installed already at this point.

```$ docker run -it python*:<major>.<minor>.<micro>*```

Docker will start a Python session in the specified version immediately, but if we don't have it, Docker will recognize this and download the image for us which could take about a minute.

 and I will do this by simply typing in - >

```$ docker run -it python:2.7.9```

```
Python 3.7.9 (default, Feb  9 2021, 08:33:04) 
[GCC 8.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
```

Perfect. I had that installed already and it was trivially easy. What if I need to go all the way back to Python 2.7 but I have never downloaded Python 2 because I learned Python after Python 3 came out?


```$ docker run -it python:2.7```

```
Unable to find image 'python:2.7' locally
2.7: Pulling from library/python
7e2b2a5af8f6: Downloading  507.1kB/50.38MB
09b6f03ffac4: Downloading  1.403MB/7.812MB
dc3f0c679f0f: Downloading  1.342MB/9.996MB
fd4b47407fc3: Waiting 
b32f6bf7d96d: Waiting 
6f4489a7e4cf: Waiting 
af4b99ad9ef0: Waiting 
39db0bc48c26: Waiting 
acb4a89489fc: Waiting 
```
Since we did not specify a micro version in the major.minor.micro python versioning paradigm introduced in PEP 440, Docker defaults to providing us with the most recent version of the image available, which happens to be 2.7.18


Enjoy the stability of replicating a perfect copy of a previous version of Python, or even try out the newest Release Candidate (RC) before it is released to the general public. Creating an isolated image separate from the rest of your operating system is the exact type of problem Docker is good at solving, as well as the most secure and low risk.

Your downloaded image is installed and you are now in a Python 2 time machine!

```
2.7: Pulling from library/python
7e2b2a5af8f6: Pull complete 
...
...
acb4a89489fc: Pull complete 
Digest: sha256:cfa62318c459b1fde9e0841c619906d15ada5910d625176e24bf692cf8a2601d
Status: Downloaded newer image for python:2.7
Python 2.7.18 (default, Apr 20 2020, 19:27:10) 
[GCC 8.3.0] on linux2
Type "help", "copyright", "credits" or "license" for more information.
```
