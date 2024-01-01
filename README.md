
# AnnouncementsService API Documentation

## Overview
This documentation covers the AnnouncementsService API endpoints for the admin panel. These endpoints allow administrators to manage announcements within the panel.

## API Endpoints

### 1. Get All Announcements
- **Endpoint**: `GET https://{your.panel.com}/api/admin/announcements`
- **Method**: GET
- **Description**: Retrieve all announcements.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/announcements"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Create an Announcement
- **Endpoint**: `POST https://{your.panel.com}/api/admin/announcements`
- **Method**: POST
- **Description**: Create a new announcement.
- **Required Parameters**:
  - `type`: Type of the announcement.
  - `text`: Text content of the announcement.
  - `active`: Boolean indicating if the announcement is active.
  - `displayAtTop`: Boolean indicating if the announcement should be displayed at the top.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/announcements"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "type": "info", "text": "Server maintenance scheduled", "active": true, "displayAtTop": false }'
  ```

### 3. Update an Announcement
- **Endpoint**: `PATCH https://{your.panel.com}/api/admin/announcements/<ID>`
- **Method**: PATCH
- **Description**: Update an existing announcement.
- **Required Parameters**:
  - `id`: Identifier of the announcement.
  - Other parameters as in `CreateAnnouncementRequest`.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/announcements/123"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PATCH     -d '{ "type": "warning", "text": "Maintenance extended", "active": true, "displayAtTop": true, "id": 123 }'
  ```

### 4. Resend an Announcement
- **Endpoint**: `POST https://{your.panel.com}/api/admin/announcements/<ID>/resend`
- **Method**: POST
- **Description**: Resend an existing announcement.
- **Required Parameters**:
  - `id`: Identifier of the announcement to resend.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/announcements/123/resend"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST
  ```

### 5. Delete an Announcement
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/announcements/<ID>`
- **Method**: DELETE
- **Description**: Delete an existing announcement.
- **Required Parameters**:
  - `id`: Identifier of the announcement to delete.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/announcements/123"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```



# ApiKeysService API Documentation

## Overview
This documentation details the ApiKeysService API endpoints, which are used for managing API keys in the application.

## API Endpoints

### 1. Get All API Keys
- **Endpoint**: `GET https://{your.panel.com}/api/admin/application-api`
- **Method**: GET
- **Description**: Retrieve all API keys.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/application-api"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get Specific API Key
- **Endpoint**: `GET https://{your.panel.com}/api/admin/application-api/:apiKey`
- **Method**: GET
- **Description**: Retrieve a specific API key.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/application-api/:apiKey"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 3. Create API Key
- **Endpoint**: `POST https://{your.panel.com}/api/admin/application-api`
- **Method**: POST
- **Description**: Create a new API key.
- **Required Parameters**:
  - `[key: ResourceString]`: Resource string for the API key.
  - `memo`: A memo for the API key.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/application-api"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "r_exampleResource": 1, "memo": "My new API key" }'
  ```

### 4. Update API Key
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/application-api/:apiKey`
- **Method**: PUT
- **Description**: Update an existing API key.
- **Note**: Endpoint pending finalization.
- **Example Request**: TBD

### 5. Delete API Key
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/application-api/:id`
- **Method**: DELETE
- **Description**: Delete an existing API key.
- **Required Parameters**:
  - `id`: Identifier of the API key to delete.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/application-api/:id"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```



# DatabaseHostsService API Documentation

## Overview
This documentation describes the DatabaseHostsService API endpoints, used for managing database hosts in the application.

## API Endpoints

### 1. Get All Database Hosts
- **Endpoint**: `GET https://{your.panel.com}/api/admin/database-hosts`
- **Method**: GET
- **Description**: Retrieve all database hosts.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/database-hosts"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get Specific Database Host
- **Endpoint**: `GET https://{your.panel.com}/api/admin/database-hosts/:databaseHost`
- **Method**: GET
- **Description**: Retrieve a specific database host.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/database-hosts/:databaseHost"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 3. Create Database Host
- **Endpoint**: `POST https://{your.panel.com}/api/admin/database-hosts`
- **Method**: POST
- **Description**: Create a new database host.
- **Required Parameters**:
  - `name`: Name of the database host.
  - `host`: Host address.
  - `port`: Port number.
  - `username`: Username for the database host.
  - `password`: Password for the database host.
  - `phpmyadmin_url`: URL to phpMyAdmin for the host.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/database-hosts"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "name": "MyDBHost", "host": "db.example.com", "port": 3306, "username": "admin", "password": "password", "phpmyadmin_url": "http://phpmyadmin.example.com" }'
  ```

### 4. Update Database Host
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/database-hosts/:databaseHost`
- **Method**: PUT
- **Description**: Update an existing database host.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/database-hosts/:databaseHost"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PUT     -d '{ "name": "UpdatedDBHost", "host": "db-updated.example.com", "port": 3307, "username": "admin_updated", "password": "password_updated", "phpmyadmin_url": "http://phpmyadmin-updated.example.com" }'
  ```

### 5. Delete Database Host
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/database-hosts/:id`
- **Method**: DELETE
- **Description**: Delete an existing database host.
- **Required Parameters**:
  - `id`: Identifier of the database host to delete.
  - `force`: Boolean indicating whether to force delete.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/database-hosts/:id"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE     -d '{ "force": true }'
  ```



# DomainsService API Documentation

## Overview
This documentation provides details about the DomainsService API endpoints, which are used for managing domains in the application.

## API Endpoints

### 1. Get All Domains
- **Endpoint**: `GET https://{your.panel.com}/api/admin/domains`
- **Method**: GET
- **Description**: Retrieve all domains.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/domains"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get Specific Domain
- **Endpoint**: `GET https://{your.panel.com}/api/admin/domains/:domain`
- **Method**: GET
- **Description**: Retrieve a specific domain.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/domains/:domain"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 3. Create Domain
- **Endpoint**: `POST https://{your.panel.com}/api/admin/domains`
- **Method**: POST
- **Description**: Create a new domain.
- **Required Parameters**:
  - `name`: Name of the domain.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/domains"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "name": "example.com" }'
  ```

### 4. Update Domain
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/domains/:domain`
- **Method**: PUT
- **Description**: Update an existing domain.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/domains/:domain"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PUT     -d '{ "name": "updated-example.com" }'
  ```

### 5. Delete Domain
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/domains/:id`
- **Method**: DELETE
- **Description**: Delete an existing domain.
- **Required Parameters**:
  - `id`: Identifier of the domain to delete.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/domains/:id"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```


## Additional Notes
- Replace `<your.panel.com>` with your actual panel domain.
- Replace `:apiKey` and `:id` with the specific API key's identifier where applicable.
- Ensure proper authentication by including a valid API token in the `Authorization` header.
- The `Content-Type` header should be set as shown in the examples for proper request handling.

