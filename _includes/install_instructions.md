
---
# Installation Instructions

## requirements 
- docker version >= 20 *version page citation*
- git version >= 2 *version page citation*

**if you do not have docker or git installed, please visit the following links to download and install them:**
- [docker installation page](https://docs.docker.com/get-docker/)
- [git installation page](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

## installation steps 
-1. open a terminal window (Ctrl + Alt + T on Linux, Command Prompt or Powershell on Windows)
-2. navigate to the directory you want to clone the repository to using the `cd` command
-3. run the following command to clone the repository:
```
git clone https://github.com/AnthonyEllis06/EnchantedBeautyBar
```
-4. navigate to the cloned repository directory using the `cd` command:
```
cd EnchantedBeautyBar
```
-5. build the docker image using the following command:
```
//to run in detached mode, add the -d flag
docker compose up
//to run in detached mode, add the -d flag
```
-6. once the container is built and running, you can access the web application by opening a web browser and navigating to `http://localhost:8000`
    Note: navigate to 'localhost:4000/admin' to access the admin panel
-7. to stop the docker container, run the following command in the terminal window:
```
docker compose down
```

## Additional Notes 
- Default login credentials for the admin page are:
    - username: admin
    - password: adminpassword
