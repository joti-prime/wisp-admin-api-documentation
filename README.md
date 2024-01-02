# Index:

- export { default as AnnouncementsService } from './announcements';
- export { default as ApiKeysService } from './apiKeys';
- export { default as DatabaseHostsService } from './databaseHosts';
- export { default as LocationsService } from './locations';
- export { default as MigratorService } from './migrator';
- export { default as ModsService } from './mods';
- export { default as NestsService } from './nests';
- export { default as EggsService } from './eggs';
- export { default as EggVariablesService } from './eggVariables';
- export { default as NodeAllocationsService } from './nodeAllocations';
- export { default as NodesService } from './nodes';
- export { default as OverviewService } from './overview';
- export { default as ServerBackupsService } from './serverBackups';
- export { default as ServerDatabasesService } from './serverDatabases';
- export { default as ServersService } from './servers';
- export { default as ServerStartupService } from './serverStartup';
- export { default as SettingsService } from './settings';
- export { default as DomainsService } from './domains';
- export { default as UsersService } from './users';


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
  ```bash
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
  ```bash
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
  ```bash
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
  ```bash
  curl "https://{your.panel.com}/api/admin/database-hosts"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get Specific Database Host
- **Endpoint**: `GET https://{your.panel.com}/api/admin/database-hosts/:databaseHost`
- **Method**: GET
- **Description**: Retrieve a specific database host.
- **Example Request**:
  ```bash
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
  ```bash
  curl "https://{your.panel.com}/api/admin/database-hosts"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "name": "MyDBHost", "host": "db.example.com", "port": 3306, "username": "admin", "password": "password", "phpmyadmin_url": "http://phpmyadmin.example.com" }'
  ```

### 4. Update Database Host
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/database-hosts/:databaseHost`
- **Method**: PUT
- **Description**: Update an existing database host.
- **Example Request**:
  ```bash
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
  ```bash
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
  ```bash
  curl "https://{your.panel.com}/api/admin/domains"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get Specific Domain
- **Endpoint**: `GET https://{your.panel.com}/api/admin/domains/:domain`
- **Method**: GET
- **Description**: Retrieve a specific domain.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/domains/:domain"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 3. Create Domain
- **Endpoint**: `POST https://{your.panel.com}/api/admin/domains`
- **Method**: POST
- **Description**: Create a new domain.
- **Required Parameters**:
  - `name`: Name of the domain.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/domains"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "name": "example.com" }'
  ```

### 4. Update Domain
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/domains/:domain`
- **Method**: PUT
- **Description**: Update an existing domain.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/domains/:domain"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PUT     -d '{ "name": "updated-example.com" }'
  ```

### 5. Delete Domain
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/domains/:id`
- **Method**: DELETE
- **Description**: Delete an existing domain.
- **Required Parameters**:
  - `id`: Identifier of the domain to delete.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/domains/:id"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```



# EggVariablesService API Documentation

## Overview
This documentation provides details about the EggVariablesService API endpoints, which are used for managing egg variables in the application.

## API Endpoints

### 1. Get All Egg Variables
- **Endpoint**: `GET https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg/variables`
- **Method**: GET
- **Description**: Retrieve all variables for a specific egg.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg/variables"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Create Egg Variable
- **Endpoint**: `POST https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg/variables`
- **Method**: POST
- **Description**: Create a new variable for a specific egg.
- **Required Parameters**:
  - `name`: Name of the variable.
  - `description`: Description of the variable.
  - `env_variable`: Environment variable name.
  - `default_value`: Default value of the variable.
  - `user_viewable`: Boolean indicating if the variable is viewable by the user.
  - `user_editable`: Boolean indicating if the variable is editable by the user.
  - `tickable`: Boolean indicating if the variable is tickable.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg/variables"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "name": "var_name", "description": "Variable description", "env_variable": "VAR_NAME", "default_value": "default", "user_viewable": true, "user_editable": true, "tickable": true }'
  ```

### 3. Update Egg Variable
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg/variables/:id`
- **Method**: PUT
- **Description**: Update an existing variable for a specific egg.
- **Required Parameters**:
  - All parameters as in `CreateVariableRequest`.
  - `id`: Identifier of the variable to update.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg/variables/:id"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PUT     -d '{ "name": "updated_var_name", "description": "Updated description", "env_variable": "UPDATED_VAR", "default_value": "updated_default", "user_viewable": false, "user_editable": false, "tickable": false, "id": 123 }'
  ```

### 4. Delete Egg Variable
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg/variables/:id`
- **Method**: DELETE
- **Description**: Delete an existing variable for a specific egg.
- **Required Parameters**:
  - `id`: Identifier of the variable to delete.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg/variables/:id"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```

  
