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
- **Description**: Create a new egg within a specific nest.
- **Required Parameters**:
  - `name`: Name of the egg.
  - `tag`: Tag for the egg.
  - `description`: Description of what the egg is for.
  - `docker_image`: Docker image to be used for this egg.
  - `startup`: Startup command for the egg.
  - `config_from`: The configuration from which this egg is derived.
  - `config_logs`: Configuration for logs.
  - `config_files`: Configuration for files.
  - `config_startup`: Configuration for the startup process.
  - `config_stop`: Configuration for the stop process.
  - `custom_config`: Any custom configuration required for the egg.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nests/:nest/eggs"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{
          "name": "Minecraft Egg",
          "tag": "minecraft",
          "description": "Egg for running a Minecraft server",
          "docker_image": "minecraft/image:latest",
          "startup": "java -Xms512M -Xmx1024M -jar server.jar",
          "config_from": 1,
          "config_logs": "/var/logs",
          "config_files": "/var/data",
          "config_startup": "/start.sh",
          "config_stop": "stop",
          "custom_config": "{"custom": true}"
        }'
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


  
# NodeAllocationsService API Documentation

## Overview
This documentation provides details about the NodeAllocationsService API endpoints, used for managing node allocations in the application.

## API Endpoints

### 1. Get All Node Allocations
- **Endpoint**: `GET https://{your.panel.com}/api/admin/nodes/:node/allocations`
- **Method**: GET
- **Description**: Retrieve all allocations for a specific node.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nodes/:node/allocations"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get All Allocations for Selector
- **Endpoint**: `GET https://{your.panel.com}/api/admin/nodes/:node/allocations/selector`
- **Method**: GET
- **Description**: Retrieve allocations for a specific node based on certain criteria.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nodes/:node/allocations/selector?filter[ip_port]=IP_PORT&filter[in_use]=true"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 3. Create Allocation
- **Endpoint**: `POST https://{your.panel.com}/api/admin/nodes/:node/allocations`
- **Method**: POST
- **Description**: Create new allocations for a node.
- **Required Parameters**:
  - `ip`: Array of IPs.
  - `ports`: Array of ports.
  - `alias`: (Optional) Alias for the allocation.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nodes/:node/allocations"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "ip": ["192.168.0.1"], "ports": ["25565", "25566"], "alias": "MyServer" }'
  ```

### 4. Update Allocation
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/nodes/:node/allocations/:id`
- **Method**: PUT
- **Description**: Update an existing allocation.
- **Required Parameters**:
  - `id`: Identifier of the allocation to update.
  - `alias`: New alias for the allocation.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nodes/:node/allocations/:id"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PUT     -d '{ "alias": "UpdatedServer" }'
  ```

### 5. Mass Delete Allocations
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/nodes/:node/allocations`
- **Method**: DELETE
- **Description**: Mass delete allocations based on a set of identifiers or IPs.
- **Required Parameters**:
  - `allocations`: Array of allocation identifiers.
  - `ips`: Array of IP addresses.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nodes/:node/allocations"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE     -d '{ "allocations": [123, 124], "ips": ["192.168.0.1"] }'
  ```

### 6. Delete Allocation
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/nodes/:node/allocations/:id`
- **Method**: DELETE
- **Description**: Delete a specific allocation.
- **Required Parameters**:
  - `id`: Identifier of the allocation to delete.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nodes/:node/allocations/:id"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```



# NodeService API Documentation

## Overview
This documentation outlines the NodeService API endpoints, used for managing nodes in the application.

## API Endpoints

### 1. Get All Nodes
- **Endpoint**: `GET https://{your.panel.com}/api/admin/nodes`
- **Method**: GET
- **Description**: Retrieve all nodes.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nodes"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get Specific Node
- **Endpoint**: `GET https://{your.panel.com}/api/admin/nodes/:node`
- **Method**: GET
- **Description**: Retrieve a specific node.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nodes/:node"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 3. Update Node
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/nodes/:node`
- **Method**: PUT
- **Description**: Update an existing node.
- **Required Parameters**:
  - `name`: Name of the node.
  - `description`: (Optional) Description of the node.
  - `public`: Boolean indicating if the node is public.
  - `display_fqdn`: (Optional) Display fully qualified domain name.
  - `maintenance_mode`: Boolean indicating if the node is in maintenance mode.
  - `location_id`: Location identifier for the node.
  - `cpu`: Total CPU resources for the node.
  - `cpu_overallocate`: (Optional) Overallocation percentage for CPU.
  - `memory`: Total memory resources for the node.
  - `memory_overallocate`: (Optional) Overallocation percentage for memory.
  - `disk`: Total disk space for the node.
  - `disk_overallocate`: (Optional) Overallocation percentage for disk.
  - `upload_size`: Maximum upload size allowed.
  - `daemonListen`: Port number for the daemon to listen on.
  - `daemonSFTP`: Port number for SFTP.
  - `daemonFastdl`: Port number for FastDL.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nodes/:node"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PUT     -d '{
          "name": "Updated Node",
          "description": "New description",
          "public": true,
          "display_fqdn": "node.example.com",
          "maintenance_mode": false,
          "location_id": 1,
          "cpu": 100,
          "memory": 1024,
          "disk": 2048,
          ...
        }'
  ```


