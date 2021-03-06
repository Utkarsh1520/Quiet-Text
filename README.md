# Quiet-Text
Quiet Text is a simple, minimalist text editor made with Python's Tkinter GUI library. Quiet Text aims to create a calming and distraction free text environment for writing code and taking notes.

<img src="images/picture_of_app.png" alt="there should be an image here...">

# Goals

- [x] Create a visually pleasing text editor! ;)
- [ ] Add syntax highlighting for Python.
- [ ] Allow user's to launch the terminal and run their scripts from any platform.
- [ ] Add special markdown for making lists and notetaking.
- [ ] Allow full customization of the editor's theme and colors.
- [ ] Add helpful features for programming like autoclosing brackets and parenthesis.

#### suggestions are welcome!

# Installation

This project requires a Python3 interpreter with Tkinter support.
You can test it using

```sh
python3 -m tkinter
```

In case your (GNU/Linux) machine does not support tkinter, there's a way to run it inside Docker (whereas you can also use another base image than `ubuntu`):

```
FROM ubuntu
RUN apt update && apt install -y python3-tk x11-apps
RUN mkdir /code
WORKDIR /code
ADD . /code
CMD ["/usr/bin/python3", "-m", "quiet"]
```

Now, expose an environment variable to allow access to your host system `XAUTH="$HOME/.Xauthority"` and build the image using `docker build -t quiet .`.
You can start a container using

```sh
docker run --network=host --rm -e DISPLAY=$DISPLAY -v $XAUTH:/root/.Xauthority quiet
```

Be aware, that the Docker container has full access to your machine! So you better trust the executed code.

# Contributing Guidelines

* Issues are open to anyone and everyone, but you must comment on the issue first and communicate to me that you are working on it. If you are confident in your ability, I will assign you to the issue. 

* Don't work on an issue that isn't assigned to you unless you communicate with the assignee first. 

* If you make an improvement on an existing feature, make sure to create an issue first and list the fixes or features you have made to the code.

* All PRs must be made from a Branch. Create a separate branch for every Issue you are working upon and once found fit, make a PR.

* Please make sure your code works before you submit it :)

#### check CONTRIBUTING.md for guidlines on how to make a pull request.
