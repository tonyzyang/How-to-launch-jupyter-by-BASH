
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
	
![My image](https://github.com/tonyzyang/How-to-launch-jupyter-by-BASH/blob/master/How%20to%20launch%20the%20Jupyter.png)

![My image](https://github.com/tonyzyang/How-to-launch-jupyter-by-BASH/blob/master/cost%20for%20jupyter%20driver.png)
A detailed budget of the costs of running a Jupyter Data Science Notebook Server for three months using at least three different kinds of EC 2 instances.<br />
https://aws.amazon.com/marketplace/pp/B00JV9JBDS <br />
Assuming every month we use 300 hours, so the Budget <br />
if we use the ubuntu t1.micro 0.02/hour, the price for 3 months would be 900hours * 0.02=18 dollar<br />
if we use the ubuntu m1.small $0.044/hour, the price for 3 months would be 900hours * 0.044=39.6 dollar<br />
if we use the ubuntu m1.medium $0.087/hour, the price for 3 months would be 900hours * 0.087=78.3 dollar<br />
if we use the ubuntu c1.medium $0.130/hour, the price for 3 months would be 900hours * 0.13=117 dollar<br />
