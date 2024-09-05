# Project Guidelines and Best Practices

## Development Steps

1. **Create Jira Ticket**:
   - Always create a Jira ticket before starting any work.

2. **Branching and Commit Messages**:
   - **Branch Name**: Include the Jira ticket number. For example, `feature/MB-180`.
   - **Commit Messages**: Prefix commit messages with the Jira ticket number. For example, `MB-180: Description of the commit`.

   ```bash
   # Creating a new branch
   git branch feature/MB-180
   
   # Committing message
   git commit -m "MB-180: Description of the commit"
   ```

3. **Pull Request Naming**:

   - Name your pull request in accordance with the Jira ticket number and description. Include relevant images if necessary, e.g., image-20230502-074059.png.

4. **Solution Design**:

   - Always design scalable solutions. If building a service, ensure it is end-to-end.
   - If copying code from other repositories, rename files, update swagger descriptions, and make necessary changes end-to-end.

5. **Database Design**:

   - Be specific when creating SQL tables; avoid using varchar for all columns.
   - Always include created_at and updated_at fields in your database schema.
   - Assess the appropriateness of SQL vs. NoSQL databases for your use case.
   - Avoid blindly creating collections or databases. Learn to separate data according to services.
   - Name databases and collections meaningfully to reflect their purpose.
   - Use proper database schemas (for SQL) and understand NoSQL principles.

6. **Containerization**:

   - Ensure everything is Dockerized.

7. **Environment Variables**:

   - Store environment variables in a .env file. Provide a .env.sample file in the repository with dummy data.
   - Ensure .env file is added to .gitignore.

8. **Critical Services**:

   - For critical services, integrate internal Slack alerts by creating a dedicated channel for the service (not for individual modules).


## Development Steps

1. **Server Monitoring**:

   - Monitor server metrics on Grafana (Azure VM Dashboard) before deploying. If the server is underutilized, deploy directly or contact @support for a new server.

2. **API Deployment**:

   - Contact engineer to configure the internal DNS for the API.

3. **Testing**:

   - Thoroughly test your deployment through all entry points and use cases.
   - Do not rely solely on the client to test your service.

## After Deployment Steps

1. **Documentation**:

   - Update the "Services On Cloud" document for every deployed service.

2. **Monitoring**:

   - For every API deployed, add it to Kuma Monitor on the Kuma Dashboard and link it to internal or external status pages (Kuma Manage Status Page)

3. **Endpoint Management**:

   - Copy the correct URLs (with both link and text) into the Backend-Endpoints Google Sheet.

4. **Confluence Documentation**:

   - Maintain a Confluence document for the service.

5. **Architecture Diagrams**:

   - Create and save an architecture diagram using Flowchart Maker or similar online diagram software. Store it in the Architecture Diagrams directory. (Request access from @support)

6. **Release Notification**:

   - Notify the Engineering Channel of your release.
