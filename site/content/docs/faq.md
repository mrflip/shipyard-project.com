+++
Categories = []
Description = ""
Tags = [tips]
menu = "main"
title = "FAQ"
date = 2014-08-06T04:37:14Z
+++

# Port Forwarding for Shipyard running in a VM

The docker commands given in the [Shipyard Quickstart](http://shipyard-project.com/docs/quickstart/)
associate the port 8080 on the docker UI container with port 8080 on the docker machine. However, if that docker machine is running as a VM, as any Mac OSX or windows installation will be, you may want to forward that port to its host OS. 

An ad-hoc solution is to use an ssh tunnel: `ssh [YOUR_USER@YOUR_DOCKER_MACHINE_IP] -L 8080:localhost:8080` -- the first number is the port on your host machine, the second is the target port on the docker machine. [Boot2docker](http://boot2docker.io/) users can do this easily by running `boot2docker ssh -L 8080:localhost:8080`. 

Permanent setup of port forwarding is handled by the virtualization layer -- not shipyard or docker -- so you'll have to consult the VM provider documentation. Boot2Docker users can find several ways to accomplish [port forwarding described in the Boot2Docker docs](https://github.com/boot2docker/boot2docker/blob/master/doc/WORKAROUNDS.md).
