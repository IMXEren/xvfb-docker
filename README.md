## xvfb-docker

Two flavours: Xvfb (headless X) and Xvfb + x11vnc (remote accessible).

### xvfb

```
docker build -f xvfb/Dockerfile -t xvfb xvfb
docker run -d --name xvfb xvfb
```

Env vars (all optional, shown with defaults):

```
DISPLAY=:0
GEOMETRY=1920x1080x24
XVFB_ARGS=-ac -listen tcp
```

### xvnc

```
docker build -f xvnc/Dockerfile -t xvnc xvnc
docker run -d --name xvnc -p 5900:5900 xvnc
```

Env vars:

```
DISPLAY=:0
GEOMETRY=1920x1080x24
VNC_PORT=5900
XVFB_ARGS=-ac -listen tcp
X11VNC_ARGS=-forever -shared -nopw
```

Connect with any VNC client on the port you picked.
