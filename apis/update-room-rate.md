# API : Update Room / Rate
api for update allotment and rate

### Endpoint
```text
https://hoteliers.guru/channel-manager/api/pms-connector/update-room-rate
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
    "periodList": [
        {
            "start": "2010-01-01",
            "end": "2010-01-14",
            "roomTypeCode": "TK1X",
            "ratePlanCode": "BAR1N",
            "applyDayOfWeek": {
                "mon": 1,
                "tue": 1,
                "wed": 1,
                "thu": 1,
                "fri": 1,
                "sat": 1,
                "sun": 1
            },
            "data": {
                "roomAvailable": "15",
                "roomAmountAfterTax": "2500.00",
                "closeToArrival": 0,
                "closeToDeparture": 0,
                "stopSaleByRoom": 1,
                "stopSaleByRate": 0,
                "minimumNightStay": "disable",
                "maximumNightStay": "9",
                "exactNightStay": "9",
                "minimumStayArrival": "0",
                "maximumStayArrival": "9",
                "exactStayArrival": "disable",
                "advancePurchase": "disable",
                "cutOffDate": "0",
                "promotionBlackout": "0",
                "extraAdult": "disable",
                "extraChild": "disable",
                "cancelDays": "0",
                "penaltyDays": "0",
                "inclusion": "rate inclusion description"
            }
        }
    ]
}
```

### Request JSON Data Specification
| Field Name    | Value Type | Require | Description                                                                                  |
|---------------|------------|---------|----------------------------------------------------------------------------------------------|
| timestamp     | String     | Yes     | 2005-08-01T09:30:47+08:00                                                                    |
| transactionID | String     | Yes     | UniqID                                                                                       |
| username      | String     | Yes     | Username from channel manager                                                                |
| password      | String     | Yes     | Password from channel manager                                                                |
| pmsRefID      | String     | Yes     | PMS Reference ID                                                                             |
| hotelRefID    | String     | Yes     | Hotel Reference ID                                                                           |
| periodList    | Array      | Yes     | period update data List<br>* <span style="color: orange">**PeriodList Specification**</span> |

- <span style="color: orange">**PeriodList Specification**</span>

| Field Name     | Value Type           | Require | Description                                                                                                   |
|----------------|----------------------|---------|---------------------------------------------------------------------------------------------------------------|
| start          | String : Date Format | Yes     | start date of period eg."2015-07-02"                                                                          |
| end            | String : Date Format | Yes     | end date of period eg. "2015-07-15"                                                                           |
| roomTypeCode   | String               | No      | room type code                                                                                                |
| ratePlanCode   | String               | No      | rate plan code                                                                                                |
| applyDayOfWeek | Object               | Yes     | data group for apply day of week<br/>* <span style="color: orange">**Apply Day Of Week Specification**</span> |
| data           | Object               | Yes     | data group for update data<br/>* <span style="color: orange">**Data Specification**</span>                    |

- <span style="color: orange">**Apply Day Of Week Specification**</span>

| Field Name | Value Type | Require | Description         |
|------------|------------|---------|---------------------|
| mon        | 0, 1       | Yes     | apply for monday    |
| tue        | 0, 1       | Yes     | apply for tuesday   |
| wed        | 0, 1       | Yes     | apply for wednesday |
| thu        | 0, 1       | Yes     | apply for thursday  |
| fri        | 0, 1       | Yes     | apply for friday    |
| sat        | 0, 1       | Yes     | apply for saturday  |
| sun        | 0, 1       | Yes     | apply for sunday    |

- <span style="color: orange">**Data Specification**</span>

| Field Name         | Value Type                  | Require  | Description                                                                 |
|--------------------|-----------------------------|----------|-----------------------------------------------------------------------------|
| roomAvailable      | String : 0...n              | No       | room available                                                              |
| roomAmountAfterTax | String : Decimal            | No       | room amount include tax                                                     |
| closeToArrival     | 0, 1                        | No       | flag to close to arrival                                                    |
| closeToDeparture   | 0, 1                        | No       | flag to close to departure                                                  |
| stopSaleByRoom     | 0, 1                        | No       | flag to stop sale by room (1 = close sell, 0 = open sell)                   |
| stopSaleByRate     | 0, 1                        | No       | flag to stop sale by rate (1 = close sell, 0 = open sell)                   |
| minimumNightStay   | String : "disable", 0...n   | No       | number for minimum night stay "disable" for cancel minimum night stay       |
| maximumNightStay   | String : "disable", 0...n   | No       | number for maximum night stay "disable" for cancel maximum night stay       |
| exactNightStay     | String : "disable", 0...n   | No       | number for exact night stay "disable" for cancel exact night stay           |
| minimumStayArrival | String : "disable", 0...n   | No       | number for minimum stay arrival "disable" for cancel minimum stay arrival   |
| maximumStayArrival | String : "disable", 0...n   | No       | number for maximum stay arrival "disable" for cancel maximum stay arrival   |
| exactStayArrival   | String : "disable", 0...n   | No       | number for exact stay arrival "disable" for cancel exact stay arrival       |
| advancePurchase    | string : "disable", 0...n   | No       | number for advance purchase "disable" for cancel advance purchase           |
| cutOffDate         | string : "disable", 0...n   | No       | number for cut off date "disable" for cancel cut off date                   |
| promotionBlackout  | 0, 1                        | No       | flag to promotion blackout                                                  |
| extraAdult         | String : "disable", Decimal | No       | decimal for extra adult rate "disable" for cancel extra adult rate          |
| extraChild         | String : "disable", Decimal | No       | decimal for extra child rate "disable" for cancel extra child rate          |
| cancelDays         | String : "disable", 0...n   | No       | number for cancel days "disable" for cancel "cancel days"                   |
| penaltyDays        | String : "disable", 0...n   | No       | number for penalty days "disable" for cancel penalty days                   |
| inclusion          | String                      | No       | string for inclusion description "disable" for cancel inclusion description |

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
