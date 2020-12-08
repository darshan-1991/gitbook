---
description: Sub page
---

# Sub-Page

{% tabs %}
{% tab title="Tab 1" %}
![](.gitbook/assets/584815a8cef1014c0b5e4973.png)
{% endtab %}

{% tab title="Tab 2" %}
```markup
{
    "proxy": {
        "basePath": "/v1/stores",
        "name": "StoreLocator",
        "flows": {
            "flow": [
                {
                    "name": "getStoreList",
                    "verb": "GET",
                    "description": "Get list of Itorix store ID's",
                    "path": "/list",
                    "targetName": "",
                    "targetOperation": ""
                },
                {
                    "name": "SearchStoresOnAddress",
                    "verb": "GET",
                    "description": "Search store based on address",
                    "path": "/search",
                    "targetName": "",
                    "targetOperation": ""
                },
                {
                    "name": "SearchStoresOnGeoLocation",
                    "verb": "GET",
                    "description": "Search Store with Geo Location",
                    "path": "/",
                    "targetName": "",
                    "targetOperation": ""
                }
            ]
        },
        "description": "StoreLocator",
        "buildProxyArtifact": "StoreLocator",
        "buildProxyArtifactType": "swagger",
        "oas": "2.0",
        "version": "v1",
        "revision": 1
    },
    "target": [
        {
            "basePath": "/v1/stores",
            "description": "StoreLocator_target",
            "name": "StoreLocator",
            "flows": {
                "flow": [
                    {
                        "condition": "(target.route.operation = &quot;getStoreList&quot;)",
                        "name": "getStoreList",
                        "verb": "GET",
                        "description": "getStoreList",
                        "path": "/list"
                    },
                    {
                        "condition": "(target.route.operation = &quot;SearchStoresOnAddress&quot;)",
                        "name": "SearchStoresOnAddress",
                        "verb": "GET",
                        "description": "SearchStoresOnAddress",
                        "path": "/search"
                    }
                ]
            },
            "buildTargetArtifact": "StoreLocator",
            "buildTargetArtifactType": "swagger",
            "oas": "2.0"
        }
    ],
    "proxySCMDetails": {
        "scmSource": "Bitbucket/Git/Gitlab",
        "hostUrl": "https://bitbucket.org/sudhakaralaparthi/storelocator.git",
        "reponame": "storelocator",
        "branch": "master",
        "commitMessage": "Itorix APP commit"
    },
    "policyTemplates": [
        {
            "type": "trafficmanagement",
            "name": "TrafficManagement",
            "description": "Traffic management policies let you configure cache, control traffic quotas and spikes, set concurrent rate limits, and so on.",
            "policies": [
                {
                    "name": "spikearrest",
                    "displayName": "SpikeArrest",
                    "description": "Spike Arrest policy protects against traffic spikes.",
                    "enabled": true
                },
                {
                    "name": "quotaatproductlevel",
                    "displayName": "Quota at Productlevel",
                    "description": "Quota policy to configure the number of request messages that an API proxy allows over a period of time.",
                    "enabled": false
                },
                {
                    "name": "responsecache",
                    "displayName": "Response Cache",
                    "description": "Caches data from a backend resource, reducing the number of requests to the resource.",
                    "enabled": false
                }
            ]
        },
        {
            "type": "security",
            "name": "Security",
            "description": "Security policies let you control access to your APIs with OAuth, API key validation, and other threat protection features.",
            "policies": [
                {
                    "name": "Authentication",
                    "displayName": "AuthN",
                    "description": "Authentication is establishing the your identity.",
                    "enabled": false
                },
                {
                    "name": "Authorization",
                    "displayName": "AuthZ & AuthN",
                    "description": "Authorization is establishing your privilege",
                    "enabled": false
                },
                {
                    "name": "AAA_With_Basic_Auth",
                    "displayName": "AAA With Basic Authentication",
                    "description": "Authorization is establishing your privilege",
                    "enabled": false
                },
                {
                    "name": "BasicAuthentication",
                    "displayName": "Basic Authentication ",
                    "description": "Enables you to use lightweight Basic Authentication for last-mile security.",
                    "enabled": false
                },
                {
                    "name": "PingFederate",
                    "displayName": "PingFederate",
                    "description": "PingFederate serves as a global authentication authority.",
                    "enabled": false
                },
                {
                    "name": "decrypt_pcitoken",
                    "displayName": "Decrypt PCIToken",
                    "description": "Decrypt Pcitoken",
                    "enabled": false
                },
                {
                    "name": "validate_xguid",
                    "displayName": "Validate XGUID",
                    "description": "Validate XGUID",
                    "enabled": false
                },
                {
                    "name": "oauth",
                    "displayName": "OAuth",
                    "description": "Secure APIs with OAuth",
                    "enabled": false
                },
                {
                    "name": "cors",
                    "displayName": "CORS",
                    "description": "Enable API's to support CORS requests",
                    "enabled": true
                },
                {
                    "name": "accesscontrol",
                    "displayName": "Access Control",
                    "description": "Lets you allow or deny access to your APIs by specific IP addresses. ",
                    "enabled": false
                },
                {
                    "name": "verifyapikey",
                    "displayName": "Verify API Key",
                    "description": "Lets you enforce verification of API keys at runtime.",
                    "enabled": false
                },
                {
                    "name": "jwt",
                    "displayName": "JWT",
                    "description": "Lets you enforce JWT verification for your proxy.",
                    "enabled": false
                }
            ]
        },
        {
            "type": "logging",
            "name": "Logging",
            "description": "Logging policies allow you to log the request data and response data.",
            "policies": [
                {
                    "name": "LOG_Req_Res_Err_v1",
                    "displayName": "Log Request Response",
                    "description": "Lets you to log the proxy data during runtime.",
                    "enabled": false
                },
                {
                    "name": "log",
                    "displayName": "Logger Handler",
                    "description": "Lets you to log the proxy data during runtime.",
                    "enabled": false
                },
                {
                    "name": "activitylog",
                    "displayName": "Activity Log",
                    "description": "Lets you to log the proxy data during runtime.",
                    "enabled": false
                }
            ]
        },
        {
            "type": "mediation",
            "name": "Mediation",
            "description": "Mediation policies let you perform message transformation, parsing, and validation, as well as raise faults and alerts.",
            "policies": [
                {
                    "name": "XFM_Req_Scrub_WSSE_Header_v1",
                    "displayName": "Remove WSSE Security Header",
                    "description": "Remove WSSE security header from SOAP API Request",
                    "enabled": false
                },
                {
                    "name": "XFM_Req_Scrub_ESBAuth_Header_v1",
                    "displayName": "Remove ServiceMetadata Request",
                    "description": "Remove ESB-Auth header from the Rest API Request",
                    "enabled": false
                },
                {
                    "name": "XFM_Req_Scrub_BasicAuth_Header_v1",
                    "displayName": "Remove Authentication Header ",
                    "description": "Remove Authentication header from the Rest API Request",
                    "enabled": false
                },
                {
                    "name": "XFM_Req_Scrub_MetaData_Header_v1",
                    "displayName": "Remove ESB-Auth Header",
                    "description": "Remove the ServiceMetadataRequest from the SOAP request",
                    "enabled": false
                },
                {
                    "name": "jsontoxml",
                    "displayName": "JSON To XML",
                    "description": "Converts messages from the JavaScript Object Notation (JSON) format to extensible markup language (XML) ",
                    "enabled": false
                },
                {
                    "name": "xmltojson",
                    "displayName": "XML To JSON",
                    "description": "Converts messages from the extensible markup language (XML) fromat to JavaScript Object Notation (JSON).",
                    "enabled": false
                }
            ]
        },
        {
            "type": "threatprotection",
            "name": "Threat Management",
            "description": "Threat management allow you to scan the incoming payloads for any miscellaneous content in the request.",
            "policies": [
                {
                    "name": "THR_Threat_SOAP_v1",
                    "displayName": "SOAP Threat Detection",
                    "description": "Threat detection for SOAP based services",
                    "enabled": false
                },
                {
                    "name": "THR_REST_XML_v1",
                    "displayName": "XML Threat Detection",
                    "description": "XML threat detection for REST based services",
                    "enabled": false
                },
                {
                    "name": "THR_REST_JSON_v1",
                    "displayName": "JSON Threat Detection",
                    "description": "JSON threat detection for REST based services",
                    "enabled": false
                },
                {
                    "name": "jsoninjection",
                    "displayName": "JSON Injection",
                    "description": "Enable payload scan for JSON content",
                    "enabled": false
                },
                {
                    "name": "xssinjection",
                    "displayName": "XSS Injection",
                    "description": "Scans XSS threats in payloads",
                    "enabled": false
                },
                {
                    "name": "xmlinjection",
                    "displayName": "XML Injection",
                    "description": "Enable payload scan for XML content",
                    "enabled": false
                }
            ]
        },
        {
            "type": "routing",
            "name": "Target Server Routing Handler",
            "description": "Endpoint routing for KPHC services & non KPHC services",
            "policies": [
                {
                    "name": "RTE_KPHC_Endpoint_Lookup_v1",
                    "displayName": "Endpoint Routing For KPHC Services",
                    "description": "Endpoint Routing For KPHC services",
                    "enabled": false
                },
                {
                    "name": "RTE_Endpoint_Lookup_v1",
                    "displayName": "Endpoint Routing For non KPHC Services",
                    "description": "Endpoint Routing For non KPHC Services",
                    "enabled": false
                }
            ]
        },
        {
            "type": "MessageValidation",
            "name": "Message Validation",
            "description": "Validate SOAP/REST Request and Response",
            "policies": [
                {
                    "name": "Schema_Validation_Request",
                    "displayName": "Schema Validation Request",
                    "description": "Schema Validation Request",
                    "enabled": false
                },
                {
                    "name": "Schema_Validation_Response",
                    "displayName": "Schema Validation Response",
                    "description": "Schema Validation Response",
                    "enabled": false
                },
                {
                    "name": "Schema_Validation_Error",
                    "displayName": "Schema Validation Error",
                    "description": "Schema Validation Error",
                    "enabled": false
                },
                {
                    "name": "Schema_Validation_MTOM",
                    "displayName": "Schema Validation MTOM",
                    "description": "Schema Validation MTOM",
                    "enabled": false
                }
            ]
        }
    ]
}
```
{% endtab %}
{% endtabs %}

| Name | Notes |
| :--- | :--- |
| Darshan | Test |
| Mahesh | Test 1 |

