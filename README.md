# How-to-launch-jupyter-by-BASH
USE MAC terminal/win Bash to launch the jupyter <br />
step 1: Preparation <br />
         $ mkdir .ssh <br />
         $ ssh-keygen <br />
	 
step 2: create the AWS account, using the EC2 platform<br />
		2.1 Set up the KEY PAIR: using the function on BASH $ cat ~/.ssh/id_rsa.pub get the computer ssh<br />
		2.2 Set up security group<br />
			http: range 80<br />
			SSH: range 22 default<br />
			TCP range 27016<br />
			TCP range 2376<br />
		2.3 launch the instance: choose ubuntu, select the security group, select 30G<br />
		2.4 after launching the instance, copy the public IP address<br />
step 3: install docker<br />
		$ ssh ubuntu@(IP address)<br />
                           $ Curl-ssl https://get.docker.com | sh<br />
                           $ sudo usermod -aG docker ubuntu<br />

step 4: set up the Jupyter<br />
	$ docker pull jupyter/datascience-notebook $ docker images (show the information security tocken)<br />
              $ docker pull postgres ------sql database<br />
              $ docker tag jupyter/datascience-notebook dsnb (change the name) $ docker run -v /home/ubuntu:/home/jovyan -p 80:8888 -d dsnb ( -d               hide the process,only show result)<br />
              $docker ps (show the running program) (if want to stop docker, $ docker stop (first 4 letter))<br />

step 5: launch the jupyter<br />
	$ docker exec (first 4 letters) jupyter notebook list ( show the jupyter address and tocken)<br />
	copy the public address into the http, or using the tocken.<br />
