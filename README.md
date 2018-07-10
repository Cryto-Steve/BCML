# BCML
# Bitcoin Cash Merchant Listings  (BCML)

## Protocol

* Actions are saved using OP_RETURN
* All actions are prefixed with a protocol identifier (0x00434d4c) before the action code
* Text is UTF8 encoded
* Longitude and latitude are multiplied by 100000 and converted to a 32 bit (4 byte) integer
* Online only listings use 0xffffffff for both longitude and latitude.

###### Example:
The action below would set the location to 40.64948, -74.05533 and the Merchant Name to “New York City”

```
OP_RETURN 0x00434d4c01 003E06B4FF8F00234E657720596F75726B2043697479
```

| Action | Prefix | Data |
|--------|--------|------|
| Create Merchant | 0x01 | Longitude(4), Latitude(4), MerchantName(206) |
| Add URL | 0x02 | Txhash(30), Url(181) |
| Add Address1 | 0x03 | Txhash(30), Address1(181) |
| Add Address2 | 0x04 | Txhash(30), Address2(181) |
| Add Address3 | 0x05 | Txhash(30), Address3(181) |
| Add Address4 | 0x06 | Txhash(30), Address4(181) |
| Add Phone | 0x07 | Txhash(30), Phone(181) |
| Add Category | 0x0a | Txhash(30), Category(181) |
| Add Review | 0x0b | Txhash(30), Rating(1), Review(177) |
| Report | 0x0c | Txhash(30), ReportType(1), Identity(177) |


Report Types

| Code | Type |
|----|----|
| 0x01 | Verified Correct |
| 0x02 | Business Closed |
| 0x03 | Not accepting BCH |

Additional discussion on Yours.org:  https://www.yours.org/content/decentralized-listing-of-bitcoin-cash-merchants--bcml----protocol-prop-488a16a8418a


bitcoincash:qpz4hkg4z0xqny326k90pqvdud57h6m0agk0pj6e62
