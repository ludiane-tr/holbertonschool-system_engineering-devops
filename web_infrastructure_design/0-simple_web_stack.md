### 0. Simple Web Stack

This is a basic web infrastructure using one server to host a website accessible via `www.foobar.com`.

#### Scenario
A user opens their browser and types `www.foobar.com`. Here's what happens behind the scenes:

- The **domain name** `www.foobar.com` is resolved through DNS to the IP address `8.8.8.8`, thanks to an **A record** pointing to the server.
- The request reaches the server at `8.8.8.8`, where:
  - The **web server (Nginx)** handles the incoming HTTP/HTTPS request.
  - If it's a static file (HTML, CSS, JS), Nginx serves it directly.
  - If it's a dynamic request, Nginx forwards it to the **application server**.
  - The **application server** processes the logic (e.g., login, data manipulation) using the **application code**, and interacts with the **database (MySQL)** to fetch or store data.
  - The application server returns the response to Nginx, which sends it back to the user's browser.

#### Components
- **Server**: A physical or virtual machine that runs all the components below.
- **Domain name**: Human-readable name that maps to the server's IP using a DNS A record.
- **Web server (Nginx)**: Listens for HTTP(S) requests, serves static files, and forwards dynamic requests to the app server.
- **Application server**: Runs the backend logic and communicates with the database.
- **Application code**: The source code that powers the web app.
- **Database (MySQL)**: Stores persistent application data (e.g., users, posts).

#### Communication
The server uses the **HTTP or HTTPS protocols** to exchange data with the user's browser.

####  Limitations of this architecture
- **Single Point of Failure (SPOF)**: If the server crashes, the entire website goes down.
- **Downtime during maintenance**: Updates or deployments may require restarts, causing temporary unavailability.
- **Scalability issues**: One server may not be enough to handle high traffic.

