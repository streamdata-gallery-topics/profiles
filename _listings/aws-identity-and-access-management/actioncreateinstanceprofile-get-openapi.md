---
swagger: "2.0"
x-collection-name: AWS Identity and Access Management
x-complete: 0
info:
  title: AWS Identity and Access Management API Create Instance Profile
  version: 1.0.0
  description: Creates a new instance profile.
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /?Action=CreateInstanceProfile:
    get:
      summary: Create Instance Profile
      description: Creates a new instance profile.
      operationId: createInstanceProfile
      x-api-path-slug: actioncreateinstanceprofile-get
      parameters:
      - in: query
        name: InstanceProfileName
        description: The name of the instance profile to create
        type: string
      - in: query
        name: Path
        description: The path to the instance profile
        type: string
      responses:
        '400: for badly-formed requests, e.g. missing or invalid parameters':
          description: ""
        '403: for authentication issues':
          description: ""
        '409: for issues where the request is well-formed but cannot be completed':
          description: ""
        200:
          description: OK
      tags:
      - Instance Profiles
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