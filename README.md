# Deploying FastAPI python application on Azure

This is a sample project to demonstrate how to deploy a FastAPI application on Azure.

## Steps to build a docker image

```bash
docker build -t <your-registry-name>.azurecr.io/fastapi-app:latest .
```
## Steps to run docker image locally

```bash
docker run -d -p 80:80 <your-registry-name>.azurecr.io/fastapi-app:latest
```

On a browser, navigate to http://localhost:80

## Steps to push docker image to Azure Container Registry

Assuming, ACR is already created on Azure.

```bash
az login

az acr login --name <your-user-name>

docker push <your-registry-name>.azurecr.io/fastapi-app:latest
```

## Steps to deploy docker image on Azure Container Instances

Follow this [article](https://learn.microsoft.com/en-us/azure/container-instances/container-instances-quickstart-portal).

### Note

If you are thinking on giving custom domain then please follow this question on stackoverflow [here](https://stackoverflow.com/questions/56435852/how-to-set-up-custom-domain-name-in-azure-container-instance).

You will need to add CNAME record in your DNS provider.

## Resources

- https://fastapi.tiangolo.com/deployment/docker/
- https://learn.microsoft.com/en-us/azure/container-instances/container-instances-quickstart-portal
