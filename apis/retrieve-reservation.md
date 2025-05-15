# API : Retrieve Reservation
API for retrieve reservation list from all OTA and use pull base time: 5 - 10 minutes

### Endpoint
```text
https://hoteliers.guru/channel-manager/api/pms-connector/reservation
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
    "searchCondition": {
        "bookingStatus": "book"
    }
}
```

### Request JSON Data Specification
| Field Name                      | Value Type | Require | Description                                                |
|---------------------------------|------------|---------|------------------------------------------------------------|
| timestamp                       | String     | Yes     | 2005-08-01T09:30:47+08:00                                  |
| transactionID                   | String     | Yes     | UniqID                                                     |
| username                        | String     | Yes     | Username from channel manager                              |
| password                        | String     | Yes     | Password from channel manager                              |
| pmsRefID                        | String     | Yes     | PMS Reference ID                                           |
| hotelRefID                      | String     | Yes     | Hotel Reference ID                                         |
| searchCondition                 | Object     | Yes     | search condition object                                    |
| searchCondition > bookingStatus | String     | Yes     | condition booking status "all", "book", "modify", “delete” |

---

### Response JSON Data Structure
```json
{
    "transactionID": "abcdefg1234567",
    "statusCode": 0,
    "message": "success",
    "reservationList": [
        {
            "uniqueID": "00000000001",
            "reservationRefID": "0000002",
            "bookingStatus": "book",
            "createDateTime": "2023-08-07 09:28:02",
            "updateDateTime": "2023-08-07 09:28:02",
            "pos": {
                "channelType": "internet",
                "channelRefID": "000024",
                "channelCode": "HG",
                "channelName": "Hoteliers.Guru",
                "channelReservationID": "OTA-0001"
            },
            "roomList": [
                {
                    "start": "2023-09-10",
                    "end": "2023-09-11",
                    "roomTypeCode": "DR",
                    "ratePlanCode": "BAR",
                    "channelRoomTypeCode": "xxx",
                    "channelRatePlanCode": "xxx",
                    "channelPaymentMethod": "PRE-PAID",
                    "amountInformation": {
                        "currencyCode": "THB",
                        "totalAmount": "1228.0000",
                        "includeBreakfast": 0,
                        "totalAmountDescription": {
                            "baseAmountBeforeTax": "1228.0000",
                            "totalDiscount": "0.0000",
                            "totalExtraAdult": "0.0000",
                            "totalExtraChild": "0.0000",
                            "totalExtraBed": "0.0000",
                            "totalExtraNight": "0.0000",
                            "totalAddonAmount": "0.0000",
                            "totalSurcharge": "0.0000",
                            "totalFeeAmount": "0.0000",
                            "totalTaxAmount": "0.00"
                        }
                    },
                    "rateList": [
                        {
                            "effectiveDate": "2023-09-10",
                            "expireDate": "2023-09-10",
                            "totalAmount": "1228.0000",
                            "pax": 0,
                            "totalAmountDescription": {
                                "baseAmountBeforeTax": "1228.0000",
                                "feeAmount": "0.0000",
                                "taxAmount": "0.0000"
                            }
                        }
                    ],
                    "guestInformation": {
                        "total": 2,
                        "remark": "Adults :  2",
                        "guestList": [
                            {
                                "titleName": "",
                                "firstName": "John",
                                "lastName": "Doe",
                                "email": "john.d@mail.com",
                                "phone": "0988998899",
                                "address": {
                                    "address": "",
                                    "city": "",
                                    "state": "",
                                    "postalCode": "",
                                    "nationalityCode": "",
                                    "nationalityName": "Thai",
                                    "countryCode": "TH",
                                    "countryName": "Thailand"
                                },
                                "note": {
                                    "arrivalTime": "",
                                    "arrivalFlight": ""
                                }
                            }
                        ]
                    },
                    "serviceList": [
                        {
                            "type": "transfer (One way private car (Max. 3 persons) - From airport to hotel Total Adult(s): 1)",
                            "remark": "transfer (One way private car (Max. 3 persons) - From airport to hotel Total Adult(s): 1)",
                            "price": {
                                "currencyCode": "THB",
                                "totalAmountAfterTax": "360.0000",
                                "totalAmountDescription": {
                                    "baseAmountBeforeTax": "360.0000",
                                    "feeAmount": "0.0000",
                                    "taxAmount": "0.0000"
                                }
                            }
                        }
                    ],
                    "specialRequest": "",
                    "remark": ""
                }
            ],
            "serviceList": [
                {
                    "type": "transfer (One way private car (Max. 3 persons) - From airport to hotel Total Adult(s): 1)",
                    "remark": "transfer (One way private car (Max. 3 persons) - From airport to hotel Total Adult(s): 1)",
                    "price": {
                        "currencyCode": "THB",
                        "totalAmountAfterTax": "360.0000",
                        "totalAmountDescription": {
                            "baseAmountBeforeTax": "360.0000",
                            "feeAmount": "0.0000",
                            "taxAmount": "0.0000"
                        }
                    }
                },
                {
                    "type": "tour_phi_phi_island (Speed boat - Apply RoomType Total 1)",
                    "remark": "tour_phi_phi_island (Speed boat - Apply RoomType Total 1)",
                    "price": {
                        "currencyCode": "THB",
                        "totalAmountAfterTax": "0.0000",
                        "totalAmountDescription": {
                            "baseAmountBeforeTax": "0.0000",
                            "feeAmount": "0.0000",
                            "taxAmount": "0.0000"
                        }
                    }
                }
            ],
            "guestList": [
                {
                    "titleName": "",
                    "firstName": "John",
                    "lastName": "Doe",
                    "email": "john.d@mail.com",
                    "phone": "0988998899",
                    "address": {
                        "address": "",
                        "city": "",
                        "state": "",
                        "postalCode": "",
                        "nationalityCode": "",
                        "nationalityName": "Thai",
                        "countryCode": "TH",
                        "countryName": "Thailand"
                    },
                    "note": {
                        "arrivalTime": "19:00",
                        "arrivalFlight": "ADV-429"
                    }
                }
            ],
            "bookingInformation": {
                "remark": "This is remark for booking detail...",
                "totalGuestCount": {
                    "adult": 1,
                    "child": 1,
                    "infant": 0,
                    "total": 2,
                    "remark": "Adults : 1 | Children : 1"
                },
                "customerProfile": {
                    "firstName": "John",
                    "lastName": "Doe",
                    "email": "john.d@mail.com",
                    "phone": "0988998899",
                    "address": {
                        "address": "",
                        "city": "",
                        "state": "",
                        "postalCode": "",
                        "countryCode": "TH"
                    }
                },
                "guarantee": {
                    "paymentCard": {
                        "code": "visa",
                        "number": "4444555566667777",
                        "expireDate": "0518",
                        "cardHolderName": "John Doe"
                    }
                },
                "depositPayment": {
                    "currencyCode": "THB",
                    "amount": "1429.20",
                    "paymentCard": {
                        "code": "",
                        "number": "",
                        "expireDate": "",
                        "cardHolderName": "John"
                    }
                },
                "summaryTotalAmount": {
                    "currencyCode": "THB",
                    "grandTotalAmount": "1588.0000",
                    "includesCommission": "1",
                    "commissionAmount": "0.0000",
                    "cancellationFeeAmount": "0.0000",
                    "grandTotalDescription": {
                        "totalRoomStayBeforeTax": "1228.0000",
                        "totalServiceBeforeTax": "360.0000",
                        "totalDiscount": "0.0000",
                        "totalExtraAdult": "0.0000",
                        "totalExtraChild": "0.0000",
                        "totalExtraBed": "0.0000",
                        "totalExtraNight": "0.0000",
                        "totalEnhancementAmount": "0.0000",
                        "totalSurcharge": "0.0000",
                        "totalFeeAmount": "0.0000",
                        "totalTaxAmount": "0.0000"
                    }
                }
            }
        }
    ]
}
```

