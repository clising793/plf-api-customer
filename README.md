
# API Documentation

This document provides sample payloads for each of the API endpoints available in this project.

## Website

https://primeleadfinder.com/

## Register User

**Endpoint**: `/customer/auth/register`  
**Method**: POST

**Sample Payload**:
```json
{
    "email": "user@example.com",
    "password": "examplepassword"
}
```

## Login User

**Endpoint**: `/customer/auth/login`  
**Method**: POST

**Sample Payload**:
```json
{
    "email": "user@example.com",
    "password": "examplepassword",
    "remember_me": true
}
```

## Update Password

**Endpoint**: `/customer/user/updatePassword`  
**Method**: POST

**Sample Payload**:
```json
{
    "current_password": "currentpassword",
    "new_password": "newpassword"
}
```

**Headers**:
```json
{
    "Authorization": "Bearer <FIREBASE_ID_TOKEN>"
}
```

## Reset Password

**Endpoint**: `/customer/auth/resetPassword`  
**Method**: POST

**Sample Payload**:
```json
{
    "email": "user@example.com"
}
```

## Buy Subscription

**Endpoint**: `/customer/billing/buySubscription`  
**Method**: POST

**Sample Payload**:
```json
{
    "payment_method_id": "pm_1IvEtH2eZvKYlo2C9XyNTKLK",
    "price_id": "price_1IvEuW2eZvKYlo2Ct6qpF8Uo"
}
```

**Headers**:
```json
{
    "Authorization": "Bearer <FIREBASE_ID_TOKEN>"
}
```

## Cancel Subscription

**Endpoint**: `/customer/billing/cancelSubscription`  
**Method**: POST

**Sample Payload**:
```json
{
    "subscription_id": "sub_1IvEuW2eZvKYlo2Ct6qpF8Uo"
}
```

**Headers**:
```json
{
    "Authorization": "Bearer <FIREBASE_ID_TOKEN>"
}
```

## Get Billing History

**Endpoint**: `/customer/billing/getBillingHistory`  
**Method**: GET

**Headers**:
```json
{
    "Authorization": "Bearer <FIREBASE_ID_TOKEN>"
}
```

**Sample Response**:
```json
[
    {
        "id": "in_1IvF2L2eZvKYlo2CJ9Gs6d0g",
        "amount": 5000,
        "currency": "usd",
        "status": "paid",
        "description": "Monthly subscription for April",
        "date": "2021-04-01"
    },
    {
        "id": "in_1IvF3L2eZvKYlo2CG7Gd7f0k",
        "amount": 5000,
        "currency": "usd",
        "status": "paid",
        "description": "Monthly subscription for May",
        "date": "2021-05-01"
    }
]
```

## Social Login

**Endpoint**: `customer/auth/socialLogin`  
**Method**: POST

**Sample Payload for Google**:
```json
{
    "provider": "google",
    "id_token": "GOOGLE_ID_TOKEN"
}
```

**Sample Payload for LinkedIn**:
```json
{
    "provider": "linkedin",
    "access_token": "LINKEDIN_ACCESS_TOKEN"
}
```

**Headers**:
```json
{
    "Authorization": "Bearer <FIREBASE_ID_TOKEN>"
}
```


```
aws lambda add-permission \
--function-name "arn:aws:lambda:eu-west-1:110847517401:function:plf_customer_api_lambda:dev" \
--source-arn "arn:aws:execute-api:eu-west-1:110847517401:*/*/*" \
--principal apigateway.amazonaws.com \
--statement-id efd27457-04ff-4c3d-80d3-42a188e85d52 \
--action lambda:InvokeFunction```

