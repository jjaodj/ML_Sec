# How to Run to Create Docker Virtual Network

This guide provides steps to create a Docker virtual network with CVE configurations using Dockerfiles, Ansible, and Python.

## Step 1: Create Dockerfile

To generate the Dockerfile with CVE configurations, run the following Ansible playbook:

```bash
ansible-playbook generate_docker.yml
```

- The Dockerfiles will be created in the `/dockerfiles` folder.
- You can add more CVEs to the `cve_config.yml` file as needed.

## Step 2: Build Docker Images

Once the Dockerfile is created, build the Docker image by running:

```bash
docker build -f `Name_Dockerfile` -t `Name_image` .
```

Replace `Name_Dockerfile` with the name of your generated Dockerfile and `Name_image` with the desired name for the Docker image.

## Step 3: Define Container with CVE in `input.json`

Create an `input.json` file to define the container that will have the CVE you want to test or use sample json. Specify the container details and configurations within this file.

## Step 4: Create Virtual Network

To set up the Docker virtual network, run the following Python script:

```bash
python3 `OVS_Code.py`
```

This will create a virtual network in Docker and connect the containers as defined.
