# WIP : These are the API Gateways that will be analysed 


## What is an API gateway?
<br/>

An API gateway is an API management tool that sits between clients and the backend services they need to access. The API gateway acts as a reverse proxy, accepting all application programming interface (API) calls, aggregating the services required to execute the calls, and returning the appropriate results to the clients.

<br/>


An API gateway is a way of decoupling the client interface from the backend implementation. When a client makes a request, an API gateway splits it into multiple requests, routes them to the appropriate location, generates a response, and keeps track of everything.

<br/>


API gateways typically handle common system-wide tasks for API services such as user authentication, rate limiting, and statistics. The challenge is to overcome the complexity of enterprise APIs and provide a simple and reliable experience for customers. 

<br/>


With adoption of Kubernetes containers and cloud native architectures for modern applications, technologies like the open source Envoy Proxy and Istio have emerged to enable application networking for distributed systems. Envoy has become the most popular proxy at the edge, and also as the sidecar to handle internal traffic in an Istio service mesh.

<br/>
<br/>

## Kong

## Traefik

Definition found in the traefik.io

What is an API Gateway?
An API gateway sits between your backend services and API clients. It processes API requests, at scale, validates them, adds authentication and authorization, applies rate limiting, and routes them to the proper backend.

API gateways are becoming increasingly popular as a way to decouple the client and server components of an application. This separation of concerns allows developers to update and maintain their backend services without affecting the client-side code. API gateways also enable developers to scale their services independently, making it easier to handle high traffic levels.


## HAProxy

## Nginx

## Amazon api gateway

- [Integrate Amazon API Gateway with Amazon EKS] (https://aws.amazon.com/blogs/containers/integrate-amazon-api-gateway-with-amazon-eks/)

## Decision
    Final decision about the API that I will use for my PoC