### 4. Delete Node
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/nodes/:node`
- **Method**: DELETE
- **Description**: Delete an existing node.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nodes/:node"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```

### 5. Get Node Daemon Information
- **Endpoint**: `GET https://{your.panel.com}/api/admin/nodes/:id/daemon-info`
- **Method**: GET
- **Description**: Retrieve daemon information for a specific node.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nodes/:id/daemon-info"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 6. Get Daemon Information for Multiple Nodes
- **Endpoint**: `GET https://{your.panel.com}/api/admin/nodes/daemon-info`
- **Method**: GET
- **Description**: Retrieve daemon information for multiple nodes.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/nodes/daemon-info"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```


  
# OverviewService API Documentation

## Overview
This documentation outlines the OverviewService API endpoint, which is used for retrieving license information in the application.

## API Endpoint

### Get License Information
- **Endpoint**: `GET https://{your.panel.com}/api/admin/license`
- **Method**: GET
- **Description**: Retrieve the license information.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/license"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```




  # ServerBackupService API Documentation

## Overview
This documentation outlines the ServerBackupService API endpoints, used for managing server backups in the application.

## API Endpoints

### 1. Get All Server Backups
- **Endpoint**: `GET https://{your.panel.com}/api/admin/servers/:server/backups`
- **Method**: GET
- **Description**: Retrieve all backups for a specific server.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers/:server/backups"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Toggle Server Backup
- **Endpoint**: `POST https://{your.panel.com}/api/admin/servers/:server/backups/:id/toggle`
- **Method**: POST
- **Description**: Toggle the backup state for a specific backup of a server.
- **Required Parameters**:
  - `id`: Identifier of the backup to toggle.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers/:server/backups/:id/toggle"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "id": 123 }'
  ```


# ServerDatabasesService API Documentation

## Overview
This documentation outlines the ServerDatabasesService API endpoints, used for managing server databases in the application.

## API Endpoints

### 1. Get All Server Databases
- **Endpoint**: `GET https://{your.panel.com}/api/admin/servers/:server/databases`
- **Method**: GET
- **Description**: Retrieve all databases for a specific server.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers/:server/databases"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Create Server Database
- **Endpoint**: `POST https://{your.panel.com}/api/admin/servers/:server/databases`
- **Method**: POST
- **Description**: Create a new database for a server.
- **Required Parameters**:
  - `host`: Identifier of the database host.
  - `name`: Name of the database.
  - `connections_from`: Allowed connections (IP or CIDR).
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers/:server/databases"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "host": 123, "name": "mydatabase", "connections_from": "192.168.0.1" }'
  ```

### 3. Rotate Server Database Password
- **Endpoint**: `POST https://{your.panel.com}/api/admin/servers/:server/databases/:id/rotate-password`
- **Method**: POST
- **Description**: Rotate the password for a specific server database.
- **Required Parameters**:
  - `id`: Identifier of the database.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers/:server/databases/:id/rotate-password"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST
  ```

### 4. Delete Server Database
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/servers/:server/databases/:id`
- **Method**: DELETE
- **Description**: Delete a specific database from a server.
- **Required Parameters**:
  - `id`: Identifier of the database to delete.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers/:server/databases/:id"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```




# ServerStartupService API Documentation

## Overview
This documentation outlines the ServerStartupService API endpoints, used for managing server startup configurations in the application.

## API Endpoints

### 1. Get Server Startup Configuration
- **Endpoint**: `GET https://{your.panel.com}/api/admin/servers/:server/startup`
- **Method**: GET
- **Description**: Retrieve the startup configuration for a specific server.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers/:server/startup"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Update Server Startup Configuration
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/servers/:server/startup`
- **Method**: PUT
- **Description**: Update the startup configuration for a specific server.
- **Required Parameters**:
  - `startup`: The startup command.
  - `egg_id`: Identifier of the egg.
  - `docker_image`: Docker image to be used.
  - `skip_scripts`: Boolean to skip execution of scripts.
  - `environment`: Key-value pairs for environment variables.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers/:server/startup"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PUT     -d '{ "startup": "java -Xms128M -Xmx1024M -jar server.jar", "egg_id": 1, "docker_image": "example/image:tag", "skip_scripts": false, "environment": { "ENV_VAR": "value" } }'
  ```



