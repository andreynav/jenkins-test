# General Notes

The project is for Jenkins pipeline works testing.

## Running project

To run Jenkins, open console and enter the following command:

```console
docker run -d --rm -p 8080:8080 -p 50000:50000 \                                                 ─╯
--mount type=bind,source=$SSH_AUTH_SOCK,target=/ssh-agent \
--env SSH_AUTH_SOCK=/ssh-agent \
--name c-jenkins \
-v ~/Documents/docker/jenkins-test:/var/jenkins_home \
-v ~/.ssh:/var/jenkins_home/.ssh \
jenkins/jenkins
```

To run Ngrok, open console and enter the following command:

```console
docker run -d --rm --name c-ngrok --link c-jenkins:jenkins -p 4040:4040 ngrok/ngrok http host.docker.internal:8080
```

To enter the Ngrok, open console and enter the following command:

```console
docker exec -it c-ngrok /bin/bash
```

To check external URL, open console and enter the following command:

```console
ngrok http 8080
```

Use the value `forwarding`