# EggsService API Documentation

## Overview
This documentation details the EggsService API endpoints, which are used for managing eggs in the application.

## API Endpoints

### 1. Get All Eggs
- **Endpoint**: `GET https://{your.panel.com}/api/admin/nests/:nest/eggs`
- **Method**: GET
- **Description**: Retrieve all eggs for a specific nest.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest/eggs"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get Specific Egg
- **Endpoint**: `GET https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg`
- **Method**: GET
- **Description**: Retrieve a specific egg.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 3. Create Egg
- **Endpoint**: `POST https://{your.panel.com}/api/admin/nests/:nest/eggs`
- **Method**: POST
- **Description**: Create a new egg.
- **Required Parameters**:
  - `name`: Name of the egg.
  - `tag`: Tag for the egg.
  - `description`: Description of the egg.
  - `docker_image`: Docker image for the egg.
  - Other configuration parameters as needed.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest/eggs"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "name": "My Egg", "tag": "myegg", "description": "An example egg", "docker_image": "example/image" }'
  ```

### 4. Import Egg
- **Endpoint**: `POST https://{your.panel.com}/api/admin/nests/:nest_id/eggs/import`
- **Method**: POST
- **Description**: Import an egg from a file.
- **Note**: This endpoint requires `multipart/form-data` content type.
- **Example Request**:
  ```bash
  # Use appropriate tool or library to handle multipart/form-data for file upload.
  ```

### 5. Update Egg
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg`
- **Method**: PUT
- **Description**: Update an existing egg.
- **Required Parameters**:
  - Same as in `CreateEggRequest`.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PUT     -d '{ "name": "Updated Egg", "tag": "updatedegg", "description": "Updated description", "docker_image": "updated/image" }'
  ```

### 6. Delete Egg
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg`
- **Method**: DELETE
- **Description**: Delete an existing egg.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest/eggs/:egg"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```


  
# LocationsService API Documentation

## Overview
This documentation covers the LocationsService API endpoints, which are used for managing locations in the application.

## API Endpoints

### 1. Get All Locations
- **Endpoint**: `GET https://{your.panel.com}/api/admin/locations`
- **Method**: GET
- **Description**: Retrieve all locations.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/locations"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get Specific Location
- **Endpoint**: `GET https://{your.panel.com}/api/admin/locations/:location`
- **Method**: GET
- **Description**: Retrieve a specific location.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/locations/:location"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 3. Create Location
- **Endpoint**: `POST https://{your.panel.com}/api/admin/locations`
- **Method**: POST
- **Description**: Create a new location.
- **Required Parameters**:
  - `short`: Short code for the location.
  - `long`: Full name or description of the location.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/locations"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "short": "US-EAST", "long": "East Coast, USA" }'
  ```

### 4. Update Location
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/locations/:location`
- **Method**: PUT
- **Description**: Update an existing location.
- **Required Parameters**:
  - Same as in `CreateLocationRequest`.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/locations/:location"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PUT     -d '{ "short": "US-WEST", "long": "West Coast, USA" }'
  ```

### 5. Delete Location
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/locations/:id`
- **Method**: DELETE
- **Description**: Delete an existing location.
- **Required Parameters**:
  - `id`: Identifier of the location to delete.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/locations/:id"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```


# MigratorService API Documentation

## Overview
This documentation provides details about the MigratorService API endpoints, which are used for managing panel migrations in the application.

## API Endpoints

