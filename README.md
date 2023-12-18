# Cloud-Native Microservices E-Commerce App Deployment Using Google Kubernetes Engine (GKE), Google Container Registry (GCR) &amp; Skaffold on Google Cloud Platform

![picture with the words Cloud Project and icons for the services used](https://miro.medium.com/v2/resize:fit:720/format:webp/0*MUoMFwKvaXDGaRo7.jpg)

In this project based on a real-world scenario I was assigned a role as a DevOps Engineer to migrate an e-commerce app from a monolithic architecture to a cloud-native
microservices architecture.

Since the company has a MultiCloud Strategy, the prototype of this cloud-native microservices application had to be created in three different cloud providers 
(AWS, Microsoft Azure and Google Cloud Platform), so they could evaluate which one would be used as future Kubernetes managed service.

Besides, I was also requested to build and host the Docker images in the Cloud provider Registry. For practical purposes, the implementation was made on Google Cloud.

![picture with a graph showing the solution architecture](https://miro.medium.com/v2/resize:fit:720/format:webp/0*beyjTJRmRA3iDYnd.jpg)

Initially I certified myself that I had Google Cloud APIs turned on. After that, I’ve created the cluster that would host the microservices deployments. 
With the cluster created, I’ve downloaded the app’s files on CloudShell, including the YAML files with the image build instructions. 
I made a light edit to the footer app, to add my name on it as part of the assignment.

The image build, push and deploy to Google Container Registry were all made by Skaffold, which uses a YAML files for instructions too. The process
was a little bit long, since it was a lot of micro-services being build, pushed to GCR and deployed. With the services online, I gave a last look
at the firewall rules, and soon the front-end was available trough the Load Balancer. To validate the stability of the platform, I’ve changed the
scale value from the checkout services to 0, which basically eliminates it. All the other services were still online, thanks to the micro-services
architecture, which allows the various services to work together, without taking each other down in case of failure.

![Google Cloud shell running Skaffold](https://miro.medium.com/v2/resize:fit:720/format:webp/0*hnMOD3n98qLrXbR-.png)

![picture of a online webshob on a browser window](https://miro.medium.com/v2/resize:fit:720/format:webp/0*AjVtcFmkqnBWDmYS.png)

I was already surprised by Docker, but studying Kubernetes made me realize how powerful is container technology allied with a
good orchestrator. And Skaffold it’s a terrific tool for deployment, automating a good part of the process
so devs and engineers can focus more on code.
