# Simple Web Infrastructure

## Diagram
Requête Utilisateur
      |
      v
+-----------------+
|  Serveur Web    |  (Nginx)
+--------+--------+
         |
         v
+--------+--------+
|  Serveur        |  (Serveur d'Application)
|  d'Application  |
+--------+--------+
         |
         v
+--------+--------+
|  Base de        |  (MySQL)
|  Données        |
+-----------------+

## Explanation of the Infrastructure

### Components and Their Roles
1. **Server**:
   - Hosts the web server, application server, and database.
   - Provides the hardware and software environment for running the website.

2. **Web Server (Nginx)**:
   - Serves static content (HTML, CSS, JS) to users.
   - Forwards dynamic requests to the application server.

3. **Application Server**:
   - Handles dynamic content and business logic.
   - Communicates with the database to retrieve or store data.

4. **Database (MySQL)**:
   - Stores and manages data for the application.
   - Provides a structured way to query and manipulate data.

5. **Domain Name (`www.foobar.com`)**:
   - Provides a human-readable address for users to access the website.
   - The `www` record points to the server IP (`8.8.8.8`).

### Communication Flow
1. The user types `www.foobar.com` in their browser.
2. The domain name is resolved to the server IP (`8.8.8.8`).
3. The request reaches the web server (Nginx), which serves static content or forwards dynamic requests to the application server.
4. The application server processes the request, interacts with the database if needed, and returns the result to the web server.
5. The web server sends the final response (HTML, JSON, etc.) back to the user’s browser.

### Issues with This Infrastructure
1. **Single Point of Failure (SPOF)**:
   - If the server fails, the entire website goes down.
2. **Downtime During Maintenance**:
   - The website becomes unavailable during code deployment or server restarts.
3. **Cannot Scale for High Traffic**:
   - A single server has limited resources and may become overwhelmed by high traffic.