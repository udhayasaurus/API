---
id: TTD Editor
title: Trade Desk API
---

# TradeDesk

In our platform, advertisers are your clients.
Campaigns, creatives, tracking tags, and data elements all belong under an advertiser. This section will detail all that API calls involved in creating and maintaining an advertiser.

## TradeDesk Collection [/advertiser]


### Creating a New Advertiser [POST/advertiser]

Creating an advertiser is the next step towards building out a campaign and ad groups within the platform.

This POST call will create a new advertiser with the requisite parameters and any optional parameters that you would like to add in addition.

#### Parameters
The following table details the required parameter and attribute values. Supported optional attributes will also be listed here when available.
| Parameter Name                               | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PartnerId                                    | The ID of the partner who owns this advertiser. Your partner ID will be provided when you are granted access to the API                                                                                                                                                                                                                                                                                                                                                                                                |
| AdvertiserName                               | The name of the advertiser                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| AttributionClickLookbackWindowInSeconds      | When The Trade Desk performs click attribution for the advertiser’s conversions, this is the amount of time (in seconds) that will be considered for attribution purposes.                                                                                                                                                                                                                                                                                                                                             |
| AttributionImpressionLookbackWindowInSeconds | When The Trade Desk performs impression attribution for the advertiser’s conversions, this is the amount of time (in seconds) that will be considered for attribution purposes                                                                                                                                                                                                                                                                                                                                         |
| ClickDedupWindowInSeconds                    | When The Trade Desk performs click attribution for your conversions, similar clicks will be considered duplicates if they are within this window. Set to zero to disable click deduplication                                                                                                                                                                                                                                                                                                                           |
| ConversionDedupWindowInSeconds               | When The Trade Desk performs impression attribution for your conversions, similar conversions will be considered duplicates if they are within this window. Set to zero to disable conversion deduplication.                                                                                                                                                                                                                                                                                                           |
| DefaultRightMediaOfferTypeId                 | Sets the default Right Media Offer Type (creative category) to use on new creatives. If an existing advertiser does not have a default offer type set, this property will be omitted from the API's response.Once set, new creatives that do not have an offer type specified on creation will inherit this offer type. Creatives that do not have a Right Media Offer Type will not be able to buy Right Media inventory until one is assigned.See the Right Media Offer Type API for a full list of possible values. |
| IndustryCategoryId                           | An ID identifying the industry category to which this ad group belongs. This property is required as of version 3 of the API. If an existing advertiser does not have an industry category set, this property will be omitted from the API's response. See the Category API for a full list of possible values.                                                                                                                                                                                                        |
| Domain Address                               | The domain address (including http:// or https://) for the advertiser.This attribute is an optional, nullable attribute to the API for backwards compatibility. It will be converted to a required, non-nullable attribute in a future release. You will be notified in advance of this change.                                                                                                                                                                                                                        |


+ Parameters
    +   PartnerID (string)

        The ID of the partner who owns this advertiser.

+ Attributes
    +   Advertiser (Advertiser[object])




+ Request (application/json)

            {
  "PartnerId": "sample string 1",
  "AdvertiserId": "sample string 1",
  "AdvertiserName": "sample string 1",
  "Description": "sample string 1",
  "CurrencyCode": "USD",
  "AttributionClickLookbackWindowInSeconds": 1,
  "AttributionImpressionLookbackWindowInSeconds": 1,
  "ClickDedupWindowInSeconds": 1,
  "ConversionDedupWindowInSeconds": 1,
  "DefaultRightMediaOfferTypeId": 1,
  "IndustryCategoryId": 1,
  "Keywords": [
    "sample string 1",
    "sample string 2",
    "sample string 3"
  ],
  "Availability": "Archived",
  "LogoURL": "sample string 1",
  "DomainAddress": "sample string 1",
  "CustomLabels": [
    {
      "CustomLabelId": "sample string 1"
    },
    {
      "CustomLabelId": "sample string 1"
    },
    {
      "CustomLabelId": "sample string 1"
    }
  ],
  "AssociatedBidLists": [
    {
      "BidListId": "sample string 1",
      "IsEnabled": true,
      "IsDefaultForDimension": true,
      "BidListSource": "ManualRecommendation",
      "BidListAdjustmentType": "TargetList",
      "BidListDimensions": [
        "HasAdFormatId",
        "HasAdFormatId",
        "HasAdFormatId"
      ]
    },
    {
      "BidListId": "sample string 1",
      "IsEnabled": true,
      "IsDefaultForDimension": true,
      "BidListSource": "ManualRecommendation",
      "BidListAdjustmentType": "TargetList",
      "BidListDimensions": [
        "HasAdFormatId",
        "HasAdFormatId",
        "HasAdFormatId"
      ]
    },
    {
      "BidListId": "sample string 1",
      "IsEnabled": true,
      "IsDefaultForDimension": true,
      "BidListSource": "ManualRecommendation",
      "BidListAdjustmentType": "TargetList",
      "BidListDimensions": [
        "HasAdFormatId",
        "HasAdFormatId",
        "HasAdFormatId"
      ]
    }
  ],
  "IgnoreReferralUrlInConversion": true,
  "IsBallotMeasure": true,
  "IsCandidateElection": true,
  "CandidateProfiles": [
    {
      "PoliticalDataId": "sample string 1",
      "CandidateName": "sample string 1",
      "ElectionState": "Alaska",
      "PayingEntityName": "sample string 1",
      "PayingEntityAddress": "sample string 1",
      "PayingEntityEmailAddress": "sample string 1",
      "PayingEntityExecutiveName": "sample string 1",
      "PayingEntityExecutiveTitle": "sample string 1",
      "GeoDescription": "sample string 1",
      "AudienceDescription": "sample string 1",
      "DisclaimerNotice": "sample string 1",
      "FileLocationInS3": "sample string 1",
      "FederalVerificationId": "sample string 1",
      "StateVerificationId": "sample string 1"
    },
    {
      "PoliticalDataId": "sample string 1",
      "CandidateName": "sample string 1",
      "ElectionState": "Alaska",
      "PayingEntityName": "sample string 1",
      "PayingEntityAddress": "sample string 1",
      "PayingEntityEmailAddress": "sample string 1",
      "PayingEntityExecutiveName": "sample string 1",
      "PayingEntityExecutiveTitle": "sample string 1",
      "GeoDescription": "sample string 1",
      "AudienceDescription": "sample string 1",
      "DisclaimerNotice": "sample string 1",
      "FileLocationInS3": "sample string 1",
      "FederalVerificationId": "sample string 1",
      "StateVerificationId": "sample string 1"
    },
    {
      "PoliticalDataId": "sample string 1",
      "CandidateName": "sample string 1",
      "ElectionState": "Alaska",
      "PayingEntityName": "sample string 1",
      "PayingEntityAddress": "sample string 1",
      "PayingEntityEmailAddress": "sample string 1",
      "PayingEntityExecutiveName": "sample string 1",
      "PayingEntityExecutiveTitle": "sample string 1",
      "GeoDescription": "sample string 1",
      "AudienceDescription": "sample string 1",
      "DisclaimerNotice": "sample string 1",
      "FileLocationInS3": "sample string 1",
      "FederalVerificationId": "sample string 1",
      "StateVerificationId": "sample string 1"
    }
  ],
  "VettingStatus": "Rejected"
}

+ Response 201 (application/json)

    + Headers

            Location: /advertiser

    + Body
~~~
            {
  "PartnerId": "sample string 1",
  "AdvertiserId": "sample string 1",
  "AdvertiserName": "sample string 1",
  "Description": "sample string 1",
  "CurrencyCode": "USD",
  "AttributionClickLookbackWindowInSeconds": 1,
  "AttributionImpressionLookbackWindowInSeconds": 1,
  "ClickDedupWindowInSeconds": 1,
  "ConversionDedupWindowInSeconds": 1,
  "DefaultRightMediaOfferTypeId": 1,
  "IndustryCategoryId": 1,
  "Keywords": [
    "sample string 1",
    "sample string 2",
    "sample string 3"
  ],
  "Availability": "Archived",
  "LogoURL": "sample string 1",
  "DomainAddress": "sample string 1",
  "CustomLabels": [
    {
      "CustomLabelId": "sample string 1"
    },
    {
      "CustomLabelId": "sample string 1"
    },
    {
      "CustomLabelId": "sample string 1"
    }
  ],
  "AssociatedBidLists": [
    {
      "BidListId": "sample string 1",
      "IsEnabled": true,
      "IsDefaultForDimension": true,
      "BidListSource": "ManualRecommendation",
      "BidListAdjustmentType": "TargetList",
      "BidListDimensions": [
        "HasAdFormatId",
        "HasAdFormatId",
        "HasAdFormatId"
      ]
    },
    {
      "BidListId": "sample string 1",
      "IsEnabled": true,
      "IsDefaultForDimension": true,
      "BidListSource": "ManualRecommendation",
      "BidListAdjustmentType": "TargetList",
      "BidListDimensions": [
        "HasAdFormatId",
        "HasAdFormatId",
        "HasAdFormatId"
      ]
    },
    {
      "BidListId": "sample string 1",
      "IsEnabled": true,
      "IsDefaultForDimension": true,
      "BidListSource": "ManualRecommendation",
      "BidListAdjustmentType": "TargetList",
      "BidListDimensions": [
        "HasAdFormatId",
        "HasAdFormatId",
        "HasAdFormatId"
      ]
    }
  ],
  "IgnoreReferralUrlInConversion": true,
  "IsBallotMeasure": true,
  "IsCandidateElection": true,
  "CandidateProfiles": [
    {
      "PoliticalDataId": "sample string 1",
      "CandidateName": "sample string 1",
      "ElectionState": "Alaska",
      "PayingEntityName": "sample string 1",
      "PayingEntityAddress": "sample string 1",
      "PayingEntityEmailAddress": "sample string 1",
      "PayingEntityExecutiveName": "sample string 1",
      "PayingEntityExecutiveTitle": "sample string 1",
      "GeoDescription": "sample string 1",
      "AudienceDescription": "sample string 1",
      "DisclaimerNotice": "sample string 1",
      "FileLocationInS3": "sample string 1",
      "FederalVerificationId": "sample string 1",
      "StateVerificationId": "sample string 1"
    },
    {
      "PoliticalDataId": "sample string 1",
      "CandidateName": "sample string 1",
      "ElectionState": "Alaska",
      "PayingEntityName": "sample string 1",
      "PayingEntityAddress": "sample string 1",
      "PayingEntityEmailAddress": "sample string 1",
      "PayingEntityExecutiveName": "sample string 1",
      "PayingEntityExecutiveTitle": "sample string 1",
      "GeoDescription": "sample string 1",
      "AudienceDescription": "sample string 1",
      "DisclaimerNotice": "sample string 1",
      "FileLocationInS3": "sample string 1",
      "FederalVerificationId": "sample string 1",
      "StateVerificationId": "sample string 1"
    },
    {
      "PoliticalDataId": "sample string 1",
      "CandidateName": "sample string 1",
      "ElectionState": "Alaska",
      "PayingEntityName": "sample string 1",
      "PayingEntityAddress": "sample string 1",
      "PayingEntityEmailAddress": "sample string 1",
      "PayingEntityExecutiveName": "sample string 1",
      "PayingEntityExecutiveTitle": "sample string 1",
      "GeoDescription": "sample string 1",
      "AudienceDescription": "sample string 1",
      "DisclaimerNotice": "sample string 1",
      "FileLocationInS3": "sample string 1",
      "FederalVerificationId": "sample string 1",
      "StateVerificationId": "sample string 1"
    }
  ],
  "VettingStatus": "Rejected"
}
~~~


### Retrieving an Advertiser [GET/advertiser/{advertiserId}]
Retrieve an existing advertiser by ID. This is the ID that was originally created and returned
by TradeDesk in the response call during the first attempt to create the advertiser.

| Parameter Name                               | Type             | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Required /Optional? |
|:--------------------------------------------:|:----------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-------------------:|
| PartnerId                                    | string           | The ID of the partner who owns this advertiser.  Your partner ID will be provided when you are  granted access to the API                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | Required            |
| AdvertiserId                                 | string           | The ID of the advertiser. Ignored on create, when  an ID will be assigned and returned by The Trade Desk.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | Required            |
| AdvertiserName                               | string           | The name of the advertiser                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | Required            |
| Description                                  | string/ nullable | An optional description of the advertiser.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | Optional            |
| CurrencyCode                                 | string           | The three-letter currency code of the Advertiser.  If not provided, this will default to the Partner's currency code.  Note The currency code cannot be changed after the Advertiser  has been created. If you want a different currency, you must  create a new Advertiser. Unless you arranged different terms  during onboarding, your Partner will be in USD and all  Advertisers under the partner must use the same currency.   If you believe you need another currency, please contact  your account manager for terms and conditions. If multiple  currency support is enabled for your account, see the  Currency API for the full set of supported currencies and their codes.  | Optional            |
| AttributionClickLookbackWindowInSeconds      | integer(int32)   | When The Trade Desk performs click attribution for the  advertiser’s conversions, this is the amount of time  (in seconds) that will be considered for attribution purposes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Required            |
| AttributionImpressionLookbackWindowInSeconds | integer(int32)   | When The Trade Desk performs impression attribution for the advertiser’s conversions, this is the amount of time  (in seconds) that will be considered for attribution purposes                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Required            |
| ClickDedupWindowInSeconds                    | integer(int32)   | When The Trade Desk performs click attribution for your  conversions, similar clicks will be considered duplicates if  they are within this window. Set to zero to disable click  deduplication.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | Required            |
| ConversionDedupWindowInSeconds               | integer(int32)   | When The Trade Desk performs impression attribution for  your conversions, similar conversions will be considered  duplicates if they are within this window. Set to zero to  disable conversion deduplication.                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Required            |
| DefaultRightMediaOfferTypeId                 | integer(int64)   | Sets the default Right Media Offer Type (creative category)  to use on new creatives. If an existing advertiser does not  have a default offer type set, this property will be omitted  from the API's response. Once set, new creatives that do  not have an offer type specified on creation will inherit this  offer type. Creatives that do not have a Right Media Offer  Type will not be able to buy Right Media inventory until  one is assigned. See the Right Media Offer Type API  for a full list of possible values.                                                                                                                                                             | Required            |
| IndustryCategoryId                           | integer(int64)   | An ID identifying the industry category to which this ad  group belongs. This property is required as of version 3  of the API. If an existing advertiser does not have an  industry category set, this property will be omitted from  the API's response. See the Category API for a full list  of possible values.                                                                                                                                                                                                                                                                                                                                                                         | Required            |
| Keywords                                     | string           | Keywords that classify the Advertiser. These can be  individual words like "travel" or phrases like "deals website". The keywords will be normalized and  duplicates will be removed. You may specify any  number of keywords and each keyword can be up to  300 characters long.                                                                                                                                                                                                                                                                                                                                                                                                            | Required            |
| Availability                                 | string           | Availability state of the Advertiser. This field is read- only.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Required            |
| LogoURL                                      | string/ nullable | The URL for the Advertiser's logo or brand image.  The API will throw an error if this is not a valid URL  to an image. While this is not a required attribute, it is  recommended that this value be set because a Logo  URL is necessary to bid on certain types of inventory  from select supply vendors.                                                                                                                                                                                                                                                                                                                                                                                 | Optional            |


+ Response 200 (application/json)

    + Headers

            Location: /advertiser/{advertiserId}

    + Body

{
  "PartnerId": "sample string 1",
  "AdvertiserId": "sample string 1",
  "AdvertiserName": "sample string 1",
  "Description": "sample string 1",
  "CurrencyCode": "USD",
  "AttributionClickLookbackWindowInSeconds": 1,
  "AttributionImpressionLookbackWindowInSeconds": 1,
  "ClickDedupWindowInSeconds": 1,
  "ConversionDedupWindowInSeconds": 1,
  "DefaultRightMediaOfferTypeId": 1,
  "IndustryCategoryId": 1,
  "Keywords": [
    "sample string 1",
    "sample string 2",
    "sample string 3"
  ],
  "Availability": "Archived",
  "LogoURL": "sample string 1",
  "DomainAddress": "sample string 1",
  "CustomLabels": [
    {
      "CustomLabelId": "sample string 1"
    },
    {
      "CustomLabelId": "sample string 1"
    },
    {
      "CustomLabelId": "sample string 1"
    }
  ],
  "AssociatedBidLists": [
    {
      "BidListId": "sample string 1",
      "IsEnabled": true,
      "IsDefaultForDimension": true,
      "BidListSource": "ManualRecommendation",
      "BidListAdjustmentType": "TargetList",
      "BidListDimensions": [
        "HasAdFormatId",
        "HasAdFormatId",
        "HasAdFormatId"
      ]
    },
    {
      "BidListId": "sample string 1",
      "IsEnabled": true,
      "IsDefaultForDimension": true,
      "BidListSource": "ManualRecommendation",
      "BidListAdjustmentType": "TargetList",
      "BidListDimensions": [
        "HasAdFormatId",
        "HasAdFormatId",
        "HasAdFormatId"
      ]
    },
    {
      "BidListId": "sample string 1",
      "IsEnabled": true,
      "IsDefaultForDimension": true,
      "BidListSource": "ManualRecommendation",
      "BidListAdjustmentType": "TargetList",
      "BidListDimensions": [
        "HasAdFormatId",
        "HasAdFormatId",
        "HasAdFormatId"
      ]
    }
  ],
  "IgnoreReferralUrlInConversion": true,
  "IsBallotMeasure": true,
  "IsCandidateElection": true,
  "CandidateProfiles": [
    {
      "PoliticalDataId": "sample string 1",
      "CandidateName": "sample string 1",
      "ElectionState": "Alaska",
      "PayingEntityName": "sample string 1",
      "PayingEntityAddress": "sample string 1",
      "PayingEntityEmailAddress": "sample string 1",
      "PayingEntityExecutiveName": "sample string 1",
      "PayingEntityExecutiveTitle": "sample string 1",
      "GeoDescription": "sample string 1",
      "AudienceDescription": "sample string 1",
      "DisclaimerNotice": "sample string 1",
      "FileLocationInS3": "sample string 1",
      "FederalVerificationId": "sample string 1",
      "StateVerificationId": "sample string 1"
    },
    {
      "PoliticalDataId": "sample string 1",
      "CandidateName": "sample string 1",
      "ElectionState": "Alaska",
      "PayingEntityName": "sample string 1",
      "PayingEntityAddress": "sample string 1",
      "PayingEntityEmailAddress": "sample string 1",
      "PayingEntityExecutiveName": "sample string 1",
      "PayingEntityExecutiveTitle": "sample string 1",
      "GeoDescription": "sample string 1",
      "AudienceDescription": "sample string 1",
      "DisclaimerNotice": "sample string 1",
      "FileLocationInS3": "sample string 1",
      "FederalVerificationId": "sample string 1",
      "StateVerificationId": "sample string 1"
    },
    {
      "PoliticalDataId": "sample string 1",
      "CandidateName": "sample string 1",
      "ElectionState": "Alaska",
      "PayingEntityName": "sample string 1",
      "PayingEntityAddress": "sample string 1",
      "PayingEntityEmailAddress": "sample string 1",
      "PayingEntityExecutiveName": "sample string 1",
      "PayingEntityExecutiveTitle": "sample string 1",
      "GeoDescription": "sample string 1",
      "AudienceDescription": "sample string 1",
      "DisclaimerNotice": "sample string 1",
      "FileLocationInS3": "sample string 1",
      "FederalVerificationId": "sample string 1",
      "StateVerificationId": "sample string 1"
    }
  ],
  "VettingStatus": "Rejected"
}


# Data Structures

## Advertiser (object)
+ AdvertiserName: "My Advertiser" (string, required)
+ AttributionClickLookbackWindowInSeconds: 5184000 (string, required)
+ AttributionImpressionLookbackWindowInSeconds: 5184000 (string, required)
+ ClickDedupWindowInSeconds: 7 (string, required)
+ ConversionDedupWindowInSeconds: 60 (string, required)
+ DefaultRightMediaOfferTypeId: 1 (string, required)
+ IndustryCategoryId: 1 (string, required)
+ Domain Address: "https://www.domain.com" (string, required)

## Campaign (object)
+ CampaignName: "My Campaign" (string, required)
+ AttributionClickLookbackWindowInSeconds: 5184000 (string, required)
+ AttributionImpressionLookbackWindowInSeconds: 5184000 (string, required)
+ ClickDedupWindowInSeconds: 7 (string, required)
+ ConversionDedupWindowInSeconds: 60 (string, required)
+ DefaultRightMediaOfferTypeId: 1 (string, required)
+ IndustryCategoryId: 1 (string, required)
