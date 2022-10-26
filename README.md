# grace_ros4hri

Integrate grace with ros4hri

Python library of [grace](https://github.com/vignif/grace)

Create your ros workspace
```bash
mkdir ~/ros_ws
cd ~/ros_ws
```

Clone the current repository in the folder `src`

```bash
git clone --recurse-submodules git@github.com:vignif/grace_ros4hri.git src
git submodule update --remote
```

Create a local python environment (good practice!)

```bash
python3 -m venv venv_grace
source venv_grace/bin/activate
```

Install dependencies of grace
```bash
pip install --upgrade pip
wget https://github.com/vignif/grace/releases/download/v1.0.0/grace-1.0.0-py3-none-any.whl
pip install grace-1.0.0-py3-none-any.whl
pip install wheel empy catkin_pkg rospkg PySide2 numpy
```

Install dependencies of hri_face_detect
```bash
cd hri_face_detect
python setup.py install
pip install mediapipe
```

Build the ros package
```bash
cd ~/ros_ws
catkin build
```


### How to run

Source the recently build binaries

```bash
source ~/ros_ws/devel/setup.sh
```

Install the package to get stream from vision sensor (usb_cam or other)
i.e. use webcam of your laptop

```bash
sudo apt-get install ros-noetic-usb-cam
```

Launch grace with:
Param setting
```bash
which_cam:={usb_cam (default) | realsense}
```

Example
```bash
roslaunch grace_ros run_grace.launch which_cam:=realsense
```