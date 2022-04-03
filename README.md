# LearningModernDataStack

Learning tools and technologies in the modern data stack. 
We will be exploring the below mentioned tools/technologies

# Data Stack

- Google cloud (VM)
- Docker (containers)
- Python for general programming
- Airbyte (data ingestion)
- Snowflake (datawarehouse)
- DBT (transformations)
- SQL (data manipulation)
- Tableau (data visualization)
- Jenkins (CI/CD principles)
- Github

# High Level Project Plan

-Setting up Google Cloud VM
- Containerization with Docker
    - Miniconda
    - Postgres
    - Pgadmin
    - Python
    - Metabase
    - Snowflake connector
    - Airbyte
    - DBT
- Data Ingestion using Airbyte and Python
- Data Modeling (dbdiagrams.io)
- Transformation with DBT
- Setup CI/CD process
- Answer business questions with Metabase

# Section 1 - Setting up Google Cloud

- Go to https://cloud.google.com/ and set up a new account with free trial
- Once you're in, start a new project and create a VM.
    - Go to create new project and give it a suitable name. (The name cannot be changed later)
    - Under the navigation menu, select Compute Engine -> Virtual Instances and select your project under the dropdown.
    - Enable the Compute Engine API. 
    - I configured the VM with the following settings : Region: us-east4, Zone: c, OS: Ubuntu 20.04 LTS, Balanced persistent disk, 30 GB and rest are the default settings
    - Go to this link https://cloud.google.com/compute/docs/connect/create-ssh-keys#linux-and-macos to create ssh keys
    - Add ssh keys to google cloud by going to Compute Engine -> Metadata. Copy the generated public key from the ssh folder and add it.
    - Type `ssh -i ~/.ssh/gcp Username@ExternalIP` in the terminal to access google cloud.
    - If you want you can create a config file for the same  
				 `Host instance_name`    
					`HostName ExternalIP`   
					`User localuser on laptop`  
					`IdentityFile file path to private key under ssh`  
		
# Section 2 - Installing and Setting up Docker and Docker Compose

- Go to https://docs.docker.com/engine/install/ and install the docker version that suits your system.
- If you are installing Docker Desktop on Windows, make sure to select the 'Install required WSL2 components' when prompted and follow the intallation wizard. Here I intsalled the Docker Desktop 4.6.1 version.
- Windows will log you out after this. Accept the terms and conditions when prompted and you are all set
- Basic steps of docker - Clone a repository that will have the docker image, Build that image, Run your container
- Sign up on Docker hub if you haven't already. https://hub.docker.com/signup and sign in.

PS: You will require git bash for this. I had it installed already.

# Section 3 - Start the docker container

- Run the following commands in git bash
				 `git clone https://github.com/josephmachado/online_store.git`    
					`cd online_store`   
					`make up`  
					`docker ps`  

(If the make up command does not run. Run `cat Makefile` in the online_store folder and copy the command for up and run it outside. Mine was `docker compose up --build -d`)
