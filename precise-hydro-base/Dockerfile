#
# jlowenz/precise-hydro-base build
#
from jlowenz/precise

user root

run echo "deb http://packages.ros.org/ros/ubuntu precise main" > /etc/apt/sources.list.d/ros-latest.list
run wget https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -O - | apt-key add -

run apt-get update
run apt-get install -y ros-hydro-ros-base
run apt-get install -y iputils-ping

run ln -sf /opt/ros/hydro/setup.sh /etc/profile.d/ros_setup.sh

## switch back to the user
user ros
env PATH /bin:/usr/bin:/usr/sbin:/sbin:/usr/local/bin
env ROS_HOME /home/ros/.ros
env ROS_PACKAGE_PATH /home/ros:/opt/ros/hydro/share:/opt/ros/hydro/stacks
ENV PKG_CONFIG_PATH /opt/ros/hydro/lib/pkgconfig
ENV ROS_MASTER_URI http://roscore:11311
ENV ROS_MAVEN_DEPLOYMENT_REPOSITORY /home/ros/devel/share/maven
ENV ROS_MAVEN_PATH /home/ros/devel/share/maven:/opt/ros/hydro/share/maven
ENV ROS_MAVEN_REPOSITORY https://github.com/rosjava/rosjava_mvn_repo/raw/master
ENV ROS_WORKSPACE /home/ros
ENV ROS_HOSTNAME roscore
ENV LD_LIBRARY_PATH /home/ros/devel/lib:/opt/ros/hydro/lib:/usr/lib/jvm/default-java/jre/lib/amd64:/usr/lib/jvm/default-java/jre/lib/amd64/server:/opt/ros/hydro/lib/python2.7/dist-packages
ENV PYTHONPATH /home/ros/devel/lib/python2.7/dist-packages:/opt/ros/hydro/lib/python2.7/dist-packages


expose 11311
cmd ["/bin/bash", "-ilc", "roscore"]
