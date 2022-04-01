# Building-Microservice-Communication-Using-RabbitMQ
Building Microservice Communication with RabbitMQ

# TEAM 6
Sneha Sujit Saha             - PES2UG19CS393\
Sapna Singh                  - PES2UG19CS366\
Sannareddy Vishnu Shruthi    - PES2UG19CS365\
Soumya Shridhar Hedge        - PES2UG19CS401

# INTRODUCTION
The microservice architecture is one of the most popular forms of deployment, especially in larger organisations where there are multiple components that can be loosely coupled together. Not only does this make it easier to work on separate components independently, but ensures that issues in one component does not bring down the rest of the service. A microservices architecture consists of a collection of small, autonomous services where each service is self-contained and should implement a single business capability within a bounded context. This also comes with the advantage that a single system can scale thereby limiting the resources to required components. For example, during a shopping sale, the cart and payment microservices might need more resources than the login microservice. However, one of the issues that comes up with microservices is inter-service communication. There is a need to send messages asynchronously and reliably across services, such that they’re delivered even in case of network delays or one of the services failing to receive it immediately. For this reason, we use messaging queues. A message queue is a form of asynchronous service-to-service communication used in serverless and microservices architectures. Messages are stored on the queue until they are processed and deleted. Each message is processed only once, by a single consumer.

# PRE-REQUISITES

- Docker( Windows | Ubuntu | MacOS )
- RabbitMQ Docker Image
        - https://hub.docker.com/_/rabbitmq\
          It is advised to pull the images into your system before the day of the hackathon\ 
          becaus of the network dependency and other uncertainties.
- Support for language of choice + IDE
While you’re allowed to use any language of choice for the project, ensure there are RabbitMQ Client\ libraries available for your language of choice. We will suggest libraries to use for Python/NodeJS\
to set up different components of the project, but you may use any library to the same effect.

# DELIVERABLES
In this project, we’ll be taking a look at building and deploying a microservice architecture where multiple components communicate with each other using RabbitMQ. Let’s take the example of Uber - the ride-sharing app. When you send a request to book a ride, the system gets your location and tries to match you with riders near your location. Since this is time-consuming, there might be a microservice that tries to do the user-ride matching in the background so that none of the other functionality is tied up for other users. Similarly, there might be a microservice responsible for inserting your ride request into the database. For this project let’s consider 3 microservices - an HTTP server that accepts your requests for a ride, a microservice that tries to calculate the best drivers for the user (we won’t go into actual ride-matching, just simulate the time taken), and a microservice that inserts the data into a database. Moreover, we want the ride-matching microservice to be highly scalable so even if there are a lot of requests, we can just add new containers and they take over (we won’t be automating new containers, but when manually adding new containers, they should be able to connect to the network and accept tasks)
