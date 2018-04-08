
<a href="https://www.docker.com">
  <img src="https://stapp.space/content/images/2016/05/docker_header1.png" alt="Docker on Windows logo" style="width:42px;height:42px;">
</a> 

<h1>Docker running GUI Applications on Windows</h1>

<div>
    <a href="https://github.com/NaPiZip/Docker_GUI_Apps_on_Windows">
        <img src="https://img.shields.io/badge/Document%20Version-1.0.0-brightgreen.svg"/>
    </a>
    <a href="https://www.docker.com">
        <img src="https://img.shields.io/badge/Docker-17.05.0--ce-blue.svg"/>
    </a>
    <a href="http://x.cygwin.com">
        <img src="https://img.shields.io/badge/Cygwin%2FX-7.7-blue.svg"/>
    </a> 
 </div>
<br/>
<div>    
This is a tutorial showing how to run graphical user interface applications
inside a Docker container on a Windows 10 host system using Cygwin/X.

The following programs are needed for the installation:
<ul>
    <li>
        <a href="https://x.cygwin.com">Cygwin/X</a>
    </li>
    <li>
        <a href="https://www.docker.com">Docker</a> (Docker is assumed to be installed and working correctly)
    </li>
<ul/>
</div>

<h2>Installation</h2>
<div>
  <ol>
    <li>Follow the instruction accordingly to this <a href=https://x.cygwin.com/docs/ug/setup.html#setup-cygwin-x-installing>link<a/>.
    </li>
    <li>Make sure to install the following packages:</li>
    <ul>
      <li>xorg-server (required, the Cygwin/X X Server)</li>
      <li>xorg-docs (optional, man pages)</li>
      <li>xlaunch (optional, a wizard for starting X sessions)</li>
    </ul>
</div>

<h2>Tutorial</h2>
<div>
  <ul>
    <li>Start a Cygwin terminal and run `XWin :0 -listen tcp -multiwindow`<li/>
    This will start an X server on Windows machine on your local machine.
    <li>Start docker and run  `docker run -ti --rm -e DISPLAY=$DISPLAY:0.0 firefox`<li/>
    This will run a container call firefox the Dockerfile is listed below:

```
FROM ubuntu:14.04

RUN apt-get update && apt-get install -y firefox

# Replace 1000 with your user / group id
RUN export uid=1000 gid=1000 && \
    mkdir -p /home/developer && \
    echo "developer:x:${uid}:${gid}:Developer,,,:/home/developer:/bin/bash" >> /etc/passwd && \
    echo "developer:x:${uid}:" >> /etc/group && \
    echo "developer ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/developer && \
    chmod 0440 /etc/sudoers.d/developer && \
    chown ${uid}:${gid} -R /home/developer

    USER developer
    ENV HOME /home/developer
    CMD /usr/bin/firefox
```


Thanks to <a href="https://jarekprzygodzki.wordpress.com/2016/07/11/running-linux-graphical-applications-in-docker-on-windows-with-cygwinx/">Jarek Przygódzki. Blog programisty<a/>.
</div>


<h2>Contributing</h2>

<div>
To get started with contributing to mu GitHub repo, pleas contact me <a href="https://slack.com/">Slack<a/>.
</div>
