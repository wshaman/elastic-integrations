                            
## JAMF PRO INTEGRATION
 - This connector integrates with the JAMF Pro dashboard to retrieve and visualize inventory data.
 - Inventory data includes: Hardware, Jamf Software data, operating system, locations.


## Data streams

 * __inventory__ provides Inventory data for computers. Includes: hardware, OS, etc. Saves each device as a separate log record.  
 This data stream utilizes `/v1/computers-inventory` endpoint from JAMF Pro API.

## Requirements


* __JAMF Pro Active License and OAuth2 Credentials:__
For running integration an active license for JAMF Pro is required. Additionally, OAuth2 credentials obtained via the API App are necessary. These credentials are essential to authenticate and establish a secure connection with the API.

* __JAMF API Application Permissions:__
To ensure proper functionality and access to pertinent features, the API application must have the following permissions:

- _Read Computer Inventory Collection_: Access to read inventory data from the computer collection.
- _Read Computers_: Allows the application to access and read data from computers.
- It is crucial that all these prerequisites are met to facilitate a smoother integration process and optimized application experience.

## Setup

* __Establishing A Connection to JAMF Pro:__ Setting up a successful connection with JAMF Pro involves creating an application and configuring the integration.  


## Step 1: Create an Application in JAMF Pro:

To create a connection to JAMF Pro, an [application must be created](https://learn.jamf.com/en-US/bundle/jamf-pro-documentation-current/page/API_Roles_and_Clients.html) first. Credentials generated during this process are required for the subsequent steps.

## Step 2: Integration Setup:

Once the application is created and credentials are obtained, proceed with setting up the integration. For step-by-step instructions on how to set up an integration, see the
[Getting started](https://www.elastic.co/guide/en/welcome-to-elastic/current/getting-started-observability.html) guide.This guide includes comprehensive step-by-step instructions for configuring Kibana to connect with JAMF Pro, to initializing data feeds. Follow each step meticulously for a successful and seamless integration.

## Logs

### Inventory

By default these sections are included into JAMF API query:
 - _GENERAL_
 - _HARDWARE_
 - _OPERATING_SYSTEM_
 Others can be included in connector settings 
 Sample events:
```json
{
  "events":[
    {
      "message":{
        "id":"3",
        "udid":"5982CE36-4526-580B-B4B9-ECC6782535BC",
        "general":{
          "name":"acme-C07DM3AZQ6NV",
          "lastReportedIp":"10.122.26.87",
          "lastIpAddress":"10.122.26.87",
          "jamfBinaryVersion":"11.4.1-t1712591696",
          "platform":"Mac",
          "barcode1":"null",
          "remoteManagement":{
            "managed":true
          },
          "supervised":false,
          "mdmCapable":{
            "capable":false,
            "capableUsers":[
              
            ]
          },
          "reportDate":"2024-06-19T15:54:37.692Z",
          "lastContactTime":"2024-04-18T14:26:51.514Z",
          "lastEnrolledDate":"2023-02-22T10:46:17.199Z",
          "initialEntryDate":"2024-06-19",
          "site":{
            "id":"-1",
            "name":"None"
          },
          "itunesStoreAccountActive":false,
          "enrolledViaAutomatedDeviceEnrollment":false,
          "userApprovedMdm":false,
          "declarativeDeviceManagementEnabled":false,
          "managementId":"1a59c510-b3a9-41cb-8afa-3d4187ac60d0",
          "extensionAttributes":[
            
          ]
        }
      }
    }
  ]
}
```