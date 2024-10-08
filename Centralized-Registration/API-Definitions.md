# Centralized Registration API Definitions
## API Definitions 
### Base Specifications & URLs
Following the OpenAPI specifications, APIs can be written in JSON, SQL, or YAML. For consistency and readability these definitions are written in JSON due to it's ease of integration with Azure SQL.
#### Base URLs
These are placeholders, will be changed once provisioned.
- Production: https://alaska.api.gov
- Dev: https://alaska.devapi.gov

#### Version History
##### Current Version: 0.1.0
###### Notes on Engage Portal JSON Output Versioning:

Due to the format of the Engage Portal JSON output, there are currently no versions tags. This could become an issue if the JSON fields are updated. There are a few solutions, it should be a priority to have the vendor add a `version` field within their JSON output which can be checked before any parsing or manipulation for the API request body. If this isn't feasible, a 'quick and dirty' method would be to write a quick comparison function within the parser to check the intended fields with the JSON file recieved.

### Constraints
Depending on security requirements and limitations of the various systems this API will interface with, it is recommended to consider implementing resource field constraints. This can assist in debugging as well as provide more clarification to developers and users when they run into unexpected behaviour.

`authorized` - True/false whether the requesting user is authorized to view the coorisponding resource

`writable` - True/false whether the field is writable

`canAdd` - True/False whether the field can have additional items added (i.e. adding a new household member)

`canRemove` - True/false whether the field can have items removed (i.e. removing a household member)

### API Definitions
#### High Level Overview:
`GET /v1/cases`

**Examples**

`GET /v1/cases?limit=10`

`GET /v1/cases?batchId=8675309`

`GET /v1/cases?batchId=8675309&limit=10`

**Description:** Get all cases the user is authorized to view, response is a comma seperated array

**Required Parameters:** `limit` - the number of cases to return, the default is 5

**Response:**

````
HTTP/1.1 200-OK
Content-Type: application/json

{
    "message": "Get case information",
    <JSON Array of case information>

}
````


`GET /v1/cases/{caseId}`

**Description:** Get case by caseId

**Required Parameters:** `caseId` - The ID of a case

**Response:**

````
HTTP/1.1 200-OK
Content-Type: application/json

{
    "message": "Get case information",
    <JSON Object of Case information>
}
````

`POST /v1/cases`

**Description:** Create a new case

**Request Body:** `NewCase` JSON object

**Response:**

````
HTTP/1.1 201-Created
Content-Type: application/json

{
    "message": "New case created",

}
````

`PUT /v1/cases/{caseId}`

**Description:** Update a case

**Required Parameters:** `caseId` - the case ID to be updated

**Request Body:** `Case` fields to be updated

**Response:**

````
HTTP/1.1 200-OK
Content-Type: application/json

{
    "message": "Successfully updated case",

}
````
#### JSON API Definitions
A few notes, the current definition has most fields included from the registration application, but not all due to the sheer length of the application. This took the most important fields to use as an example of the structure and those not included can easily be added durinmg implementation. Also, most of the `required` elements have been left blank. This is due to the unknown of how EIS will behave due to missing information. These can be adjusted during implementation to require some or all of the relevant `Case` fields. 

The `delete` method has been intentionally left out of these definitions, but can be added later if necessary. It should also be noted that JSON is a data-only format, comments have been included to provide more clarification but are not syntactically correct. As mentioned previously, the `host` field is a placeholder and can be easily updated once provisioned.

