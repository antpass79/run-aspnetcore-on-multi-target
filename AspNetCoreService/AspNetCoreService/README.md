# run-aspnetcore-on-multi-target
Define configuration to run asp net core service across multi target hosts

## How to run on Docker

The project supports the docker container (checking option in the template during creation).

In order to orchestrate more containers, use docker compose command:

- From Visual Studio, select *docker-compose* project and run it.
- From commandline:
	- Navigate to *run-aspnetcore-on-multi-target\AspNetCoreService* folder, where there are docker-compse files.
	- Launch the following commands:

		docker compose build

		docker compose up

## References

### Containers

- <https://medium.com/@__hungrywolf/web-api-and-docker-compose-453f9b824ff9>