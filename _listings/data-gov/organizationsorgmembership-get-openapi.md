---
swagger: "2.0"
x-collection-name: Data.Gov
x-complete: 0
info:
  title: Data.gov API Get Organizations Org Membership
  description: List membership requests for a given organization
  version: "3"
host: catalog.data.gov
basePath: /api/3/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /organizations/{org}/:
    get:
      summary: Get Organizations Org
      description: Get a organization given its identifier
      operationId: getOrganizationsOrg
      x-api-path-slug: organizationsorg-get
      parameters:
      - in: path
        name: org
        description: The organization ID or slug
      responses:
        200:
          description: OK
      tags:
      - Organizations
      - Org
    put:
      summary: Put Organizations Org
      description: Update a organization given its identifier
      operationId: putOrganizationsOrg
      x-api-path-slug: organizationsorg-put
      parameters:
      - in: path
        name: org
        description: The organization ID or slug
      - in: body
        name: payload
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Organizations
      - Org
  /organizations/{org}/badges/:
    post:
      summary: Add Organizations Org Badges
      description: Create a new badge for a given organization
      operationId: postOrganizationsOrgBadges
      x-api-path-slug: organizationsorgbadges-post
      parameters:
      - in: path
        name: org
        description: The organization ID or slug
      - in: body
        name: payload
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Organizations
      - Org
      - Badges
  /organizations/{org}/datasets/:
    get:
      summary: Get Organizations Org Datasets
      description: List organization datasets (including private ones when member)
      operationId: getOrganizationsOrgDatasets
      x-api-path-slug: organizationsorgdatasets-get
      parameters:
      - in: path
        name: org
      responses:
        200:
          description: OK
      tags:
      - Organizations
      - Org
      - Datasets
  /organizations/{org}/logo:
    post:
      summary: Add Organizations Org Logo
      description: Upload a new logo
      operationId: postOrganizationsOrgLogo
      x-api-path-slug: organizationsorglogo-post
      parameters:
      - in: formData
        name: bbox
      - in: formData
        name: file
      - in: path
        name: org
        description: The organization ID or slug
      responses:
        200:
          description: OK
      tags:
      - Organizations
      - Org
      - Logo
    put:
      summary: Put Organizations Org Logo
      description: Set the logo BBox
      operationId: putOrganizationsOrgLogo
      x-api-path-slug: organizationsorglogo-put
      parameters:
      - in: formData
        name: bbox
      - in: formData
        name: file
      - in: path
        name: org
        description: The organization ID or slug
      responses:
        200:
          description: OK
      tags:
      - Organizations
      - Org
      - Logo
  /organizations/{org}/membership/:
    get:
      summary: Get Organizations Org Membership
      description: List membership requests for a given organization
      operationId: getOrganizationsOrgMembership
      x-api-path-slug: organizationsorgmembership-get
      parameters:
      - in: path
        name: org
        description: The organization ID or slug
      - in: query
        name: status
        description: If provided, only return requests ith a given status
      responses:
        200:
          description: OK
      tags:
      - Organizations
      - Org
      - Membership
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