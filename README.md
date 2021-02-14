**MODULE DOCKER-COMPOSE (Compose Configuration)**
QA-Learning

**Trio Task**

The instructions were: 

Clone down this [repository](https://gitlab.com/qacdevops/trio-task) and write a docker-compose.yaml file to deploy the Flask application, database and NGINX container with Docker Compose.

> >  **Option1: Bind mount:   1 file: nginx.config**

![](https://trello-attachments.s3.amazonaws.com/60282250a94b5e6ea9ecb302/602830f1c20ac22a90891451/ecb8c893477319c28ace5b9d066f9b7b/B_Nginx_ok.png)



# HOW TO RUN THIS EXERCISE 

1. Fork this repository 
2. Clone the repository in your VM 
3. Make sure docker & docker-compose are installed **(if not, see next section).**  
3. Go to inside the folder "Matata_TrioTask", **where the docker-compose.yaml file is.** 
4. Run 

	`docker-compose up -d`
5. See the results with curl  

	`curl localhost`

6. Clean up 

	`docker-compose down --rmi all`


---

# **Installation Docker-Compose from 0.**

(New Virtual Machine) 

**Run**

`sudo su - `

**Installation DOCKER**

`apt update && apt upgrade -y && apt install -y docker.io  `

or 

`apt update`  
`apt upgrade -y`  
`apt install -y docker.io`

**Installation DOCKER-COMPOSE**

1. Make sure jq & curl are installed

	`apt install -y curl jq`

2. Set which version to download (latest)

	`version=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | jq -r 	'.tag_name')`

3.  Download to /usr/local/bin/docker-compose

	`curl -L "https://github.com/docker/compose/releases/download/${version}/docker-	compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
`
4. Make the file executable

	`chmod +x /usr/local/bin/docker-compose`


5. Check if it is installed 
	
	`docker-compose --version`
	
----
