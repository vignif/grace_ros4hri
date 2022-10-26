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
```

Create a local python environment (good practice!)

```bash
python3 -m venv venv_grace
source venv_grace/bin/activate
```

Install the dependency of grace
```bash
pip install --upgrade pip
wget https://github.com/vignif/grace/releases/download/v1.0.0/grace-1.0.0-py3-none-any.whl
pip install grace-1.0.0-py3-none-any.whl
pip install wheel empy catkin_pkg rospkg PySide2
```

Build the ros package

```bash
cd ~/ros_ws
catkin build
```

