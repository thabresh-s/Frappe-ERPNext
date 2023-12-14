# Project PWD Docker Compose Setup

## Step 1: Docker Compose File for the PWD Project from Github

Download the Docker Compose file (`pwd.yaml`) from the [PWD Project on Github](<link-to-your-github-repo>).

- [Raw File of PWD.Yaml](https://raw.githubusercontent.com/frappe/frappe_docker/main/pwd.yml)
- [PWD.YML File on Github](https://github.com/frappe/frappe_docker/blob/main/pwd.yml)

## Step 2: Organize Your Files

Store the `pwd.yaml` file on your computer. For this tutorial, we recommend the following folder structure:

```
C:\Data\Docker\Frappe\pwd.yaml
```

The `pwd.yaml` file is stored in the above location. This Docker Compose file contains all the necessary configurations for images, containers, and volumes that ERPNext will use in a Docker environment. You generally don't need to make any changes to it.

## Step 3: Execute the Plan

Using the Docker Compose command, navigate to your folder and run:

```bash
docker-compose -p pwd -f pwd.yaml up -d
```

Explanation of the command:
- `docker-compose` is the command for Docker Compose.
- `-p` specifies the project name (`pwd` in this case).
- `-f` specifies the file name (`pwd.yaml`).
- `up` means the containers will be created and started.
- `-d` runs the containers in detached mode.

This command will download images, create volumes, containers, and start the containers.

## Step 4: Validate the Containers

Check the list of containers created. Ensure that `create-site-1` is available. Capture the logs of this container to monitor for any issues:

```bash
docker logs pwd-create-site-1 -f
```

This container is crucial as it contains the site of the Docker setup.

## Step 5: Verification Time

Access ERPNext using the following link:

[http://localhost:8080](http://localhost:8080)

This will initiate the ERPNext configuration wizard.

If you want to ensure that all containers are running (especially in Linux), you can use the following command:

```bash
docker ps
```

## Step 6: Explore ERPNext 15

Open your browser and go to [localhost:8080](http://localhost:8080). ERP Next version 15 is now ready for setup. Use `administrator/admin` to log in and choose your chart of accounts.
```

Feel free to replace `<link-to-your-github-repo>`, `<link-to-raw-pwd.yaml>`, and `<link-to-pwd.yml>` with the actual links to your GitHub repository and raw YAML files.