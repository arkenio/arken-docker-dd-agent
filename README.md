Arken Datadog docker agent
==========================

This docker image uses the default [DataDog docker agent](https://github.com/DataDog/docker-dd-agent) and configures it to monitor the host and the docker containers


How to run
----------

We have to share mount the `/var/run/` directory to the Docker container so that the agent know how to monitor docker

Just run

	docker run -d --privileged --name dd-agent -h `hostname` -e API_KEY=<<datadog_api_key>> -v /var/run/:/host/var/run/:ro arken/docker-dd-agent


