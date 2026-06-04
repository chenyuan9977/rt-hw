# HW6: System Architecture Fundamentals

### 1. Client-Server Model
This architecture functions by separating the "client" (the user interface/application) from the "server" (the data/logic processor). The client sends requests, and the server processes them and returns results. It is used to achieve separation of concerns, allowing the UI to remain lightweight while the server manages centralized business logic and data security.
[Image of client server architecture]

### 2. Application Service
An application service is a dedicated component in the backend designed to perform specific business tasks, such as processing a payment or calculating user points. Its purpose is to provide modularity and reusability, allowing different parts of a system to request specific logic without needing to know how that logic is implemented.

### 3. HTTP Request/Response
The lifecycle begins when a client (e.g., a browser) sends an HTTP Request (containing method, URL, and headers) to a server. The server processes the request and sends back an HTTP Response (containing status codes and data). This cycle is stateless, meaning each interaction is independent, requiring tokens or cookies to maintain sessions.

### 4. Horizontal vs. Vertical Scaling
Vertical Scaling means upgrading the existing server (adding more CPU/RAM), which is simple but hits a physical performance ceiling. Horizontal Scaling means adding more server instances to the network. Horizontal is generally preferred in modern systems because it offers better fault tolerance and nearly unlimited growth.
[Image of horizontal vs vertical scaling]

### 5. Load Balancer
In a high-traffic environment, a load balancer acts as a traffic officer, distributing incoming requests across multiple servers to ensure no single machine is overwhelmed. Its role is to ensure high availability and system stability by performing health checks and rerouting traffic if one server fails.

### 6. Microservices & Microfrontends
These patterns involve breaking a large application into small, independent, and deployable units. Microservices handle backend logic separately, while Microfrontends do the same for UI components. They are popular because they allow different teams to develop, scale, and deploy features independently without impacting the entire system.

### 7. Databases
Relational (SQL) databases (like PostgreSQL) store data in structured tables with strict schemas, ensuring data consistency via ACID properties. Non-relational (NoSQL) databases (like MongoDB) use flexible formats like documents or key-value pairs, which are optimized for rapid development and handling massive, unstructured data.

### 8. API Gateway
An API gateway acts as a single entry point for all client requests. It is necessary in microservice architectures to perform centralized tasks such as authentication, rate limiting, and request routing, shielding the complex backend services from direct client exposure.

### 9. Message Queue
Message queues enable asynchronous communication by acting as a buffer between services. A service sends a message (e.g., "process order") to the queue and continues working immediately, while another service consumes that message later. This prevents the system from crashing during traffic spikes by "smoothing out" the workload.
[Image of message queue in distributed systems]

### 10. Log & Monitor
Logs provide a historical trail of events, which is critical for debugging past errors. Monitoring provides real-time visibility into system health (e.g., CPU, latency, error rates). Together, they are essential because they turn a "black box" system into an observable one, allowing developers to detect and fix issues before they become outages.

### 11. Deployment (AWS/Azure/GCP)
Deploying to a cloud provider involves migrating application code onto their virtualized infrastructure. It entails utilizing services like virtual machines, containers, and managed databases, allowing developers to leverage global infrastructure, automated backups, and elastic scaling without owning physical hardware.

### 12. Security
Authentication verifies "who you are" (e.g., username/password login), while Authorization verifies "what you are allowed to do" (e.g., checking if a user has admin privileges to delete a file). Both are necessary to ensure users can only access the data they are permitted to see.

### 13. Why Testing
Testing is non-negotiable because it is the primary way to verify code correctness and ensure system reliability. It acts as a safety net during refactoring, allowing developers to change or optimize code with the confidence that existing features will not break.

---
**S3 Link:** https://rt-celine.s3.us-east-2.amazonaws.com/HW6.mp4?response-content-disposition=inline&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEJX%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMiJGMEQCID%2B24P79DwMrMcdOZ%2FhnxM3DTsCkMz2pYbYuNGD7BZhyAiABBkhKoGGdb29bsEq14BFSdxGXnIGctX7rF%2FGF32ALuCq1AwhfEAAaDDIxNzM0MzUwNTIxMCIM%2FbYgInY%2BFjD4ihw9KpID8c5mwqsVgJ%2FuuM08Tl3PQlM3Y6iprpJYbaC16roPK4QMlTa8KjuqarRra9%2Fl3nCjz4gxfwLh7bQ9HbgwuY0UCdNx4Gz67JIR6MpTaTfDN6l%2B54GBwFx9K5DggRD0adKwhvOeABfALC9nyJqDI0m47LKtA82Y6BP1smdj7L4V7AZABZhRHBCeeTIWclRR%2FwwCJ8riGhQ82js2S%2BMYVY5uKa8uGS4kjh5oKj1auQxEOJfD5d5I4Agecz8WVjgoIiH6b4z%2BfyZX6%2BrI2UAMpq2PeEmO0GstZ%2BNMle4FpdScIJ3GSiKQphmgOsjtqKX0ec56Oo5754YhcBWl%2BgbD9KEc64Q82z2wA5Ush0e4FxDvQ7tsFkTqiDEsYDTKGBOIFrFGBqlLDgK%2BzvRym80gmz6slD2mSFvIrLa1z0coHqRyo7xkbxaJ%2BCeo%2FNlK7dRuZptBLe%2FmhWkT3VpqZ5IZUpTEsP5LAg0P51JWRxacgpnmKLokBNILz330NrvBbGopZnMn2fhFkFSSsHWSCJ9fbkfomYwaMKzWh9EGOt8ClGRaLNRjr51my6ciBXy0VmDAGHNtxhGIkjaU3i6hNUQYfJsU3SRoVcel%2Fs%2BtK6NZ%2BqvXZzHFqieJgHi50s3jlpNxOCrr64RLKjz08jfAywOv80iWXvtjadbsmiLama9omz7zQAYtMTc19iZCgJPidNa9dbQdH6J0Qn%2B1Lnieo0a15yA5drtS%2F5eqL0bB%2FDIguAMAwTJk0TbQTy60JORruLCiR9W7ESpykmh1rQSSZRSkk0G76yD0%2B%2FHzP1%2Ft8IzBvsIg8Dnt3QzpItovgUOMwbw9g1wVpENUa%2Fz9i9KWxkCSDYh7polxWg%2F%2BUgiL%2Bt9em1FHakN8RG4yr5BJeOMhaiuJ01d2eOUVPOClsoAx0Rl79MZzXlRH%2F%2BbMhsUXBeSs%2B7H%2BP5esehf2cDd49PphwxlsiWZz%2B97%2B5DMCYsHaQULtRbEbkYtiFTHQ%2BEe8e4R3gASw4XLyg1hZjn5KLTza&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=ASIATFGVOWM5BYOU5UXW%2F20260604%2Fus-east-2%2Fs3%2Faws4_request&X-Amz-Date=20260604T212333Z&X-Amz-Expires=43200&X-Amz-SignedHeaders=host&X-Amz-Signature=b7062dadab917f348956a72998c0b49ddc5bcfa33e2893b427eb57dab26b29c1 
