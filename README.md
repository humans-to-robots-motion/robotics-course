# MLR robotics course

This repo is based on RAI code, including its python bindings. See https://github.com/MarcToussaint/rai for a README of the RAI code.

## Quick Start

This assumes a standard Ubuntu 16.04 machine.

WE DIDN'T GET TO RUN THIS WITH ANACONDA PYTHON. If you have Anaconda
installed, please remove it from the PATH in .bashrc. The setup below will
install the standard Ubuntu python3 and jupyter notebook.

In the ROBOTICS PRACTICAL course (where we use ROS), change 'ROS = 0' to '#ROS = 0' in 'config.mk' before compilation.

```
git clone https://github.com/MarcToussaint/robotics-course.git
cd robotics-course

git submodule init
git submodule update

make -j1 initUbuntuPackages  # calls sudo apt-get install; you can always interrupt
make -j4                     # builds libs and tests

source setupPython.sh

python3 -m pip install --upgrade pip
python3 -m pip install jupyter
python3 -m pip install matplotlib

jupyter-notebook docs/1-basics.ipynb 
```
After loading the pr2 and the kitchen (running first 3 cells in the notebook), the simulator window should look similar to:
![Alt text](screenshot.png?raw=true "Title")

## Updating after a pulling a new version

```
git submodule update
make -C rai dependAll
make -j4
```


## Tutorials
[Basics:](docs/1-basics.ipynb) Configurations, Features & Jacobians