### 1. Get All Panel Migrations
- **Endpoint**: `GET https://{your.panel.com}/api/admin/migrator`
- **Method**: GET
- **Description**: Retrieve all panel migrations.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/migrator"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Trigger Migration
- **Endpoint**: `POST https://{your.panel.com}/api/admin/migrator`
- **Method**: POST
- **Description**: Trigger a new panel migration.
- **Required Parameters**:
  - `panel_url`: URL of the panel to migrate from.
  - `api_key`: API key for authentication.
  - Migration options (boolean values): `locations_node_and_game_data`, `nests_and_eggs`, `users`.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/migrator"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "panel_url": "https://old-panel.com", "api_key": "APIKEY", "locations_node_and_game_data": true, "nests_and_eggs": true, "users": true }'
  ```

### 3. Notify Users About Migration
- **Endpoint**: `POST https://{your.panel.com}/api/admin/migrator/:id/notify`
- **Method**: POST
- **Description**: Notify users about the migration.
- **Required Parameters**:
  - `id`: Identifier of the migration.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/migrator/:id/notify"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST
  ```

  
# ModsService API Documentation

## Overview
This documentation outlines the ModsService API endpoints, which are used for managing mods in the application.

## API Endpoints

### 1. Get All Mods
- **Endpoint**: `GET https://{your.panel.com}/api/admin/mods`
- **Method**: GET
- **Description**: Retrieve all mods.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/mods"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get Specific Mod
- **Endpoint**: `GET https://{your.panel.com}/api/admin/mods/:mod`
- **Method**: GET
- **Description**: Retrieve a specific mod.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/mods/:mod"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 3. Create Mod
- **Endpoint**: `POST https://{your.panel.com}/api/admin/mods`
- **Method**: POST
- **Description**: Create a new mod.
- **Required Parameters**:
  - `name`: Name of the mod.
  - `description`: Description of the mod.
  - `version`: Version of the mod.
  - `category`: Category of the mod.
  - `scriptInstall`: Install script for the mod.
  - `scriptUninstall`: Uninstall script for the mod.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/mods"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "name": "Mod Name", "description": "Description of mod", "version": "1.0", "category": "Category", "scriptInstall": "install.sh", "scriptUninstall": "uninstall.sh" }'
  ```

### 4. Update Mod
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/mods/:mod`
- **Method**: PUT
- **Description**: Update an existing mod.
- **Required Parameters**:
  - Same as in `CreateModRequest`.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/mods/:mod"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PUT     -d '{ "name": "Updated Mod", "description": "Updated description", "version": "1.1", "category": "Updated Category", "scriptInstall": "updated_install.sh", "scriptUninstall": "updated_uninstall.sh" }'
  ```

### 5. Delete Mod
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/mods/:id`
- **Method**: DELETE
- **Description**: Delete an existing mod.
- **Required Parameters**:
  - `id`: Identifier of the mod to delete.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/mods/:id"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```



# NestsService API Documentation

## Overview
This documentation outlines the NestsService API endpoints, used for managing nests in the application.

## API Endpoints

### 1. Get All Nests
- **Endpoint**: `GET https://{your.panel.com}/api/admin/nests`
- **Method**: GET
- **Description**: Retrieve all nests.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get Specific Nest
- **Endpoint**: `GET https://{your.panel.com}/api/admin/nests/:nest`
- **Method**: GET
- **Description**: Retrieve a specific nest.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 3. Create Nest
- **Endpoint**: `POST https://{your.panel.com}/api/admin/nests`
- **Method**: POST
- **Description**: Create a new nest.
- **Required Parameters**:
  - `name`: Name of the nest.
  - `identifier`: Identifier for the nest.
  - `description`: Description of the nest.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "name": "My Nest", "identifier": "my_nest", "description": "Description of my nest" }'
  ```

### 4. Update Nest
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/nests/:nest`
- **Method**: PUT
- **Description**: Update an existing nest.
- **Required Parameters**:
  - Same as in `CreateNestRequest`.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PUT     -d '{ "name": "Updated Nest", "identifier": "updated_nest", "description": "Updated description" }'
  ```

### 5. Delete Nest
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/nests/:nest`
- **Method**: DELETE
- **Description**: Delete an existing nest.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```

  
## Additional Notes
- Replace `<your.panel.com>` with your actual panel domain.
- Replace `:apiKey` and `:id` with the specific API key's identifier where applicable.
- Ensure proper authentication by including a valid API token in the `Authorization` header.
- The `Content-Type` header should be set as shown in the examples for proper request handling.

