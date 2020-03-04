# DataRepository
Additional data that is required by some components or systems. For example, it includes environments for simulators (e.g. for use with Gazebo and PlayerStage simulators).

This repository is maintained by Servicerobotik Ulm. For more information see:

* Big picture: relation of repositories: https://wiki.servicerobotik-ulm.de/download
* SRRC Technical Wiki on SmartSoft and SmartMDSD Toolchain: https://wiki.servicerobotik-ulm.de

# Gazebo9 Set Up
* Install Gazebo 9, as in http://gazebosim.org/tutorials?cat=install&tut=install_ubuntu&ver=9.0 step by step:

1) ```sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-stable.list'```
2) ```wget http://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -```
3) ```sudo apt-get update```
4) ```sudo apt-get install gazebo9```
5) ```sudo apt-get install libgazebo9-dev```

* Check installation with:
```
gazebo
```
* Verify if file setup.sh exists:
```
cat /usr/share/gazebo/setup.sh
```
If you see something like this in the terminal, you are fine:
```
export GAZEBO_MASTER_URI=http://localhost:11345
export GAZEBO_MODEL_DATABASE_URI=http://models.gazebosim.org
export GAZEBO_RESOURCE_PATH=/usr/share/gazebo-9:${GAZEBO_RESOURCE_PATH}
export GAZEBO_PLUGIN_PATH=/usr/lib/x86_64-linux-gnu/gazebo-9/plugins:${GAZEBO_PLUGIN_PATH}
export GAZEBO_MODEL_PATH=/usr/share/gazebo-9/models:${GAZEBO_MODEL_PATH}
export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:/usr/lib/x86_64-linux-gnu/gazebo-9/plugins
export OGRE_RESOURCE_PATH=/usr/lib/x86_64-linux-gnu/OGRE-1.9.0
```
Otherwise, create the setup.sh file above in the path ```/usr/share/gazebo/setup.sh``` (correct paths if necessary).

# Webots Set Up
* Install Webots from sources
1) ```mkdir ~/dev && cd ~/dev```
2) ```git clone --recurse-submodules git@github.com:cyberbotics/webots.git```
3) ```cd webots```
4) ```make```
* Create an environment variable for webots' path
```
cat >> ~/.profile <<x
export WEBOTS_HOME=$HOME/dev/webots   
x
```
(obs.: if you install webots with a binary file, you must configure WEBOTS_HOME with the right path, which might be ```/usr/share/webots``` or ```/usr/local/webots```)
