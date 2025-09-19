# Status Code
| Code                           | Description                                                                                                                                     |
|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| 0                              | Success                                                                                                                                         |
| 1000                           | Authentication Error                                                                                                                            |
|                                |                                                                                                                                                 |
| 2xxx : Parameter Required      |                                                                                                                                                 |
| 2010                           | timestamp does not exist                                                                                                                        |
| 2011                           | timestamp invalid value type                                                                                                                    |
| 2020                           | transactionID does not exist                                                                                                                    |
| 2030                           | pmsRefID does not exist                                                                                                                         |
| 2040                           | hotelRefID does not exist                                                                                                                       |
| 2100                           | periodList does not exist                                                                                                                       |
| 2110                           | start does not exist                                                                                                                            |
| 2111                           | start invalid value type                                                                                                                        |
| 2120                           | end does not exist                                                                                                                              |
| 2121                           | end invalid value type                                                                                                                          |
| 2200                           | applyDayOfWeek does not exist                                                                                                                   |
| 2201                           | applyDayOfWeek invalid value type                                                                                                               |
| 2300                           | data does not exist                                                                                                                             |
| 2301                           | roomAvailable invalid value type                                                                                                                |
| 2302                           | roomAmountAfterTax invalid value type                                                                                                           |
| 2303                           | roomStatus invalid value type                                                                                                                   |
| 2304                           | closeToArrival invalid value type                                                                                                               |
| 2305                           | closeToDeparture invalid value type                                                                                                             |
| 2306                           | stopSaleByRoom invalid value type                                                                                                               |
| 2307                           | stopSaleByRate invalid value type                                                                                                               |
| 2308                           | minimumNightStay invalid value type                                                                                                             |
| 2309                           | maximumNightStay invalid value type                                                                                                             |
| 2310                           | exactNightStay invalid value type                                                                                                               |
| 2311                           | minimumStayArrival invalid value type                                                                                                           |
| 2312                           | maximumStayArrival invalid value type                                                                                                           |
| 2313                           | exactStayArrival invalid value type                                                                                                             |
| 2314                           | advancePurchase invalid value type                                                                                                              |
| 2315                           | cutOffDate invalid value type                                                                                                                   |
| 2316                           | promotionBlackout invalid value type                                                                                                            |
| 2317                           | extraAdult invalid value type                                                                                                                   |
| 2318                           | extraChild invalid value type                                                                                                                   |
| 2319                           | cancelDays invalid value type                                                                                                                   |
| 2320                           | penaltyDays invalid value type                                                                                                                  |
| 2321                           | inclusion invalid value type                                                                                                                    |
| 2500                           | searchCondition does not exist                                                                                                                  |
| 2501                           | bookingStatus does not exist                                                                                                                    |
| 2502                           | bookingStatus invalid value                                                                                                                     |
|                                |                                                                                                                                                 |
| 3xxx : Process Parameter Error |                                                                                                                                                 |
| 3011                           | pmsRefID not found                                                                                                                              |
| 3012                           | hotelRefID not found                                                                                                                            |
| 3013                           | hotelRefID not match pmsRefID                                                                                                                   |
| 3014                           | periodList is empty                                                                                                                             |
| 3021                           | invalid start date                                                                                                                              |
| 3022                           | invalid end date                                                                                                                                |
| 3023                           | start date great than end date                                                                                                                  |
| 3024                           | roomTypeCode not found                                                                                                                          |
| 3025                           | ratePlanCode not found                                                                                                                          |
| 3027                           | Date greater than maximum date, Maximum date is today date + 3 years, Ex. today date is '2025-09-19', Maximum date is greater than '2028-09-19' |
|                                |                                                                                                                                                 |
| 5xxx : Process Business Error  |                                                                                                                                                 |
| 5001                           | roomTypeCode not found for roomAvailable                                                                                                        |
| 5002                           | roomTypeCode or rateTypeCode or both not found for roomAmountAfterTax                                                                           |
| 5003                           | roomTypeCode not found for roomStatus                                                                                                           |
| 5004                           | roomTypeCode or rateTypeCode or both not found for closeToArrival                                                                               |
| 5005                           | roomTypeCode or rateTypeCode or both not found for closeToDeparture                                                                             |
| 5006                           | roomTypeCode not found for stopSaleByRoom                                                                                                       |
| 5007                           | roomTypeCode or rateTypeCode or both not found for stopSaleByRate                                                                               |
| 5008                           | roomTypeCode or rateTypeCode or both not found for minimumNightStay                                                                             |
| 5009                           | roomTypeCode or rateTypeCode or both not found for maximumNightStay                                                                             |
| 5010                           | roomTypeCode or rateTypeCode or both not found for exactNightStay                                                                               |
| 5011                           | roomTypeCode or rateTypeCode or both not found for minimumStayArrival                                                                           |
| 5012                           | roomTypeCode or rateTypeCode or both not found for maximumStayArrival                                                                           |
| 5013                           | roomTypeCode or rateTypeCode or both not found for exactStayArrival                                                                             |
| 5014                           | roomTypeCode or rateTypeCode or both not found for advancePurchase                                                                              |
| 5015                           | roomTypeCode or rateTypeCode or both not found for cutOffDate                                                                                   |
| 5016                           | roomTypeCode or rateTypeCode or both not found for promotionBlackout                                                                            |
| 5017                           | roomTypeCode or rateTypeCode or both not found for extraAdult                                                                                   |
| 5018                           | roomTypeCode or rateTypeCode or both not found for extraChild                                                                                   |
| 5019                           | roomTypeCode or rateTypeCode or both not found for cancelDays                                                                                   |
| 5020                           | roomTypeCode or rateTypeCode or both not found for penaltyDays                                                                                  |
| 5021                           | roomTypeCode or rateTypeCode or both not found for inclusion                                                                                    |