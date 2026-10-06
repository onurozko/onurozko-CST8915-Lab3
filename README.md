# CST8915 - Lab 3
Tahir Onur Ozkoral - 041122154

## Demo Video

[YouTube Demo Video](https://youtu.be/WnMbAyJcSms)

## Service Repositories

- [order-service](https://github.com/onurozko/order-service)
- [product-service](https://github.com/onurozko/product-service)
- [store-front](https://github.com/onurozko/store-front)

## Deployment Note
I couldn't use Azure Static Web Apps because my Azure for Students account was blocked by the new region policy. Since the professor allowed the VM option, I deployed the `store-front` on a VM instead.
The `order-service` and Python version of `product-service` were deployed with Azure App Service. RabbitMQ was deployed on its own VM.

## Reflection Questions

### 1. What challenges did you encounter when configuring environment variables in the GitHub Actions workflow?
I couldn't really complete the Static Web Apps part because of the Azure student account restriction, so I ended up using the VM option allowed by the professor. For the store front, I set the backend URLs as environment variables before building it on the VM. I mainly had to make sure both service URLs were correct before building.

### 2. How does deploying microservices on Azure Web App Service differ from running them locally?
Locally, I had to start the services myself and use localhost. On Azure App Service, the services are hosted for me and can be accessed using public URLs. I also had to configure things like the RabbitMQ connection in Azure instead of only using a local `.env` file.

### 3. Why is it important to use environment variables for configurations in a cloud environment?
Environment variables make it easier to change settings without changing the code every time. Things like URLs, ports, and passwords can be different depending on where the app is running, so it is better than hardcoding them directly in the code.

Also, in my previous positions, there were many times where this allowed another available developer to quickly change a variable and fix someone else's project by following some basic instructions, especially when another team needed a quick change outside normal work hours. So I have also seen their usefulness firsthand in actual work.
