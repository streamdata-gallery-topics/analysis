swagger: "2.0"
x-collection-name: Pingdom
x-complete: 1
info:
  title: Traceroute API
  description: the-traceroute-api-
  version: 1.0.0
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  ? |2-

        /api/{version}/analysis/{checkid}
  : ? |2-

          get
    : summary: Get Root Cause Analysis Results List
      description: Returns a list of the latest root cause analysis results for a
        specified check.
      operationId: get-root-cause-analysis-results-list
      x-api-path-slug: apiversionanalysischeckid-get
      parameters:
      - in: query
        name: from
        description: Return only results with timestamp of first test greater or equal
          to this value
        type: <td>integer</td>
      - in: query
        name: limit
        description: Limits the number of returned results to the specified quantity
        type: <td>integer</td>
      - in: query
        name: offset
        description: Offset for listing
        type: <td>integer</td>
      - in: query
        name: to
        description: Return only results with timestamp of first test less or equal
          to this value
        type: <td>integer</td>
      responses:
        "":
          description: ""
        400:
          description: Bad input parameter
        401:
          description: Bad or expired token
        403:
          description: Bad OAuth request (wrong consumer key, bad nonce, expired timestamp
        404:
          description: File or folder not found at the specified path
        405:
          description: Request method not expected (generally should be GET or POST)
        429:
          description: Your app is making too many requests and is being rate limited
        503:
          description: If the response includes the Retry-After header, this means
            your OAuth 1
        507:
          description: User is over Dropbox storage quota
        5xx:
          description: Server error
      tags:
      - Analysis
host: api.pingdom.com
basePath: /