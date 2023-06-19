# General Notes

The project is for Jenkins pipeline works testing

## Running project

Tp create docker network ngrok enter the following command:

```console
docker network create ngrok
```

To run Jenkins, open console and enter the following command:

```console
docker run -d --rm -p 8080:8080 -p 50000:50000 \
--mount type=bind,source=$SSH_AUTH_SOCK,target=/ssh-agent \
--env SSH_AUTH_SOCK=/ssh-agent \
--name c-jenkins \
-v ~/Documents/docker/jenkins-test:/var/jenkins_home \
-v ~/.ssh:/var/jenkins_home/.ssh \
jenkins/jenkins
```

To add env variable $AUTH_TOKEN to the current session enter the following command:

```console
export AUTH_TOKEN="<ngrok_auth_token>"
```

To run Ngrok, open console and enter the following command:

```console
docker run --net=host -it ngrok/ngrok http 8080 --host-header=rewrite --authtoken <auth_token>
```

To check external URL, open console and enter the following command:

```console
ngrok http 8080
```

Use the value `forwarding`
