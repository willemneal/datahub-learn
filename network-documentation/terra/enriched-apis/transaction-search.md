---
description: Learn how to use the Transaction Search API on Terra
---

# Transaction Search

Test out our Transaction Search API today with [**DataHub**](https://datahub.figment.io/sign_up?service=terra)! 

{% api-method method="post" host="https://terra--search.datahub.figment.io/transactions\_search" path=" " %}
{% api-method-summary %}
transactions\_search
{% endapi-method-summary %}

{% api-method-description %}
Transaction Search allows users to filter and query by account, transaction type, and date range. Users can also search by memo field and logs. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="network" type="string" required=true %}
Network identifier to search in. In this case, `terra`
{% endapi-method-parameter %}

{% api-method-parameter name="account" type="array" required=false %}
The account identifier to look for. This searches for all account IDs which exist in transaction, including senders, recipients, validators, feeders, etc. 
{% endapi-method-parameter %}

{% api-method-parameter name="after\_height" type="integer" required=false %}
Gets all transactions bigger than given height. Has to be bigger than BeforeHeight
{% endapi-method-parameter %}

{% api-method-parameter name="after\_time" type="string" required=false %}
The time of transaction \(if not given by chain API, the same as block\) 
{% endapi-method-parameter %}

{% api-method-parameter name="before\_height" type="integer" required=false %}
Gets all transactions lower than given height. Has to be lesser than AfterHeight
{% endapi-method-parameter %}

{% api-method-parameter name="before\_time" type="string" required=false %}
The time of transaction \(if not given by the chain API, the same as block\) 
{% endapi-method-parameter %}

{% api-method-parameter name="block\_hash" type="string" required=false %}
The hash of block to get transaction from
{% endapi-method-parameter %}

{% api-method-parameter name="chain\_ids" type="array" required=false %}
ChainID to search in. In this case, `columbus-3` or `columbus-4`
{% endapi-method-parameter %}

{% api-method-parameter name="epoch" type="string" required=false %}
Epoch of the transaction
{% endapi-method-parameter %}

{% api-method-parameter name="hash" type="string" required=false %}
The hash of the transaction
{% endapi-method-parameter %}

{% api-method-parameter name="height" type="integer" required=false %}
Height of the transactions to get
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
Limit how many requests to get in one requests
{% endapi-method-parameter %}

{% api-method-parameter name="memo" type="string" required=false %}
Sets full text search for memo field
{% endapi-method-parameter %}

{% api-method-parameter name="offset" type="integer" required=false %}
Offset the next X number of records
{% endapi-method-parameter %}

{% api-method-parameter name="receiver" type="array" required=false %}
Looks for transactions that include given account IDs
{% endapi-method-parameter %}

{% api-method-parameter name="sender" type="array" required=false %}
Looks for transactions that include given account IDs
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="array" required=false %}
The list of types of transactions \(see below for full list of parameters\)
{% endapi-method-parameter %}

{% api-method-parameter name="with\_raw" type="boolean" required=false %}
Include base64 raw request in search response
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Success response
{% endapi-method-response-example-description %}

```javascript
{
  "block_hash": "string",
  "chain_id": "string",
  "created_at": "2020-10-15T20:38:09.017Z",
  "epoch": "string",
  "events": [
    {
      "id": "string",
      "kind": "string",
      "sub": [
        {
          "action": "string",
          "additional": {
            "additionalProp1": [
              "string"
            ],
            "additionalProp2": [
              "string"
            ],
            "additionalProp3": [
              "string"
            ]
          },
          "amount": {
            "additionalProp1": {
              "currency": "string",
              "exp": 0,
              "numeric": {},
              "text": "string"
            },
            "additionalProp2": {
              "currency": "string",
              "exp": 0,
              "numeric": {},
              "text": "string"
            },
            "additionalProp3": {
              "currency": "string",
              "exp": 0,
              "numeric": {},
              "text": "string"
            }
          },
          "completion": "2020-10-15T20:38:09.017Z",
          "error": {
            "message": "string"
          },
          "module": "string",
          "node": {
            "additionalProp1": [
              {
                "detail": {
                  "contact": "string",
                  "description": "string",
                  "name": "string",
                  "website": "string"
                },
                "id": "string"
              }
            ],
            "additionalProp2": [
              {
                "detail": {
                  "contact": "string",
                  "description": "string",
                  "name": "string",
                  "website": "string"
                },
                "id": "string"
              }
            ],
            "additionalProp3": [
              {
                "detail": {
                  "contact": "string",
                  "description": "string",
                  "name": "string",
                  "website": "string"
                },
                "id": "string"
              }
            ]
          },
          "nonce": "string",
          "recipient": [
            {
              "account": {
                "detail": {
                  "contact": "string",
                  "description": "string",
                  "name": "string",
                  "website": "string"
                },
                "id": "string"
              },
              "amounts": [
                {
                  "currency": "string",
                  "exp": 0,
                  "numeric": {},
                  "text": "string"
                }
              ]
            }
          ],
          "sender": [
            {
              "account": {
                "detail": {
                  "contact": "string",
                  "description": "string",
                  "name": "string",
                  "website": "string"
                },
                "id": "string"
              },
              "amounts": [
                {
                  "currency": "string",
                  "exp": 0,
                  "numeric": {},
                  "text": "string"
                }
              ]
            }
          ],
          "type": [
            "string"
          ]
        }
      ]
    }
  ],
  "gas_used": 0,
  "gas_wanted": 0,
  "hash": "string",
  "height": 0,
  "id": [
    0
  ],
  "memo": "string",
  "raw": [
    0
  ],
  "time": "2020-10-15T20:38:09.017Z",
  "transaction_fee": [
    {
      "currency": "string",
      "exp": 0,
      "numeric": {},
      "text": "string"
    }
  ],
  "updated_at": "2020-10-15T20:38:09.017Z",
  "version": "string"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Bad parameters sent 
{% endapi-method-response-example-description %}

```javascript
{
  "error": "Something bad happened"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}
Not acceptable content type
{% endapi-method-response-example-description %}

```javascript
{
  "error": "Something bad happened"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Internal/Other server error while processing request
{% endapi-method-response-example-description %}

```javascript
{
  "error": "Something bad happened"

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### **Transaction Types**

List of currently supporter transaction types in cosmos-worker are \(listed by modules\):

| **Module** | Type |
| :--- | :--- |
| **bank** | `multisend` , `send`  |
| **crisis** | `verify_invariant` |
| **distribution** | `withdraw_validator_commission`, `set_withdraw_address`, `withdraw_delegator_reward`, `fund_community_pool` |
| **evidence** | `submit_evidence` |
| **gov** | `deposit`, `vote`, `submit_proposal` |
| **slashing** | `unjail` |
| **staking** | `begin_unbonding`, `edit_validator`, `create_validator` , `delegate`, `begin_redelegate` |
| **internal** | `error` |



If you need help with this API or simply want to share with other builders, you can [**join our community today**](https://discord.gg/fszyM7K)!

