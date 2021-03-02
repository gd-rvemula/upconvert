
  
# upconvert

## Story - Create Table 1:
Define a table with these columns
- UniqueID_Tbl1
- AccountToken
- AmountDue
- DueDate
- MessageText
- PhoneNbr
- emailAddress
- ZipCode
- SaltStriing(A random string)
- PaymentStatus (Success, Fail, NotAttempted)
- NumberContactAttempts 
- ContactStatus (Success, Fail, NotAttempted)

## Story - Create Table 2:
Define a table with these columns
- PmtRefNbr
- UniqueID_Tbl1


## Story - Create Table 3:
- Read a record from table 1
- Generate SHA512 hash from combining AccountToken+AmountDue+DueDate+SaltStrring=PmtRefNbr
- Call an email service
- Insert a record into table2
- Update table 1 with ContactStatus=Success, Increment NumberContactAttempts

## Story - Service 2:
- Receive PmtReffNbr, Last_four_digits_AccountToken, ZipCode
- Read Table2 and then table 1
- Validate Last_four_digits_AccountToken, ZipCode with data from table1, confir they match. If dont, exit
- If they do, send success response

## Story - Service 3:
 - Receive PmtReffNbr, Last_four_digits_AccountToken, ZipCode, Card
   Number, expiry date, CVV2, Name, Address 
 
 - Crate a MOCK payment service with details from above and send a success or failure
   
   
 - Call payments mock service with
   the above details Update the table 1 with payment status = success,
   failure. 
   
# Story 

- Call payment gateway and replace the mock payments service

## Build Screens

 - Screen 1 : Capture input for service 3 and show response
 - 
 
