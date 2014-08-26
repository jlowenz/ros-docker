#
# jlowenz/precise build
#
from ubuntu:12.04

# prepare system with basic needs
run apt-get update
run apt-get install -y wget apt-utils python-software-properties

run apt-get install -y screen byobu
run apt-get install -y vim sudo iputils-ping
run chmod 777 /var/run/screen
run byobu-select-backend screen
env SHELL /bin/bash
add .screenrc /.screenrc
#add fix-console.sh /etc/profile.d/fix-console.sh

# create a ros user
run useradd -m -d /home/ros -s /bin/bash -G sudo,adm,tty -g users ros
run echo "ros:r0s0r" | chpasswd


workdir /home/ros
user ros
add .screenrc /home/ros/.screenrc

cmd /bin/bash -il
