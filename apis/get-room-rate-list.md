# API : Get Room Rate List

api for retrieve all room and rate list on channel manager system

### Endpoint URL
```text
https://hoteliers.guru/channel-manager/api/pms-connector/room-rate-list
```

### Request JSON Data Structure
```json
{
     "timestamp": "2005-08-01T09:30:47+08:00",
     "transactionID": "abcdefg1234567",
     "username": "username",
     "password": "password",
     "pmsRefID": "pmsdemo",
     "hotelRefID": "RACD000001"
}
```

### Request JSON Data Specification
| Field Name    | Value Type | Require | Description                   |
|---------------|------------|---------|-------------------------------|
| timestamp     | String     | Yes     | 2005-08-01T09:30:47+08:00     |
| transactionID | String     | Yes     | UniqID                        |
| username      | String     | Yes     | Username from channel manager |
| password      | String     | Yes     | Password from channel manager |
| pmsRefID      | String     | Yes     | PMS Reference ID              |
| hotelRefID    | String     | Yes     | Hotel Reference ID            |

---

### Response JSON Data Structure
```json
{
    "transactionID": "abcdefg1234567",
    "statusCode": 0,
    "message": "success",
    "rateList": [
        {
            "code": "BAR-01",
            "name": "Room only",
            "description": "this is room only"
        },
        {
            "code": "ABF-01",
            "name": "Breakfast",
            "description": "this is room and breakfast"
        }
    ],
    "roomList": [
        {
            "code": "SUP-01",
            "name": "Superior",
            "description": "this room is superior",
            "allowExtraBed": 1,
            "allowExtraPerson": 1,
            "rateIncludeList": [
                {
                    "code": "BAR-01"
                }
            ]
        },
        {
            "code": "DLX-01",
            "name": "Deluxe",
            "description": "this room is deluxe",
            "allowExtraBed": 1,
            "allowExtraPerson": 0,
            "rateIncludeList": [
                {
                    "code": "ABF-01",
                    "rateLinkList": [
                        "ABF-01"
                    ]
                }
            ]
        }
    ]
}
```

### Response JSON Data Structure
| Field Name                                | Value Type | Require  | Description                                   |
|-------------------------------------------|------------|----------|-----------------------------------------------|
| timestamp                                 | String     | Yes      | 2005-08-01T09:30:47+08:00                     |
| statusCode                                | 0...n      | Yes      | status code if 0 = success, otherwise error   |
| message                                   | String     | Yes      | message for processing request data           |
| rateList                                  | Array      | Yes      | List of rate object on channel manager system |
| rateList > code                           | String     | Yes      | code for rate object                          |
| rateList > name                           | String     | Yes      | name for rate object                          |
| rateList > description                    | String     | Yes      | description for rate object                   |
| roomList                                  | Array      | Yes      | List of room object on channel manager system |
| roomList > code                           | String     | Yes      | code for room object                          |
| roomList > name                           | String     | Yes      | name for room object                          |
| roomList > description                    | String     | Yes      | description for room object                   |
| roomList > allowExtraBed                  | 0, 1       | No       | allow this room extra bed                     |
| roomList > allowExtraPerson               | 0, 1       | No       | allow this room extra person                  |
| roomList > rateIncludeList                | Array      | Yes      | List of rate object in this room object       |
| roomList > rateIncludeList > code         | String     | Yes      | rate code available on room object            |
| roomList > rateIncludeList > rateLinkList | Array      | No       | List of rate to link this rate code           |
