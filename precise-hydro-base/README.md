precise-hydro-base
==========

This image will run a `roscore` process by default, and exposes port 11311. It should be run with the following command, to make sure the hostname is specified properly:

    docker run --name roscore -h roscore -it jlowenz/precise-hydro-base
