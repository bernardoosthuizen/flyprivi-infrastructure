# Fly Privi's Infrustructure
This short document describes the architecture for [Fly Privi](https://flyprivi.com/). I update this document whenever I make a change in production based on new best practices I learnt or a new service I want to try out. Fly Privi is a project I am using to experiment with and explore interesting technologies. 

## Overview

![download](https://github.com/user-attachments/assets/5cd8b086-ffd5-44a3-8865-0ca0fd4cd616)


## Thoughts :thinking:

### Load balancing
This is the first project that I am exploring load balancing. Firebase hosting provides built-in CDN and load balancing, but I have implemented load balancing for the API as well. Traffic is routed based on the user's location, their traffic is directed to the nearest backend region. Regions were chosen based on the concentration of existing users. 

### Databases
Having different regions means that data lives in multiple locations. Flight information is the only data replicated across regions. This data is replicated from the European region. User data is not replicated since it is accessed not as frequently and is not a lot of data.

### IaC
This is also the first project that I am exploring Infrastructure as Code (IaC). Terraform was used to deploy this app. 