This API definition includes schemas for logical groupings of relevant case data within the file, during implementation it is recommended that these schemas be split into their own files for readability and ease of future changes.
```
{
  "info": {
    "version": "0.1.0",
    "title": "Centralized Registration API",
    "description": "An API that can create and update case registration applications",
  },
  "host": "alaska.api.gov",
  "basePath": "/v1",
  "description": "Base host location for production"
  "schemes": [
    "http"
  ],
  "consumes": [
    "application/json"
  ],
  "produces": [
    "application/json"
  ],
  "paths": {
    "/cases": {
      "get": {
        "description": "Returns all cases from the system that the user has access to",
        "operationId": "findCases",
        "produces": [
          "application/json"
        ],
        "parameters": [
          {
            # These are query parameters to filter and search by i.e. by batchId, address, city, etc
            "name": "tags",
            "in": "query",
            "description": "tags to filter by",
            "required": false,
            "type": "array",
            "items": {
              "type": "string"
            },
            "collectionFormat": "csv"
          },
          {
            # Limit the amount of cases returned, default is 5
            "name": "limit",
            "in": "query",
            "description": "maximum number of results to return",
            "required": "false",
            "default": "5",
            "type": "integer",
            "format": "int32"
          }
        ],
        "responses": {
          "200": {
            "description": "A JSON array of cases",
            "schema": {
              "type": "array",
              "items": {
                "$ref": "#/schemas/Case"
              }
            }
          },
          "default": {
            "description": "unexpected error",
            "schema": {
              "$ref": "#/schemas/ErrorModel"
            }
          }
        }
      },
      "post": {
        "description": "Creates a new case.  Duplicates are not allowed",
        "operationId": "addCase",
        "produces": [
          "application/json"
        ],
        "parameters": [
          {
            "name": "caseId",
            "in": "body",
            "description": "Case to be created",
            "required": true,
            "schema": {
              "$ref": "#/schemas/NewCase"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "Successful case creation",
            "schema": {
              "$ref": "#/schemas/Case"
            }
          },
          "default": {
            "description": "unexpected error",
            "schema": {
              "$ref": "#/schemas/ErrorModel"
            }
          }
        }
      }
    },
    "/cases/{caseId}": {
      "get": {
        "description": "Returns a case based on a case ID",
        "operationId": "findCaseById",
        "produces": [
          "application/json"
        ],
        "parameters": [
          {
            "name": "caseId",
            "in": "path",
            "description": "ID of case to return",
            "required": true,
            "type": "integer",
            "format": "int64"
          }
        ],
        "responses": {
          "200": {
            "description": "Get Case response",
            "schema": {
              "$ref": "#/schemas/Case"
            }
          },
          "default": {
            "description": "unexpected error",
            "schema": {
              "$ref": "#/schemas/ErrorModel"
            }
          }
        }
      },
      "put": {
        "description": "Update Case",
        "operationId": "updateCase",
        "produces": [
          "application/json"
        ],
        "parameters": [
          {
            "name": "caseId",
            "in": "path",
            "description": "ID of case to update",
            "required": true,
            "schema": {
              "$ref": "#/schemas/Case"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "Case updated successfully",
            "schema": {
              "$ref": "#/schemas/Case"
            }
          },
          "default": {
            "description": "unexpected error",
            "schema": {
              "$ref": "#/schemas/ErrorModel"
            }
          }
      }
    }
  },
  "schemas": {
    "Case": {
      "type": "object",
      "allOf": [
        {
          "$ref": "#/schemas/NewCase"
        },
        {
          "required": [
            "caseId"
          ],
          "properties": {
            "caseId": {
              "type": "integer",
              "format": "int64"
            }
          }
        }
      ]
    },
    "NewCase": {
        "type": "object",
        "required": [
          "caseId"
        ],
        "properties": {
          "caseId": {
            "type": "integer"
          },
          "date-created": {
            "type": "string"
          },
          "date-updated": {
            "type": "string"
          },
          "ip-address": {
            "type": "string"
          },
          "status": {
            "type": "string"
          },
          "batch-Id": {
            "type": "string"
          },
          "report-filter-user-groups": {
            "type": "string"
          },
          "englishPrimary": {
            "type": "bool"
          },
          "englishProficeny": {
            "type": "bool"
          },
          "primaryLanguage": {
            "type": "string"
          },
          "appForSelf": {
            "type": "bool"
          },
          "authorizedRepStatus": {
            "type": "bool"
          },
          "authorizedRep": {
            "$ref": "#/schemas/Person"
          },
          "primaryApplicantInfo": {
            "$ref": "#/schemas/Person"
          },
          "householdMembers": {
            "$ref": "#/schemas/householdMembers"
          },
          "employmentStatus": {
            "oneOf": [
                {
            "$ref": "#/schemas/employmentInfo"
                },{
            "$ref": "#/schemas/selfEmploymentInfo"
                }
            ]
          }
          "additionalIncomeInfo": {
            "$ref": "#/schemas/additionalIncomeInfo"
          },
          "propertyOwnedInfo": {
            "$ref": "#/schemas/additionalIncomeInfo"
          },
          "liquidAssetOwnedInfo": {
            "$ref": "#/schemas/additionalIncomeInfo"
          },
        }
      },
      "personInfo": {
        "type": "object", 
        "required": [
                "id"
            ],
            "properties": {
                "id": {
                "type": "integer",
                "format": "int64"
                },
                "firstName": {
                    "type": "string"
                },
                "lastName": {
                    "type": "string"
                },
                "middleName": {
                    "type": "string"
                },
                "suffix": {
                    "type": "string"
                },
                "aliasFirstName": {
                    "type": "string"
                },
                "aliasLastName": {
                    "type": "string"
                },
                "relationship": {
                    "type": "string"
                },
                "primaryPhoneNumber": {
                    "type": "integer"
                },
                "alternateNumber": {
                    "type": "integer"
                },
                "primaryAddress": {
                    "$ref": "#/schemas/Address"
                },
                "mailingAddress": {
                    "$ref": "#/schemas/Address"
                },
                "emailAddress": {
                    "type": "string"
                },
                "alternateEmailAddress": {
                    "type": "string"
                }, 
                "textOptIn": {
                    "type": "bool"
                },
                "emailOptIn": {
                    "type": "bool"
                },
                "homelessStatus": {
                    "type": "bool"
                },
                "grossDeductiuonEligibility": {
                    "type": "bool"
                },
                "cashAvailableStatus": {
                    "type": "bool"
                },
                "monthlyCostOverGross": {
                    "type": "bool"
                }
            }
        }
    },
    "householdMember": {
            "type": "object", 
            "required": [
                     "id"
            ],
            "properties":{
                "id": {
                "type": "integer",
                "format": "int64"
                },
                "firstName": {
                    "type": "string"
                },
                "lastName": {
                    "type": "string"
                },
                "middleName": {
                    "type": "string"
                },
                "suffix": {
                    "type": "string"
                },
                "aliasFirstName": {
                    "type": "string"
                },
                "aliasLastName": {
                    "type": "string"
                },
                "relationship": {
                    "type": "string"
                },
                "martialStatus": {
                    "type": "string"
                },
                "sex": {
                    "type": "string"
                },
                "ssn": {
                    "type": "integer"
                },
                "dob": {
                    "type": "string"
                },
                "pregnancyStatus": {
                    "type": "bool"
                },
                "disabilityStatus": {
                    "type": "bool"
                },
                "citizenshipStatus": {
                    "type": "bool"
                },
                "immigrationStatus": {
                    "type": "bool"
                },
                "immigrationType": {
                    "type": "string"
                },
                "immigrationNumber": {
                    "type": "integer"
                },
                "educationStatus": {
                    "type": "bool"
                },
                "educationType": {
                    "type": "string"
                },
                "ethnicity": {
                    "type": "string"
                },
                "race": {
                    "type": "string"
                }
            }
    },
    "employmentInfo": {
        "type": "object",
        "required": [

        ],
        "properties": {
            "id": {
             "type": "integer",
             "format": "int64"   
            },
            "householdMemberNumber": {
             "type": "integer",
             "format": "int64"   
            },
            "householdMemberFullName": {
                "type": "string"
            },
            "employerName": {
                "type": "string"
            },
            "employerPhone": {
                "type": "string"
            },
            "employerAddress": {
                "$ref": "#/schemas/Address"
            },
            "supervisorFirstName": {
                "type": "string"
            },
            "supervisorLastName": {
                "type": "string"
            },
            "wages": {
                "type": "integer"
            },
            "hours": {
                "type": "integer"
            },
            "payFrequency": {
                "type": "string"
            }
        }
    },
    "selfEmploymentInfo": {
        "type": "object",
        "required": [

        ],
        "properties": {
            "id": {
             "type": "integer",
             "format": "int64"   
            },
            "householdMemberNumber": {
             "type": "integer",
             "format": "int64"   
            },
            "householdMemberFullName": {
                "type": "string"
            },
            "businessType": {
                "type": "string"
            },
            "frequency": {
                "type": "string"
            },
            "currentIncome": {
                "type": "string"
            },
            "nextIncome": {
                "type": "string"
            },
            "currentExpense": {
                "type": "integer"
            },
            "nextExpense": {
                "type": "integer"
            }
        }
    },
    "additionalIncomeInfo": {
        "type": "object",
        "properties": {
            "id": {
                "type": "integer"
            },
            "householdMemberNumber": {
                "type": "integer"
            },
            "householdMemberFullName": {
                "type": "string"
            },
            "incomeType": {
                "type": "string"
            },
            "incomeFrequency": {
                "type": "string"
            },
            "currentMonthlyAmount": {
                "type": "integer"
            },
            "nextMonthlyAmount": {
                "type": "string"
            }
        }
    },
    "propertyOwned"Info: {
        "type": "object",
        "properties": {
            "id": {
                "type": "integer"
            },
            "householdMemberNumber": {
                "type": "integer"
            },
            "householdMemberFullName": {
                "type": "string"
            },
            "propertyType": {
                "type": "string"
            },
            "propertyValue": {
                "type": "string"
            },
            "propertyAmountOwed": {
                "type": "integer"
            },
            "propertyCoOwned": {
                "type": "bool"
            }
        }
    },
    "liquidAssetOwnedInfo": {
        "type": "object",
        "properties": {
            "id": {
                "type": "integer"
            },
            "householdMemberNumber": {
                "type": "integer"
            },
            "householdMemberFullName": {
                "type": "string"
            },
            "assetType": {
                "type": "string"
            },
            "assetLocation": {
                "type": "string"
            },
            "assetAccountNumber": {
                "type": "integer"
            },
            "nextMontassetCoOwned": {
                "type": "bool"
            }
        }
    },
    "vehicleOwnedInfo": {
        "type": "object",
        "properties": {
            "id": {
                "type": "integer"
            },
            "householdMemberNumber": {
                "type": "integer"
            },
            "householdMemberFullName": {
                "type": "string"
            },
            "vehicleType": {
                "type": "string"
            },
            "vehicleMake": {
                "type": "string"
            },
            "vehicleModel": {
                "type": "integer"
            },
            "vehicleYear": {
                "type": "integer"
            },
            "vehicleUse": {
                "type": "string"
            },
            "vehicleValue": {
                "type": "integer"
            },
            "vehicleOwed": {
                "type": "integer"
            },
            "vehicleCoOwned": {
                "type": "bool"
            }
        }
    },
    "transferredResourceInfo": {
        "type": "object",
        "properties": {
            "id": {
                "type": "integer"
            },
            "householdMemberNumber": {
                "type": "integer"
            },
            "householdMemberFullName": {
                "type": "string"
            },
            "resourceType": {
                "type": "string"
            },
            "resourceChangeStatus": {
                "type": "string"
            },
            "resourceChangeDate": {
                "type": "integer"
            },
            "resourceBalance": {
                "type": "bool"
            }
        }
    },
    "Address": {
        "type": "object",
        "properties": {
            "street1": {
                "type": "string"
            },
            "street2": {
                "type": "string"
            },
            "city": {
                "type": "string"
            },
            "state": {
                "type": "string"
            },
            "zipcode": {
                "type": "integer"
            },
            "country": {
                "type": "string"
            }
        }
    },
      # This can be tailored as implemented, including standardized respomses for content not found etc.
      "ErrorModel": {
        "type": "object",
        "required": [
          "code",
          "message"
        ],
        "properties": {
          "code": {
            "type": "integer",
            "format": "int32"
          },
          "message": {
            "type": "string"
          }
        }
      }
}
```
### Transforming JSON into Azure SQL
This can be done either as an alternate JSON response format or as a standalone process within the workflow. OPENJSON is an Azure SQL table-value function that pasrses and iterates through JSON text. Below is an example of transforming a JSON array into a set of rows, which can then be inserted into a standard table. A query can also automatically load and transform a JSON input. More information can be found [HERE.](https://learn.microsoft.com/en-us/azure/azure-sql/database/json-features?view=azuresql)
```
CREATE PROCEDURE InsertCase(@cases nvarchar(max))
AS BEGIN

    -- Can specify all fields to be returned or use OPENJSON function to do this programatically
    insert into Cases(caseId, date-created, date-updated...) 
    select caseId,
        date-created,
        date-updated,
    FROM OPENJSON (@cases)
     WITH (
        caseId varchar(n)-- char size of caseId
        date-created datetime,
        date-updated datetime, -- Case fields list, left out due to length
     )
END
```
##### Notes on ADABAS Integration:
Due to the current schema of ADABASE, the Azure SQL DB will need to make some adjustments to field names to allow for API integration. The field names within ADABAS can be non-descriptive, it's recommended to use aliases of the ADABAS fields with the the descriptive SQL field names for integration. 
