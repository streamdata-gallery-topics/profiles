swagger: "2.0"
x-collection-name: Plentymarkets
x-complete: 1
info:
  title: plentymarkets REST-API
  description: the-plentymarkets-rest-api-expands-the-functionality-of-the-plentymarkets-cms-and-allows-access-to-resources-i-e--data-records-via-unique-uri-paths
  contact:
    name: plentymarkets
    url: https://forum.plentymarkets.com/c/rest-api
  version: 1.0.0
host: example.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /rest/items/item_shipping_profiles:
    get:
      summary: List all shipping profiles of all items
      description: |-
        Lists all shipping profiles of all items. Results can be filtered by the timestamp of the link between items and shipping profiles (eq, lt, lte, gt, gte, between).
        <ul>
        <li>eq = Equal to</li>
        <li>gte = Greater than or equal to</li>
        <li>gt = Greater than</li>
        <li>lte = Less than or equal to</li>
        <li>lt = Less than</li>
        <li>between = Date range</li>
        </ul>
        Example: updated=gt:2018-04-16 16:00:00 returns all items with shipping profiles that were activated after 4pm on the 16th of April 2018.
      operationId: getRestItemsItemShippingProfiles
      x-api-path-slug: restitemsitem-shipping-profiles-get
      responses:
        200:
          description: OK
      tags:
      - List
      - ""
      - Shipping
      - Profiles
      - Of
      - ""
      - Items
    post:
      summary: Bulk activate shipping profiles
      description: Activates up to 50 shipping profiles for items
      operationId: postRestItemsItemShippingProfiles
      x-api-path-slug: restitemsitem-shipping-profiles-post
      responses:
        200:
          description: OK
      tags:
      - Bulk
      - Activate
      - Shipping
      - Profiles
  /rest/items/{itemId}/item_shipping_profiles:
    delete:
      summary: Deactivate shipping profiles of an item
      description: Deactivates all shipping profiles of an item. The ID of the item
        must be specified.
      operationId: deleteRestItemsItemItemShippingProfiles
      x-api-path-slug: restitemsitemiditem-shipping-profiles-delete
      parameters:
      - in: path
        name: itemId
      responses:
        200:
          description: OK
      tags:
      - Deactivate
      - Shipping
      - Profiles
      - Of
      - Item
    get:
      summary: List shipping profiles of an item
      description: Lists the shipping profiles linked to an item. The ID of the item
        must be specified.
      operationId: getRestItemsItemItemShippingProfiles
      x-api-path-slug: restitemsitemiditem-shipping-profiles-get
      parameters:
      - in: path
        name: itemId
      responses:
        200:
          description: OK
      tags:
      - List
      - Shipping
      - Profiles
      - Of
      - Item
    post:
      summary: Activate a shipping profile
      description: Links a shipping profile to the item. The ID of the item and the
        ID of the shipping profile must be specified.
      operationId: postRestItemsItemItemShippingProfiles
      x-api-path-slug: restitemsitemiditem-shipping-profiles-post
      parameters:
      - in: path
        name: itemId
      responses:
        200:
          description: OK
      tags:
      - Activate
      - Shipping
      - Profile
  /rest/listings/shipping_profiles:
    get:
      summary: List listing shipping profiles
      description: Lists listing shipping profiles.
      operationId: getRestListingsShippingProfiles
      x-api-path-slug: restlistingsshipping-profiles-get
      parameters:
      - in: query
        name: credentialsId
        description: Filter that restricts the search result to listing shipping profiles
          with given credential ID(s)
      - in: query
        name: id
        description: Filter that restricts the search result to listing shipping profiles
          that match the given ID(s)
      - in: query
        name: itemsPerPage
        description: The number of items to list per page
      - in: query
        name: page
        description: The page of results to search for
      - in: query
        name: referrerId
        description: Filter that restricts the search result to listing shipping profiles
          with given referrer ID(s)
      responses:
        200:
          description: OK
      tags:
      - List
      - Listing
      - Shipping
      - Profiles
  /rest/orders/shipping/presets:
    get:
      summary: List shipping profiles
      description: List shipping profiles.
      operationId: getRestOrdersShippingPresets
      x-api-path-slug: restordersshippingpresets-get
      parameters:
      - in: query
        name: columns
        description: The attributes to be loaded in the shipping profile
      - in: query
        name: parcelServiceName
        description: Filter that restricts the search result to parcel service presets
          with a specified service name (e
      - in: query
        name: shippingServiceProvider
        description: Filter that restricts the search result to a shipping service
          provider
      - in: query
        name: updatedAtAfter
        description: Filter that restricts the search result to presets that were
          updated after a specific date
      - in: query
        name: updatedAtBefore
        description: Filter that restricts the search result to presets that were
          updated before a specific date
      - in: query
        name: with
        description: The name of an relation to the preset
      responses:
        200:
          description: OK
      tags:
      - List
      - Shipping
      - Profiles
  /rest/items/{itemId}/item_shipping_profiles/{id}:
    delete:
      summary: Deactivate a shipping profile
      description: Unlinks a shipping profile from the item. The ID of the item must
        be specified.
      operationId: deleteRestItemsItemItemShippingProfiles
      x-api-path-slug: restitemsitemiditem-shipping-profilesid-delete
      parameters:
      - in: path
        name: id
      - in: path
        name: itemId
      responses:
        200:
          description: OK
      tags:
      - Deactivate
      - Shipping
      - Profile
  /rest/listings/shipping_profiles/{id}:
    get:
      summary: Get a shipping profile
      description: Gets a shipping profile by providing its ID.
      operationId: getRestListingsShippingProfiles
      x-api-path-slug: restlistingsshipping-profilesid-get
      parameters:
      - in: path
        name: id
      - in: query
        name: with
        description: An array with child instances to be loaded
      responses:
        200:
          description: OK
      tags:
      - Shipping
      - Profile
  /rest/orders/shipping/presets/{presetId}:
    get:
      summary: Get a shipping profile
      description: Gets a shipping profile. The ID of the shipping profile must be
        specified.
      operationId: getRestOrdersShippingPresetsPreset
      x-api-path-slug: restordersshippingpresetspresetid-get
      parameters:
      - in: query
        name: columns
        description: The attributes to be loaded in the shipping profile
      - in: path
        name: presetId
      responses:
        200:
          description: OK
      tags:
      - Shipping
      - Profile