# ServersService API Documentation

## Overview
This documentation outlines the ServersService API endpoints, used for managing servers in the application.

## API Endpoints

### 1. Get All Servers
- **Endpoint**: `GET https://{your.panel.com}/api/admin/servers`
- **Method**: GET
- **Description**: Retrieve all servers.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get Specific Server
- **Endpoint**: `GET https://{your.panel.com}/api/admin/servers/:server`
- **Method**: GET
- **Description**: Retrieve a specific server.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers/:server"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 3. Create Server
- **Endpoint**: `POST https://{your.panel.com}/api/admin/servers`
- **Method**: POST
- **Description**: Create a new server.
- **Required Parameters**:
  - `name`: Name of the server.
  - `description`: (Optional) Description of the server.
  - `owner_id`: User ID of the server owner.
  - `egg_id`: Identifier of the egg.
  - `docker_image`: (Optional) Docker image to use.
  - `startup`: (Optional) Startup command.
  - `environment`: Environment variables.
  - `skip_scripts`: (Optional) Boolean to skip execution scripts.
  - `start_on_completion`: (Optional) Boolean to start the server upon creation completion.
  - `cpu`: CPU limit.
  - `memory`: Memory limit.
  - `swap`: Swap limit.
  - `disk`: Disk space limit.
  - `io`: IO performance.
  - `databases_limit`: Limit of databases.
  - `allocations_limit`: Limit of allocations.
  - `backup_megabytes_limit`: Backup size limit.
  - `primary_allocation_id`: Primary allocation ID.
  - `secondary_allocation_ids`: List of secondary allocation IDs.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{
          "name": "My Server",
          "owner_id": 1,
          "egg_id": 2,
          "environment": { "ENV_VAR": "value" },
          "cpu": 100,
          "memory": 1024,
          "disk": 10240,
          ...
        }'
  ```

### 4. Delete Server
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/servers/:server`
- **Method**: DELETE
- **Description**: Delete a specific server.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers/:server"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```

### 5. Update Server Details
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/servers/:server/details`
- **Method**: PUT
- **Description**: Update the details of a specific server.
- **Required Parameters**:
  - `name`: New name of the server.
  - `external_id`: (Optional) External identifier for the server.
  - `description`: Description of the server.
  - `owner_id`: User ID of the server owner.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/servers/:server/details"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PUT     -d '{ "name": "Updated Server Name", "external_id": "ext123", "description": "Updated description", "owner_id": 2 }'
  ```

### 6. Update Server Build Configuration
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/servers/:server/build`
- **Method**: PUT
- **Description**: Update the build configuration of a server.
- **Example Request**: TBD

### 7. Reinstall Server
- **Endpoint**: `POST https://{your.panel.com}/api/admin/servers/:server/reinstall`
- **Method**: POST
- **Description**: Reinstall the server.
- **Example Request**: TBD

### 8. Toggle Server Installation Status
- **Endpoint**: `POST https://{your.panel.com}/api/admin/servers/:server/toggle-install`
- **Method**: POST
- **Description**: Toggle the installation status of the server.
- **Example Request**: TBD

### 9. Rebuild Server
- **Endpoint**: `POST https://{your.panel.com}/api/admin/servers/:server/rebuild`
- **Method**: POST
- **Description**: Rebuild the server.
- **Example Request**: TBD

### 10. Suspend/Unsuspend Server
- **Endpoint**: `POST https://{your.panel.com}/api/admin/servers/:server/suspension`
- **Method**: POST
- **Description**: Suspend or unsuspend the server.
- **Example Request**: TBD

### 11. Move Server
- **Endpoint**: `POST https://{your.panel.com}/api/admin/servers/:server/move`
- **Method**: POST
- **Description**: Move the server to a different location or node.
- **Example Request**: TBD

### 12. Toggle Server Move Status
- **Endpoint**: `POST https://{your.panel.com}/api/admin/servers/:server/toggle-move`
- **Method**: POST
- **Description**: Toggle the move status of the server.
- **Example Request**: TBD

### 13. Reset Server Mods
- **Endpoint**: `POST https://{your.panel.com}/api/admin/servers/:server/reset-mods`
- **Method**: POST
- **Description**: Reset the mods of the server.
- **Example Request**: TBD




