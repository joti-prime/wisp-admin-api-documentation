
# AnnouncementsService API Documentation

## Overview
This documentation covers the AnnouncementsService API endpoints for the admin panel. These endpoints allow administrators to manage announcements within the panel.

## API Endpoints

### 1. Get All Announcements
- **Endpoint**: `GET https://{your.panel.com}/api/admin/announcements`
- **Method**: GET
- **Description**: Retrieve all announcements.
- **Example Request**:
  ```
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
  ```
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
  ```
  curl "https://{your.panel.com}/api/admin/announcements/123"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X PATCH     -d '{ "type": "warning", "text": "Maintenance extended", "active": true, "displayAtTop": true, "id": 123 }'
  ```

### 4. Resend an Announcement
- **Endpoint**: `POST https://{your.panel.com}/api/admin/announcements/<ID>/resend`
- **Method**: POST
- **Description**: Resend an existing announcement.
- **Required Parameters**:
  - `id`: Identifier of the announcement to resend.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/announcements/123/resend"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X POST
  ```

### 5. Delete an Announcement
- **Endpoint**: `DELETE https://{your.panel.com}/api/admin/announcements/<ID>`
- **Method**: DELETE
- **Description**: Delete an existing announcement.
- **Required Parameters**:
  - `id`: Identifier of the announcement to delete.
- **Example Request**:
  ```
  curl "https://{your.panel.com}/api/admin/announcements/123"     -H "Content-Type: application/json"     -H "Authorization: Bearer ADMINAPITOKEN"     -X DELETE
  ```

## Additional Notes
- Replace `<your.panel.com>` with your actual panel domain.
- Replace `<ID>` with the specific announcement's identifier where applicable.
- Ensure proper authentication by including a valid API token in the `Authorization` header.
- The `Content-Type` header should be set as shown in the examples for proper request handling.
