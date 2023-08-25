# API : Acknowledge Reservation
API acknowledge channel manager for PMS received reservation

### Endpoint
```text
https://hoteliers.guru/channel-manager/api/pms-connector/ack-reservation
```

### Request JSON Data Structure
```json
{
    "timestamp": "2005-08-01T09:30:47+08:00",
    "transactionID": "abcdefg1234567",
    "username": "username",
    "password": "password",
    "pmsRefID": "pmsdemo",
    "hotelRefID": "RACD000001",
    "reservationList": [
        {
            "uniqueID": "0000001",
            "statusCode": 0,
            "message": "success"
        },
        {
            "uniqueID": "0000002",
            "statusCode": 100,
            "message": "some data invalid type"
        },
        {
            "uniqueID": "0000002",
            "statusCode": 158,
            "message": "not found room type"
        }
    ]
}
```
### Request JSON Data Specification
| Field Name                 | Value Type | Require | Description                                                    |
|----------------------------|------------|---------|----------------------------------------------------------------|
| timestamp                  | String     | Yes     | 2005-08-01T09:30:47+08:00                                      |
| transactionID              | String     | Yes     | UniqID                                                         |
| username                   | String     | Yes     | Username from channel manager                                  |
| password                   | String     | Yes     | Password from channel manager                                  |
| pmsRefID                   | String     | Yes     | PMS Reference ID                                               |
| hotelRefID                 | String     | Yes     | Hotel Reference ID                                             |
| reservationList            | Array      | Yes     | List of result reservation process                             |
| reservationList > uniqueID | String     | Yes     | Item uniq ID from reservation item on retrieve reservation API |
| reservationList > status   | String     | Yes     | Status code of process if 0 = success, otherwise error         |
| reservationList > message  | String     | No      | Note for error case                                            |
---

### Response JSON Data Structure
```json
{
    "transactionID": "abcdefg1234567",
    "statusCode": 0,
    "message": "success"
}
```

### Response JSON Data Specification
| Field Name    | Value Type | Require | Description                                 |
|---------------|------------|---------|---------------------------------------------|
| transactionID | String     | Yes     | UniqID                                      |
| statusCode    | 0...n      | Yes     | status code if 0 = success, otherwise error |
| message       | String     | Yes     | message for processing request data         |
