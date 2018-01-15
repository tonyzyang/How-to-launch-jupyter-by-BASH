# How-to-launch-jupyter-by-BASH
USE MAC terminal/win Bash to launch the jupyter
step 1: Preparation a__
         $ mkdir .ssh a__
         $ ssh-keygen a__
step 2: create the AWS account, using the EC2 platform
		2.1 Set up the KEY PAIR: using the function on BASH $ cat ~/.ssh/id_rsa.pub get the computer ssh
		2.2 Set up security group
			http: range 80
			SSH: range 22 default
			TCP range 27016
			TCP range 2376
		2.3 launch the instance: choose ubuntu, select the security group, select 30G
		2.4 after launching the instance, copy the public IP address
step 3: install docker
		$ ssh ubuntu@(IP address)
                           $ Curl-ssl https://get.docker.com | sh
                           $ sudo usermod -aG docker ubuntu

step 4: set up the Jupyter
	$ docker pull jupyter/datascience-notebook $ docker images (show the information security tocken)
              $ docker pull postgres ------sql database
              $ docker tag jupyter/datascience-notebook dsnb (change the name) $ docker run -v /home/ubuntu:/home/jovyan -p 80:8888 -d dsnb ( -d               hide the process,only show result)
              $docker ps (show the running program) (if want to stop docker, $ docker stop (first 4 letter))

step 5: launch the jupyter
	$ docker exec (first 4 letters) jupyter notebook list ( show the jupyter address and tocken)
	copy the public address into the http, or using the tocken.
