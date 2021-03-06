swagger: "2.0"
x-collection-name: Actility
x-complete: 1
info:
  title: ThingPark DX Maker API
  description: api-providing-features-for-device-makers-such-as-preprovisioning-on-standalone-join-servers-
  version: 1.0.0
host: dx-api.thingpark.com
basePath: /maker/v011/api
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /profiles:
    get:
      summary: Profiles Retrieval
      description: Retrieves all available profiles. By default only retrieves ACTILITY-owned
        profiles.
      operationId: retrieves-all-available-profiles-by-default-only-retrieves-actilityowned-profiles
      x-api-path-slug: profiles-get
      responses:
        200:
          description: OK
      tags:
      - Profiles
      - Retrieval
  /profiles/{profileId}:
    get:
      summary: Profile Retrieval
      description: Retrieves the profile corresponding to the provided profile Id.
      operationId: retrieves-the-profile-corresponding-to-the-provided-profile-id
      x-api-path-slug: profilesprofileid-get
      parameters:
      - in: path
        name: profileId
        description: Id of the profile to retrieve
      responses:
        200:
          description: OK
      tags:
      - Profile
      - Retrieval
  /deviceProfiles:
    get:
      summary: Device profiles retrieval
      description: Retrieves the list of existing device profiles.
      operationId: retrieves-the-list-of-existing-device-profiles
      x-api-path-slug: deviceprofiles-get
      responses:
        200:
          description: OK
      tags:
      - Device
      - Profiles
      - Retrieval
  /routingProfiles:
    get:
      summary: Routing profiles retrieval
      description: Retrieves a list of existing routing profiles within authorized
        scopes.
      operationId: retrieves-a-list-of-existing-routing-profiles-within-authorized-scopes
      x-api-path-slug: routingprofiles-get
      parameters:
      - in: query
        name: routingProfileId
        description: Id of the routing profile to search for
      responses:
        200:
          description: OK
      tags:
      - Routing
      - Profiles
      - Retrieval
    post:
      summary: Routing profiles creation
      description: Creates a new routing profile.
      operationId: creates-a-new-routing-profile
      x-api-path-slug: routingprofiles-post
      parameters:
      - in: body
        name: routingProfile
        description: Contents of the routing profile to create
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Routing
      - Profiles
      - Creation
  /baseStationProfiles:
    get:
      summary: Base station profiles retrieval
      description: Retrieves the list of existing base station profiles.
      operationId: retrieves-the-list-of-existing-base-station-profiles
      x-api-path-slug: basestationprofiles-get
      responses:
        200:
          description: OK
      tags:
      - Base
      - Station
      - Profiles
      - Retrieval
  /routingProfiles/{routingProfileRef}:
    get:
      summary: Routing profile retrieval
      description: Retrieves the routing profile corresponding to the provided routing
        profile ref, if that routing profile is within authorized scopes.
      operationId: retrieves-the-routing-profile-corresponding-to-the-provided-routing-profile-ref-if-that-routing-prof
      x-api-path-slug: routingprofilesroutingprofileref-get
      parameters:
      - in: path
        name: routingProfileRef
        description: Ref of the routing profile to retrieve
      responses:
        200:
          description: OK
      tags:
      - Routing
      - Profile
      - Retrieval
    put:
      summary: Routing profile update
      description: Updates the routing profile corresponding to the provided routing
        profile ref, if that routing profile is within authorized scopes. Note that
        the 'default' attribute can only be updated from 'false' to 'true' (thus updating
        'default' attribute for the previous default routing profile from 'true' to
        'false').
      operationId: updates-the-routing-profile-corresponding-to-the-provided-routing-profile-ref-if-that-routing-profil
      x-api-path-slug: routingprofilesroutingprofileref-put
      parameters:
      - in: body
        name: routingProfile
        description: Contents of the routing profile to update
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: routingProfileRef
        description: Ref of the routing profile to update
      responses:
        200:
          description: OK
      tags:
      - Routing
      - Profile
      - Update
    delete:
      summary: Routing profile deletion
      description: Deletes the routing profile corresponding to the provided routing
        profile ref, if that routing profile is within authorized scopes.
      operationId: deletes-the-routing-profile-corresponding-to-the-provided-routing-profile-ref-if-that-routing-profil
      x-api-path-slug: routingprofilesroutingprofileref-delete
      parameters:
      - in: path
        name: routingProfileRef
        description: Ref of the routing profile to delete
      responses:
        200:
          description: OK
      tags:
      - Routing
      - Profile
      - Deletion