# SettingsService API Documentation

## Overview
This documentation outlines the SettingsService API endpoints, used for managing various settings in the application.

## API Endpoints

### General Settings Update
- **Endpoint**: `POST https://{your.panel.com}/api/admin/settings/general`
- **Method**: POST
- **Description**: Update general settings of the application.
- **Required Parameters**:
  - `branding.name`: Branding name.
  - `misc.databases_allow_random`: Boolean for database random allowance.
  - `misc.required_2fa`: Required 2FA level.
  - `default_locale`: Default locale setting.
- **Example Request**: TBD

### Embed Settings Update
- **Endpoint**: `POST https://{your.panel.com}/api/admin/settings/embed`
- **Method**: POST
- **Description**: Update embed settings of the application.
- **Required Parameters**:
  - `og.site_name`: Site name for embedding.
  - `og.title`: Embed title.
  - `og.description`: Embed description.
  - `og.color`: Embed color.
  - `og.image`: Embed image URL.
- **Example Request**: TBD

### JS Settings Update
- **Endpoint**: `POST https://{your.panel.com}/api/admin/settings/js`
- **Method**: POST
- **Description**: Update JavaScript settings.
- **Required Parameters**:
  - `js`: JavaScript content or script.
- **Example Request**: TBD

### CSS Settings Update
- **Endpoint**: `POST https://{your.panel.com}/api/admin/settings/css`
- **Method**: POST
- **Description**: Update CSS settings.
- **Required Parameters**:
  - `css`: CSS content.
- **Example Request**: TBD

### SSO Settings Update
- **Endpoint**: `POST https://{your.panel.com}/api/admin/settings/sso`
- **Method**: POST
- **Description**: Update Single Sign-On settings.
- **Required Parameters**:
  - `whmcs.enabled`: Boolean for WHMCS SSO enable.
  - `whmcs.button_text`: Button text for WHMCS SSO.
  - Other WHMCS related settings.
- **Example Request**: TBD

### Asset Uploads
- **Endpoints**:
  - `/settings/branding/login_logo`
  - `/settings/branding/favicon`
  - `/settings/branding/logo`
- **Method**: POST
- **Description**: Upload various branding assets like logos and favicon.
- **Required Parameters**:
  - `asset`: File to be uploaded.
- **Example Request**: TBD



# UsersService API Documentation

## Overview
This documentation outlines the UsersService API endpoints, used for managing users in the application.

## API Endpoints

### 1. Get All Users
- **Endpoint**: `GET https://{your.panel.com}/api/admin/users`
- **Method**: GET
- **Description**: Retrieve all users.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/users"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 2. Get Specific User
- **Endpoint**: `GET https://{your.panel.com}/api/admin/users/:user`
- **Method**: GET
- **Description**: Retrieve a specific user.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/users/:user"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X GET
  ```

### 3. Create User
- **Endpoint**: `POST https://{your.panel.com}/api/admin/users`
- **Method**: POST
- **Description**: Create a new user.
- **Required Parameters**:
  - `email`: Email of the user.
  - `name_first`: First name of the user.
  - `name_last`: Last name of the user.
  - `external_id`: External ID of the user.
  - `password`: Password for the user.
  - `root_admin`: Boolean indicating if the user is a root admin.
  - `support_op`: Boolean indicating if the user is a support operator.
  - `support_op_bypass`: Bypass option for support operation.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/users"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST     -d '{ "email": "user@example.com", "name_first": "John", "name_last": "Doe", ... }'
  ```

### 4. Update User
- **Endpoint**: `PUT https://{your.panel.com}/api/admin/users/:user`
- **Method**: PUT
- **Description**: Update an existing user.
- **Example Request**: TBD

### 5. Disable User's 2FA
- **Endpoint**: `POST https://{your.panel.com}/api/admin/users/:user/disable-2fa`
- **Method**: POST
- **Description**: Disable Two-Factor Authentication for a specific user.
- **Example Request**: TBD

### 6. Delete User
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/users/:id`
- **Method**: DELETE
- **Description**: Delete a specific user.
- **Required Parameters**:
  - `id`: Identifier of the user to delete.
- **Example Request**:
  ```bash
  curl "https://{your.panel.com}/api/admin/users/:id"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```


  
  
## Additional Notes
- Replace `<your.panel.com>` with your actual panel domain.
- Replace `:apiKey` and `:id` with the specific API key's identifier where applicable.
- Ensure proper authentication by including a valid API token in the `Authorization` header.
- The `Content-Type` header should be set as shown in the examples for proper request handling.

