---
swagger: "2.0"
x-collection-name: CollabNet
x-complete: 0
info:
  title: CollabNet TeamForge API Documentation Deletes profile picture for current
    user
  version: 1.0.0
  description: Deletes profile picture for current user.
basePath: /ctfrest/foundation/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /users/{userid}/profile-picture:
    delete:
      summary: Deletes profile picture by user id
      description: Deletes profile picture by user id.
      operationId: deleteProfilePictureById
      x-api-path-slug: usersuseridprofilepicture-delete
      parameters:
      - in: path
        name: userid
        description: User ID
      responses:
        200:
          description: OK
      tags:
      - Profile
      - Picture
      - By
      - User
    post:
      summary: Uploads and sets profile picture by user id
      description: Uploads and sets profile picture by user id.
      operationId: setProfilePictureById
      x-api-path-slug: usersuseridprofilepicture-post
      parameters:
      - in: body
        name: body
        description: Picture
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: userid
        description: User ID
      responses:
        200:
          description: OK
      tags:
      - Uploads
      - Sets
      - Profile
      - Picture
      - By
      - User
  /users/myself/profile-picture:
    delete:
      summary: Deletes profile picture for current user
      description: Deletes profile picture for current user.
      operationId: deleteProfilePictureForMyself
      x-api-path-slug: usersmyselfprofilepicture-delete
      responses:
        200:
          description: OK
      tags:
      - Profile
      - Picturecurrent
      - User
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---