### Response JSON Data Specification
| Field Name      | Value Type | Require | Description                                                                                                        |
|-----------------|------------|---------|--------------------------------------------------------------------------------------------------------------------|
| transactionID   | String     | Yes     | UniqID                                                                                                             |
| statusCode      | 0...n      | Yes     | status code if 0 = success, otherwise error                                                                        |
| message         | String     | Yes     | message for processing request data                                                                                |
| reservationList | Array      | Yes     | list of reservation item<br/>See [ReservationItemSpecification](push-reservation.md#ReservationItemSpecification). |

#### ReservationItemSpecification

| Field Name                          | Value Type | Require | Description                                                                                                              |
|-------------------------------------|------------|---------|--------------------------------------------------------------------------------------------------------------------------|
| uniqueID                            | String     | Yes     | Item uniqID for acknowledge reservation API                                                                              |
| reservationRefID                    | String     | Yes     | reservation ID on channel manager system                                                                                 |
| bookingStatus                       | String     | Yes     | booking statuseg. "book", "modify" and "delete"                                                                          |
| createDateTime                      | String     | Yes     | booking create date time on channel                                                                                      |
| updateDateTime                      | String     | No      | booking update date time on channel                                                                                      |
| pos                                 | Object     | Yes     | point of sale for reservation item                                                                                       |
| pos > channelType                   | String     | Yes     | type of channel                                                                                                          |
| pos > channelRefID                  | String     | Yes     | channel referenceID                                                                                                      |
| pos > channelCode                   | String     | Yes     | channel code                                                                                                             |
| pos > channelName                   | String     | Yes     | channel name                                                                                                             |
| pos > channelReservationID          | String     | Yes     | reservationID from OTA                                                                                                   |
| roomList                            | Array      | Yes     | list of room on reservation<br/> See [RoomItemSpecification](push-reservation.md#RoomItemSpecification)                  |
| serviceList                         | Array      | No      | list of service on reservation<br/>See [ServiceItemSpecification](push-reservation.md#ServiceItemSpecification)          |
| guestList                           | Array      | No      | list of guest on reservation<br/>See [GuestItemSpecification](push-reservation.md#GuestItemSpecification)                |
| bookingInformation                  | Object     | Yes     | booking information for reservation<br/>See [BookingInformationSpecific](push-reservation.md#BookingInformationSpecific) |

#### RoomItemSpecification

| Field Name                                                      | Value Type | Require | Description                                                |
|-----------------------------------------------------------------|------------|---------|------------------------------------------------------------|
| start                                                           | String     | Yes     | checkin date                                               |
| end                                                             | String     | Yes     | checkout date                                              |
| roomTypeCode                                                    | String     | Yes     | PMS room type code                                         |
| ratePlanCode                                                    | String     | Yes     | PMS rate plan code                                         |
| channelRoomTypeCode                                             | String     | Yes     | Channel Manager room type code                             |
| channelRatePlanCode                                             | String     | Yes     | Channel Manager rate plan code                             |
| channelPaymentMethod                                            | String     | No      | Channel Payment Method ('PRE-PAID', 'PAY-AT-HOTEL', '')    |
| amountInformation                                               | Object     | Yes     | amount information for room                                |
| amountInformation >currencyCode                                 | String     | Yes     | currency code                                              |
| amountInformation > totalAmount                                 | String     | Yes     | total amount for room                                      |
| amountInformation > includeBreakfast                            | 0, 1, ''   | Yes     | 0 = exclude breakfast, 1 = include breakfast, '' = unknown |
| amountInformation > totalAmountDescription                      | Object     | Yes     | total description                                          |
| amountInformation >totalAmountDescription > baseAmountBeforeTax | String     | Yes     | base amount before TAX                                     |
| amountInformation > totalAmountDescription > totalDiscount      | String     | No      | discount amount                                            |
| amountInformation > totalAmountDescription > totalExtraAdult    | String     | No      | extra adult amount                                         |
| amountInformation > totalAmountDescription > totalExtraChild    | String     | No      | extra child amount                                         |
| amountInformation > totalAmountDescription > totalExtraBed      | String     | No      | extra bed amount                                           |
| amountInformation > totalAmountDescription > totalExtraNight    | String     | No      | extra night amount                                         |
| amountInformation > totalAmountDescription > totalAddonAmount   | String     | No      | addon amount                                               |
| amountInformation > totalAmountDescription > totalSurcharge     | String     | No      | surcharge amount                                           |
| amountInformation > totalAmountDescription > totalFeeAmount     | String     | No      | fee amount                                                 |
| amountInformation > totalAmountDescription > totalTaxAmount     | String     | No      | tax amount                                                 |
| rateList                                                        | Array      | Yes     | rate list for room                                         |
| rateList > effectiveDate                                        | String     | Yes     | rate start date for period                                 |
| rateList > expireDate                                           | String     | Yes     | rate end date for period                                   |
| rateList > totalAmount                                          | String     | Yes     | total amount for period                                    |
| rateList > pax                                                  | String     | No      | PAX for period                                             |
| rateList > totalAmountDescription                               | Object     | Yes     | Total amount information for period                        |
| rateList > totalAmountDescription > baseAmountAfterTax          | String     | Yes     | base amount after tax for period                           |
| rateList > totalAmountDescription > feeAmount                   | String     | No      | fee amount for period                                      |
| rateList > totalAmountDescription > taxAmount                   | String     | No      | tax amount for period                                      |
| guestInformation                                                | Object     | No      | guest information for room                                 |
| guestInformation > adult                                        | 0..n       | No      | total adult for room                                       |
| guestInformation > child                                        | 0..n       | No      | total child for room                                       |
| guestInformation > infant                                       | 0..n       | No      | total infant for room                                      |
| guestInformation > total                                        | 0..n       | No      | total guest for room                                       |
| guestInformation > remark                                       | String     | No      | remark                                                     |
| guestInformation > guestList                                    | Array      | No      | guest list for room                                        |
| serviceList                                                     | Array      | No      | service list for room                                      |
| specialRequest                                                  | String     | No      | special request                                            |
| remark                                                          | String     | No      | remark                                                     |

#### ServiceItemSpecification

| Field Name                                           | Value Type | Require | Description                                                                                   |
|------------------------------------------------------|------------|---------|-----------------------------------------------------------------------------------------------|
| type                                                 | String     | No      | service type eg. extra_bed, extra_person, surcharge, meal, service, tour, event, extra, other |
| remark                                               | String     | No      | remark for service item                                                                       |
| effectiveDate                                        | String     | No      | service start date                                                                            |
| expireDate                                           | String     | No      | service expire date                                                                           |
| price                                                | Object     | No      | price for service item                                                                        |
| price > currencyCode                                 | String     | No      | currency code                                                                                 |
| price > totalAmountAfterTax                          | String     | No      | total amount after tax                                                                        |
| price > totalAmountDescription                       | Object     | No      | total amount description object                                                               |
| price > totalAmountDescription > baseAmountBeforeTax | String     | No      | base amount before tax                                                                        |
| price > totalAmountDescription > feeAmount           | String     | No      | fee amount                                                                                    |
| price > totalAmountDescription > taxAmount           | String     | No      | tax amount                                                                                    |

#### GuestItemSpecification

| Field Name                | Value Type | Require | Description                    |
|---------------------------|------------|---------|--------------------------------|
| titleName                 | String     | No      | title name e.g. mr., ms., mrs. |
| firstName                 | String     | No      | first name                     |
| lastName                  | String     | No      | last name                      |
| email                     | String     | No      | email                          |
| phone                     | String     | No      | phone                          |
| address                   | Object     | No      | address data                   |
| address > address         | String     | No      | address                        |
| address > city            | String     | No      | city                           |
| address > state           | String     | No      | state or province              |
| address > postalCode      | String     | No      | postal code                    |
| address > nationalityCode | String     | No      | nationality code               |
| address > nationalityName | String     | No      | nationality name               |
| address > countryCode     | String     | No      | country code                   |
| address > countryName     | String     | No      | country name                   |
| note                      | Object     | No      | note                           |
| note > arrivalTime        | String     | No      | arrival time                   |
| note > arrivalFlight      | String     | No      | arrival flight                 |

#### BookingInformationSpecific

| Field Name                                                          | Value Type | Require | Description                                                                                                              |
|---------------------------------------------------------------------|------------|---------|--------------------------------------------------------------------------------------------------------------------------|
| remark                                                              | String     | No      | remark for reservation item                                                                                              |
| totalGuestCount                                                     | Object     | No      | total guest count information                                                                                            |
| totalGuestCount > adult                                             | 0..n       | No      | total adult                                                                                                              |
| totalGuestCount > child                                             | 0..n       | No      | total child                                                                                                              |
| totalGuestCount > infant                                            | 0..n       | No      | total infant                                                                                                             |
| totalGuestCount > total                                             | 0..n       | No      | total guest                                                                                                              |
| totalGuestCount > remark                                            | String     | No      | remark for guest                                                                                                         |
| customerProfile                                                     | Object     | Yes     | profile of customer                                                                                                      |
| customerProfile > firstName                                         | String     | Yes     | first name                                                                                                               |
| customerProfile > lastName                                          | String     | Yes     | last name                                                                                                                |
| customerProfile > email                                             | String     | Yes     | email                                                                                                                    |
| customerProfile > phone                                             | String     | Yes     | phone                                                                                                                    |
| customerProfile > address                                           | Object     | Yes     | address data                                                                                                             |
| customerProfile > address > address                                 | String     | Yes     | address                                                                                                                  |
| customerProfile > address > city                                    | String     | Yes     | city                                                                                                                     |
| customerProfile > address > state                                   | String     | Yes     | state or province                                                                                                        |
| customerProfile > address > postalCode                              | String     | Yes     | postal code                                                                                                              |
| customerProfile > address > countryCode                             | String     | Yes     | country code                                                                                                             |
| guarantee                                                           | Object     | No      | guarantee information                                                                                                    |
| guarantee > paymentCard                                             | Object     | No      | payment card information                                                                                                 |
| guarantee > paymentCard > code                                      | String     | No      | card code                                                                                                                |
| guarantee > paymentCard > number                                    | String     | No      | card number                                                                                                              |
| guarantee > paymentCard > expireDate                                | String     | No      | card expire date format MMYY                                                                                             |
| guarantee > paymentCard > cardHolderName                            | String     | No      | card holder name                                                                                                         |
| depositPayment                                                      | Object     | No      | deposit payment information                                                                                              |
| depositPayment > currencyCode                                       | String     | No      | currency code                                                                                                            |
| depositPayment > amount                                             | String     | No      | deposit amount                                                                                                           |
| depositPayment > paymentCard                                        | Object     | No      | payment card information                                                                                                 |
| depositPayment > paymentCard > code                                 | String     | No      | card code                                                                                                                |
| depositPayment > paymentCard > number                               | String     | No      | card number                                                                                                              |
| depositPayment > paymentCard > expireDate                           | String     | No      | card expire date format MMYY                                                                                             |
| depositPayment > paymentCard > cardHoldername                       | String     | No      | card holder name                                                                                                         |
| summaryTotalAmount                                                  | Object     | Yes     | summary total amount for reservation                                                                                     |
| summaryTotalAmount > currencyCode                                   | String     | Yes     | currency code                                                                                                            |
| summaryTotalAmount > grandTotalAmount                               | String     | Yes     | grand total amount                                                                                                       |
| summaryTotalAmount > includesCommission                             | String     | No      | "1" = total amount is include commission<br/>"0" = total amount not is include commission<br/>"" (empty value) = Unknown |
| summaryTotalAmount > commissionAmount                               | String     | No      | commission amount                                                                                                        |
| summaryTotalAmount > cancellationFeeAmount                          | String     | No      | cancellation fee amount                                                                                                  |
| summaryTotalAmount > grandTotalDescription                          | Object     | Yes     | grand total amount information                                                                                           |
| summaryTotalAmount > grandTotalDescription > totalRoomStayBeforeTax | String     | Yes     | total room stay amount before tax                                                                                        |
| summaryTotalAmount > grandTotalDescription > totalServiceBeforeTax  | String     | No      | total service before tax                                                                                                 |
| summaryTotalAmount > grandTotalDescription > totalDiscount          | String     | No      | total discount amount                                                                                                    |
| summaryTotalAmount > grandTotalDescription > totalExtraAdult        | String     | No      | total extra adult amount                                                                                                 |
| summaryTotalAmount > grandTotalDescription > totalExtraChild        | String     | No      | total extra child amount                                                                                                 |
| summaryTotalAmount > grandTotalDescription > totalExtraBed          | String     | No      | total extra bed amount                                                                                                   |
| summaryTotalAmount > grandTotalDescription > totalExtraNight        | String     | No      | total extra night                                                                                                        |
| summaryTotalAmount > grandTotalDescription > totalEnhancementAmount | String     | No      | total enhancement amount                                                                                                 |
| summaryTotalAmount > grandTotalDescription > totalSurcharge         | String     | No      | total surcharge amount                                                                                                   |
| summaryTotalAmount > grandTotalDescription > totalFeeAmount         | String     | No      | total fee amount                                                                                                         |
| summaryTotalAmount > grandTotalDescription > totalTaxAmount         | String     | No      | total tax amount                                                                                                         |
