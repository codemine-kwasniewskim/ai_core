# Demo Code
Below page shows SAP-RPT1 foundation model by using REST API.

## Prerequisite
- Bruno installation https://www.usebruno.com/downloads
- Import Bruno collection
- Foundation model SAP-RPT1 deployed in AI Core ([deployment steps](https://github.com/codemine-kwasniewskim/ai_core/blob/main/deployment.md))
- Example from SAP https://help.sap.com/docs/sap-ai-core/sap-ai-core-service-guide/example-payloads-for-inferencing-sap-rpt-1?locale=en-US

# SAP RPT-1 model deployment
- check the existence of foundation models in AI Core
- if you have own AI CORE instanc you can try to deploy RPT1 Model and use the below endpoint
<code>GET {{AI-API-URL}}/v2/lm/scenarios/foundation-models/models</code>
<img width="1677" height="678" alt="image" src="https://github.com/user-attachments/assets/ab37ba47-9eee-4929-a214-633bd92fbed2" />
- if you want to use SAP RPT-1 playground https://rpt.cloud.sap/
  
## Authorization token
Please use token from https://rpt.cloud.sap/ eiher your own generated 

# API Payload Inferencing
ref. https://help.sap.com/docs/sap-ai-core/sap-ai-core-service-guide/example-payloads-for-inferencing-sap-rpt-1?locale=en-US

Limitations
| Constraint                 | Limit        |
|----------------------------|------------------- |
  | Maximum rows               | 2,073 rows per       |
  | Maximum columns            | 50 columns per            |
  | Maximum cell length        | 1,000 characters       |
  | Maximum column name length | 100 characters        
          |

## URL
URL: <code> {{$DEPLOYMENT_URL}}/api/predict </code>
## HEADER

| Header     | Value |
| ------------- | ------------- |
| Authorization      | Bearer $AUTH_TOKEN       |
| AI-Resource-Group |  Resource group     |
| $DEPLOYMENT_URL     | The deployment URL for your generative AI model        |

## Example dumy data
Example data table:
 | ID | COLUMN1 | COLUMN2 | COLUMN3 |
  | --- | --- | --- | --- |
  | 1 | dummty1_1 | dymmy1_2 | dymmy1_3 |
  | 2 | dummty2_1 | dummty2_2 | dummty2_3 |
  | 3 | dummty3_1 | dymmy3_2 | dymmy3_3 |
  | 4 | dummty4_1 | dummty4_2 | dummty4_3 |
  | 5 | dummty5_1 | dymmy5_2 | dymmy5_3 |
  | 6 | dummty6_1 | dummty6_2 | **[PREDICT]** |        
  | 7 | dummty7_1 | dymmy7_2 | dymmy7_3 |
  | 8 | dummty8_1 | dummty8_2 | dummty8_3 |
  
## Request BODY **(by rows)**

```JSON
{
    "prediction_config": {
        "target_columns": [
            {
                "name": "COLUMN3",
                "prediction_placeholder": "[PREDICT]",
                "task_type": "regression"
            }
        ]
    },
    "index_column": "ID",
    "rows": [
          {
      "ID": 1,
      "COLUMN1": "dummy1_1",
      "COLUMN2": "dummy1_2",
      "COLUMN3": "dummy1_3"
    },
    {
      "ID": 2,
      "COLUMN1": "dummy2_1",
      "COLUMN2": "dummy2_2",
      "COLUMN3": "dummy2_3"
    },
    {
      "ID": 3,
      "COLUMN1": "dummy3_1",
      "COLUMN2": "dummy3_2",
      "COLUMN3": "dummy3_3"
    },
    {
      "ID": 4,
      "COLUMN1": "dummy4_1",
      "COLUMN2": "dummy4_2",
      "COLUMN3": "dummy4_3"
    },
    {
      "ID": 5,
      "COLUMN1": "dummy5_1",
      "COLUMN2": "dummy5_2",
      "COLUMN3": "dummy5_3"
    },
    {
      "ID": 6,
      "COLUMN1": "dummy6_1",
      "COLUMN2": "dummy6_2",
      "COLUMN3": "[PREDICT]"
    },
    {
      "ID": 7,
      "COLUMN1": "dummy7_1",
      "COLUMN2": "dummy7_2",
      "COLUMN3": "dummy7_3"
    },
    {
      "ID": 8,
      "COLUMN1": "dummy8_1",
      "COLUMN2": "dummy8_2",
      "COLUMN3": "dummy8_3"
    }
    ],
    "data_schema": {
       "ID": {
            "dtype": "string"
        },
      "COLUMN1": {
            "dtype": "string"
        },
        "COLUMN2": {
            "dtype": "string"
        },
        "COLUMN3": {
            "dtype": "string"
        }     
    }
}
```

<img width="1673" height="862" alt="SAP RPT-1 prediction by rows" src="https://github.com/user-attachments/assets/056a2bb4-3fed-4b8e-995d-44ffb4750730" />

There is confidence NULL which does not give us any confidence fro the data provided.

## Request BODY **(by columns)**
  
```JSON
{
  "prediction_config": {
    "target_columns": [
      {
        "name": "COLUMN3",
        "prediction_placeholder": "[PREDICT]",
        "task_type": "classification"
      }
    ]
  },
  "index_column": "ID",
  "columns":  {
    "ID": [1, 2, 3, 4, 5, 6, 7, 8],
    "COLUMN1": [
      "dummty1_1",
      "dummty2_1",
      "dummty3_1",
      "dummty4_1",
      "dummty5_1",
      "dummty6_1",
      "dummty7_1",
      "dummty8_1"
    ],
    "COLUMN2": [
      "dymmy1_2",
      "dummty2_2",
      "dymmy3_2",
      "dummty4_2",
      "dymmy5_2",
      "dummty6_2",
      "dymmy7_2",
      "dummty8_2"
    ],
    "COLUMN3": [
      "dymmy1_3",
      "dummty2_3",
      "dymmy3_3",
      "dummty4_3",
      "dymmy5_3",
      "[PREDICT]",
      "dymmy7_3",
      "dummty8_3"
    ]
  }

## Request BODY Parquet file
TODO
  "data_schema": {
      "PRODUCT": {
          "dtype": "string"
      }
  }
}
```
