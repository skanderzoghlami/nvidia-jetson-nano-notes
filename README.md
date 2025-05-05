# nvidia-jetson-nano-notes
Those are my notes after following the "Getting Started with AI on Jetson Nano" From Nvidia DLI

# Hardware Gibberish
- The board has 40 pins to connect to General purpose Input / Output or like enrds want to call it GPIO (Those will be connected to stuff like sensors motors diods etc..), Python libraries can be used to itneract with them.
- 4 usb ports + HDMI to facilitate interfacing with the board.
- Power can be given through USB type C or Barreljack depending on how consuming our board will be (more devices connected = more hunger for electricity).

Check The videos for more details about hardware configuration and how to flush your first image.
Check out a short video for Jetson Nano [here](https://youtu.be/uvU8AXY1170).
Check out a short video for Jetson Orin [here](https://youtu.be/VWdJ4BCtam8).

# Furst Steps
- First thing to do is to download an image from the jetpack sdk, think of it as downloading an OS for your new computer, the image is around 6GB and the version is very important, you'll need it for docker later on.
- To flush the image you need two things the formatted and Etcher.
- Make Swap bigger.
# Connecting to the board:
- First we ssh into it, very easy, we also create a data package that will persist into it.
- Second we start a docker container and connect the data folder of the container to the data container that we created earlier.
- when the docker container start we can use the notebooks that exist there to use cameras etc...