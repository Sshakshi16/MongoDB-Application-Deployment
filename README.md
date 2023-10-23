# MongoDB-Application-Deployment
Complete Application Deployment using Kubernetes Components


1. **MongoDB Pod Creation**:
   - We start by creating a MongoDB pod. However, we want to restrict access to this pod to components within the same cluster. External requests are not allowed.

2. **Internal Service Creation**:
   - To enable communication with the MongoDB pod, we create an internal service. This service ensures that only components within the same cluster can access the MongoDB pod.

3. **Express Deployment Setup**:
   - Next, we set up an Express deployment. For Express to connect to the MongoDB database, we need two essential pieces of information:
     - The database URL.
     - Credentials (username and password) for database authentication.
   - We pass these details to the Express deployment through its configuration file using environmental variables. This configuration process helps us set up and configure the application.

4. **Configuration Data with Config Map and Secret**:
   - To achieve this configuration, we create a config map that stores the database URL and a secret that securely stores the database credentials. Both the config map and secret are referenced in the deployment configuration file for Express.

5. **External Service Creation**:
   - Finally, to make the Express application accessible from a web browser, we create an external service. This service allows external requests to reach the Express pod. Users can access the application via a URL like http://IP_address_of_the_node:service_port.

In summary, this process involves creating a MongoDB pod, securing it with an internal service, configuring an Express deployment with database information, and allowing external access through an external service. This setup ensures a secure and well-configured application within the Kubernetes cluster while enabling external access to the Express application.
