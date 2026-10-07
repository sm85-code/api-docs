# Developer Guide - Shopee Open Platform

<iframe src="https://www.googletagmanager.com/ns.html?id=GTM-WC2P2P6&amp;" height="0" width="0" style="display:none;visibility:hidden" title="gtm"></iframe>

Created with Sketch.Open Platform

[

Documentation

](/developer-guide)

Support Center

[Announcement](/announcements) [Console](/console?from=header)

[AI Assistant](/ai-chat-bot)

What’s new

![](https://deo.shopeemobile.com/shopee/shopee-openplatform-live-sg/staticssr/static/img/ai-new-guide.8139d20.png)

Meet Your New AI Assistant

Need a quick answer? Let AI spark the solution for you!

Got it

Bahasa Indonesia

S

Tables of Contents

API Guidelines and Flows

API Guidelines and Flows

 > 

Creating product

Creating product

1\. Uploading media files

1\. Uploading media files

1.1 Uploading image

1.1 Uploading image

1.2 Uploading video

1.2 Uploading video

2\. Uploading category and attributes

2\. Uploading category and attributes

2.1 Uploading category

2.1 Uploading category

2.2 Uploading attributes

2.2 Uploading attributes

3\. Uploading description

3\. Uploading description

4\. Uploading price

4\. Uploading price

5\. Uploading stock

5\. Uploading stock

6\. Uploading shipment channels and shipping fee

6\. Uploading shipment channels and shipping fee

7\. Creating Variants

7\. Creating Variants

Getting Started

Getting Started

Introduction

Introduction

Developer account registration

Developer account registration

App management

App management

Service Market

Service Market

API calls

API calls

Push Mechanism notifications

Push Mechanism notifications

Authorization and Authentication

Authorization and Authentication

Sandbox Testing V2

Sandbox Testing V2

Service Partner Program

Service Partner Program

V2.0 API Call Flow

V2.0 API Call Flow

CNSC API Integration Guide

CNSC API Integration Guide

KRSC API Integration Guide

KRSC API Integration Guide

V2.0 Data Definition

V2.0 Data Definition

Requesting Access to Sensitive Data

TW New Developer Audit

TW New Developer Audit

BR SPI App Creation User Guide

BR SPI App Creation User Guide

BRASIL | Jornada do Desenvolvedor

BRASIL | Jornada do Desenvolvedor

Sua trilha começa aqui!

Sua trilha começa aqui!

Desenvolva uma integração

Desenvolva uma integração

Crie um login

Crie um login

Crie a conta de desenvolvedor

Crie a conta de desenvolvedor

Crie seu App

Crie seu App

Realize testes (Sandbox)

Realize testes (Sandbox)

Publique seu App (Go Live)

Publique seu App (Go Live)

Autorize sua primeira loja

Autorize sua primeira loja

Dados Sensíveis (Sensitive Data)

Dados Sensíveis (Sensitive Data)

Faça sua primeira chamada de API

Faça sua primeira chamada de API

Push Notifications (Webhooks)

Push Notifications (Webhooks)

Perguntas Frequentes

Perguntas Frequentes

Referências

Referências

Boas práticas antes de abrir um ticket

Boas práticas antes de abrir um ticket

API Guidelines and Flows

API Guidelines and Flows

Guidelines for Creating Product

Guidelines for Creating Product

Product creation preparation

Product creation preparation

Creating product

Creating product

Creating global product

Creating global product

Publishing global product

Publishing global product

Variant management

Variant management

Product base info management

Product base info management

Stock & Price Management

Stock & Price Management

Order Management

Order Management

First Mile Binding

First Mile Binding

Return Refund Management

Return Refund Management

SIP best practices

SIP best practices

Shopee On-Platform Ads API Guide

Shopee Xpress - Package-free Integration Guide

Shopee Xpress - Package-free Integration Guide

BRAZIL | Specific Local Guides

BRAZIL | Specific Local Guides

APIs de Order (Pedido)

APIs de Order (Pedido)

APIs de Logistics (Logística)

APIs de Logistics (Logística)

Como subir a NF-e através da OpenAPI e Mascaramento de Dados

AUTO PARTS: COMPATIBILIDADE DE AUTOPEÇAS

AUTO PARTS: COMPATIBILIDADE DE AUTOPEÇAS

Shopee Entrega Direta

Shopee Entrega Direta

Fulfilled by Shopee (BR)

Fulfilled by Shopee (BR)

Logística do Vendedor (API de Cotação)

Logística do Vendedor (API de Cotação)

Turbo Delivery (Quotation API)

Turbo Delivery (Quotation API)

Ferramenta de Log da Open Platform

Ferramenta de Log da Open Platform

Instant Mart Integration Guide

Instant Mart Integration Guide

Livestream API Integration Guide

Livestream API Integration Guide

Shopee AMS API Integration Guide

Shopee AMS API Integration Guide

Shopee Video API Integration Guide

Shopee Video API Integration Guide

Brand Portal Service API Integration Guide

Brand Portal Service API Integration Guide

Instant Order Fulfillment Guide

Instant Order Fulfillment Guide

Terms of Use

Terms of Use

Terms of Service

Terms of Service

Data Protection Policy

Data Protection Policy

Platform Partner Rules

Platform Partner Rules

TW Developer Screening

TW Developer Screening

Chatbot Terms of Service

Chatbot Terms of Service

Declare seus IPs

Declare seus IPs

# Creating product

Last Updated: 2025-09-19

Language Supported: English / 简体中文 / 繁體中文 / Português (Brasil) / ไทย

Once you have obtained the product base data, you can start creating products.

# 1\. Uploading media files

Images and videos of your products need to be pre-stored in Shopee's media space. So you need to call the MediaSpace API to upload first.

## 1.1 Uploading image

API: [v2.media\_space.upload\_image](https://open.shopee.com/documents/v2/v2.media_space.upload_image?module=91&type=1)

  

Each product must have product images, in addition, we also support insert images to product description. And the product image files need to meet the following requirements:

-   Image size: maximum 10MB
-   Image format: JPG, JPEG, PNG

  

Please note:

-   [V2.media\_space.upload\_image](https://open.shopee.com/documents/v2/v2.media_space.upload_image?module=91&type=1) API we only support image file upload, not support URL. When the image is uploaded successfully, you will get the Shopee image URL accessible in each region and a unique image\_id. We recommend that you link the Shopee image URL based on the shop region. image\_id is for creating products and updating the product image information.
-   If you upload a product image, the request parameter scene should be normal; if you upload a product description image, the request parameter scene should be desc, because the product image we will handle as a square image, the description image we will not handle.

  

## 1.2 Uploading video

Product video is optional, we support video files with the following requirements:

-   Video size: max 30MB
-   Video length: 10s~60s
-   Video format: mp4
-   Video pixel requirements: pixel width and height no more than 1280px \* 1280px

If your video file is over 4M, you need to split the video file, for example, a 10MB video, you need to split it into 4M, 4M and 2M fragments, because each fragment cannot be larger than 4M.

  

Uploading product videos need four steps:

  

-   Step 1: Call the [v](https://open.shopee.com/documents/v2/v2.media_space.init_video_upload?module=91&type=1)[2.media\_space.init\_video\_upload](https://open.shopee.com/documents/v2/v2.media_space.init_video_upload?module=91&type=1) API. Create a video upload task and get the video\_upload\_id. Please note that regardless of whether your video has a partition or not, file\_md5 needs to upload the md5 value of the full video file and file\_size is also for the full video file.
-   Step 2: Call the [v2.media\_space.upload\_video\_part](https://open.shopee.com/documents/v2/v2.media_space.upload_video_part?module=91&type=1) API. When the video file has fragments, the part\_seq (should start from 0)  parameter indicates the fragments sequence number, part\_content parameter indicates the fragments file. Please finish uploading all the fragments.
-   Step 3: Call the [v2.media\_space.complete\_video\_upload](https://open.shopee.com/documents/v2/v2.media_space.complete_video_upload?module=91&type=1) API. Video transcoding, when you call this API, Shopee will transcode all the video fragments files you uploaded. The part\_seq\_list parameter takes the sequence number of all the parts you uploaded, for example, if you uploaded 2 parts, the part\_seq\_list will be \[0,1\]. For the upload\_cost field you can upload the time of using the upload\_video\_part API for one video file.
-   Step 4: Call the [v2.media\_space.get\_video\_upload\_result](https://open.shopee.com/documents/v2/v2.media_space.get_video_upload_result?module=91&type=1) API. Get the video transcoding result. Since video transcoding takes some time, you can get the result by calling the [v2.media\_space.get\_video\_upload\_result](https://open.shopee.com/documents/v2/v2.media_space.get_video_upload_result?module=91&type=1) API or by subscribing to the [Video upload push](https://open.shopee.com/push-mechanism/11). Only when the returned status is SUCCEEDED, you can get the Shopee video URLs and video cover image URLs which are accessible to each market, and at that time, the video\_upload\_id can be used to create or update the video information of the product.

  

  

After uploading images and videos, you can call [v2.product.add\_item](https://open.shopee.com/documents/v2/v2.product.add_item?module=89&type=1) API to create products, the following will explain some points that need attention in calling [v2.product.add\_item](https://open.shopee.com/documents/v2/v2.product.add_item?module=89&type=1) API.

# 2\. Uploading category and attributes

## 2.1 Uploading category

Products must have category\_id. You can only select the leaf category ID in the category tree for the product, otherwise, the API will return an error with Invalid category id.

## 2.2 Uploading attributes

Products must upload all required attributes (attributes with "mandatory": true in the "[v2.product.get\_attribute\_tree](https://open.shopee.com/documents/v2/v2.product.get_attribute_tree?module=89&type=1)" API response are considered required). You can refer to the article "Product creation preparation" to learn more about different attribute types. Below are explanations of how to upload different attribute types when calling the "v2.product.add\_item" API.

  

When uploading the attribute with "input\_type": 1 (SINGLE\_DROP\_DOWN), you can only upload one "value\_id", and this "value\_id" must be one of the values from the attribute list returned by the “[v2.product.get\_attribute\_tree](https://open.shopee.com/documents/v2/v2.product.get_attribute_tree?module=89&type=1)” API.

  

Example 1

Json

```
"attribute_list": [
    {
        "attribute_id": 100036,
        "attribute_value_list": [
            {
                "value_id": 678
            }
        ]
    }
]
```

  

When uploading the attribute with "input\_type": 4 (MULTI\_DROP\_DOWN), you can upload multiple "value\_id" values, and these "value\_id" values must be be from the attribute list returned by the "[v2.product.get\_attribute\_tree](https://open.shopee.com/documents/v2/v2.product.get_attribute_tree?module=89&type=1)" API.

  

Example 2

Json

```
"attribute_list": [
    {
        "attribute_id": 100036,
        "attribute_value_list": [
            {
                "value_id": 678
            },
            {
                "value_id": 679
            }
        ]
    }
]
```

  

When uploading the attribute with "input\_type": 3 (FREE\_TEXT\_FILED), you can only upload one "value\_id" and specify a custom value. Therefore, you must upload “value\_id”: 0 and provide the custom value in the “original\_value\_name” field.

  

Example 3

Json

```
"attribute_list": [
    {
        "attribute_id": 100061,
        "attribute_value_list": [
            {
                "value_id": 0,
                "original_value_name": "customized name"
            }
        ]
    }
]
```

  

i) If the attribute has “input\_type”: 3 (FREE\_TEXT\_FIELD) and requires a unit, you must upload the “value\_unit” field as well. (That is, "input\_type": 3 & "format\_type": 2 (FORMAT\_QUANTITATIVE\_WITH\_UNIT))

  

Example 4

Json

```
"attribute_list": [
    {
        "attribute_id": 100061,
        "attribute_value_list": [
            {
                "value_id": 0,
                "original_value_name": "12",
                "value_unit": "g"
            }
        ]
    }
]
```

  

ii) If the attribute has “input\_type”: 3 (FREE\_TEXT\_FIELD) and requires a date type, you must upload a timestamp in the "original\_value\_name" field. (That is, "input\_type": 3 & "input\_validation\_type": 4)

  

Example 5

Json

```
"attribute_list": [
    {
        "attribute_id": 100061,
        "attribute_value_list": [
            {
                "value_id": 0,
                "original_value_name": "1634526913"
            }
        ]
    }
]
]
```

  

For the attribute with "input\_type": 2 (SINGLE\_COMBO\_BOX), you can only upload one "value\_id". This "value\_id" must be one of the values from the attribute list returned by the "[v2.product.get\_attribute\_tree](https://open.shopee.com/documents/v2/v2.product.get_attribute_tree?module=89&type=1)" API (please refer to Example 1) or a user-defined value (please refer to Example 3). If a unit is required, please refer to Example 4. If a date type is required, please refer to Example 5.

  

For the attribute with "input\_type": 5 (MULTI\_COMBO\_BOX), you can upload multiple "value\_id" values from the attribute list returned by the "[v2.product.get\_attribute\_tree](https://open.shopee.com/documents/v2/v2.product.get_attribute_tree?module=89&type=1)" API, or specify custom values.

  

Example 6

Json

```
"attribute_list": [
    {
        "attribute_id": 100061,
        "attribute_value_list": [
            {
                "value_id": 0,
                "original_value_name": "customized name"
            },
            {
                "value_id": 678
            }
        ]
    }
]
```

  

If a unit is required, please refer to Example 4. If a date type is required, please refer to Example 5.

  

Summary:

1) For all attribute types, you must upload a "value\_id". When uploading a user-defined value, "value\_id" must be 0 and "original\_value\_name" is required.

2) Regardless of the data type of the value, the "original\_value\_name" field must be uploaded in string format.

3) When "format\_type" is 2 and you upload a user-defined value, you must also upload the "value\_unit" field, and the unit should be selected from the "attribute\_unit\_list" in the response of the "[v2.product.get\_attribute\_tree](https://open.shopee.com/documents/v2/v2.product.get_attribute_tree?module=89&type=1)" API.

  

# 3\. Uploading description

\*Please note that we currently support whitelisted sellers to use extended\_description, please refer to the [FAQ](https://open.shopee.com/faq?top=162&sub=166&page=1&faq=218) for details on how to use it.

# 4\. Uploading price

Except for SG/MY/BR/MX/PL markets, we support sellers to upload two decimal prices (original\_price), for other marketplaces, only integers are supported, if sellers fill in decimals, we will do rounding.

# 5\. Uploading stock

If the seller does not have a stock warehouse (currently only used by whitelist users) then there is no need to upload the location\_id field.

# 6\. Uploading shipment channels and shipping fee

Depending on how the channel calculates the shipping fee, we have divided the channels into several types, you can get the fee\_type through [v2.logistics.get\_channel\_list](https://open.shopee.com/documents/v2/v2.logistics.get_channel_list?module=95&type=1) API, the types including:

-   SIZE\_SELECTION: The shipping fee is calculated based on the size ID
-   SIZE\_INPUT: The shipping fee is calculated according to the specific product dimension, so for this type, the seller needs to upload the length, width ,height and weight for the product.
-   FIXED\_DEFAULT\_PRICE: Fixed shipping fee.
-   CUSTOM\_PRICE: shipping fee can be customized by the seller.

  

The seller can choose multiple channels for the product.

i)enabled=true means the product is open to this channel and the buyer can choose.

ii) is\_free=true means the seller bears the shipping fee, i.e. the product is shipped, the buyer does not need to bear the shipping fee, and all channel types support setting up shipping.

  

1) For the SIZE\_SELECTION channel, the size\_id must be uploaded, and size\_id can be obtained through [v2.logistics.get\_channel\_list](https://open.shopee.com/documents/v2/v2.logistics.get_channel_list?module=95&type=1) API.

Example 1:

"logistic\_info":\[

   {

           "sizeid":1,

           "enabled":true,

           "is\_free":false,

           "logistic\_id":80101

       }\]

  

2）For the SIZE\_INPUT channel, the weight and dimension must be uploaded.

Example2:

   "weight": 1,

  "dimension":{

       "package\_height":11,

       "package\_length":11,

       "package\_width":11

   },

"logistic\_info":\[

   {

           "enabled":true,

           "is\_free":false,

           "logistic\_id":80101

       }\]

  

3）For the CUSTOM\_PRICE channel, the shipping\_fee must be uploaded.

Exapmle 3：

 "logistic\_info":\[

       {

           "shipping\_fee":23.12,

           "enabled":true,

           "is\_free":false,

           "logistic\_id":80103

       }\]

"logistic\_info":\[

       {

           "enabled":true,

           "logistic\_id":80103

       }\]

# 7\. Creating Variants

When you create the item successfully, [v2.product.add\_item](https://open.shopee.com/documents/v2/v2.product.add_item?module=89&type=1) will return the item\_id, which is the unique identifier of the item. If you also need to define specifications and create multiple option variants, such as the color and size, you can call [v2.product.init\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.init_tier_variation?module=89&type=1) API for the next step. We will create model\_id for each variation, which will be the unique identifier of the variation.

  

Scenario 1: The product has size specifications and the size contains XS, S, and M. We call this 1-tier variation product.

  

tier\_index

size

price

stock

SKU

tier\_index\[0\]

XS

100

10

sku1

tier\_index\[1\]

S

200

20

sku2

tier\_index\[2\]

M

300

30

sku3

  

  

[v2.product.init\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.init_tier_variation?module=89&type=1) API request example:

Json

```
{

    "item_id": 800188562,

    "tier_variation": [

        {

            "name": "size",

            "option_list": [

                {

                    "option": "XS",

                    "image": {"image_id":"82becb4830bd2ee90ad6acf8a9dc26d7"}

                },

                {

                    "option": "S",

        "image": {"image_id":"72becb4830bd2ee90ad6acf879dc26d7"}

                },

                {

                    "option": "M",

      "image": {"image_id":"92becb4830bd2ee90ad6acf8a9dc26d7"}

                }

            ]

        }

    ],

    "model": [

        {

            "tier_index": [0],

            "original_price": 100,

            "model_sku": "sku1",

            "normal_stock": 10

        },

        {

            "tier_index": [1],

            "original_price": 200,

            "model_sku": "sku1",

            "normal_stock": 20

        },

       {

            "tier_index": [2],

            "original_price": 300,

            "model_sku": "sku3",

            "normal_stock": 30

        }

    ]

}
```

  

  

  

Scenario 2: The product has color and size specifications, the color includes red and blue, and the size includes XL and L. We call this 2-tier variation product.

  

tier\_index

color

size

price

stock

SKU

tier\_index\[0,0\]

Red

XL

100

10

sku1

tier\_index\[0,1\]

Red

L

200

20

sku2

tier\_index\[1,0\]

Blue

XL

300

30

sku3

tier\_index\[1,1\]

Blue

L

400

40

sku4

  

[v2.product.init\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.init_tier_variation?module=89&type=1) API request example:

Json

```
 {

  "item_id": 100917481,

  "tier_variation": [

    {

      "name": "color",

      "option_list": [

        {

          "image": {"image_id": "82becb4830bd2ee90ad6acf8a9dc26d7"},

          "option": "Red"

        },

        {

          "image": {"image_id": "72becb4830bd2ee90ad6acf879dc26d7"},

          "option": "Blue"

        }

      ]

    },

    {

      "name": "size",

      "option_list": [

        {

          "option": "XL"

        },

        {

          "option": "L"

        }

      ]

    }

  ],

  "model": [

     { 

      "tier_index": [0,0],

      "original_price": 100,

      "normal_stock": 10,

      "global_model_sku": "sku1"

    },

    {

     "tier_index": [0,1],

      "original_price": 200,

      "normal_stock": 20,

      "global_model_sku": "sku2"

    },

    {

      "tier_index": [1,0],

      "original_price": 300,

      "normal_stock": 30,

      "global_model_sku": "sku3"

    },

    {

     "tier_index": [1,1],

      "original_price": 400,

      "normal_stock": 40,

      "global_model_sku": "sku4"

    }

  ]

}
```

  

Please note that

1\. The options you define will be displayed on the Shopee mall side in order. Shopee currently only supports the definition of up to 2-tier variation.

2\. You can define an image for each variant. If it is a 2-tier variation product, you can only define the first layer of options, that is, in the example, you can define variant images based on color, but not based on size. Once you want to add variant images, all the options in the first layer need to define the image. The image needs to be uploaded by calling the [v2.media\_space.upload\_image](https://open.shopee.com/documents/v2/v2.media_space.upload_image?module=91&type=1) API first.

3\. The tier\_index must start from 0 and not overflow, otherwise an error will be reported.

\*4.It is recommended that you create variants after an interval of 5 seconds after creating an item, because there may be a delay in creating item data.

5\. After successful creation you can call [v2.product.get\_model\_list](https://open.shopee.com/documents/v2/v2.product.get_model_list?module=89&type=1) API to get the model id corresponding to each tier\_index.

  

  

### User Guide

#### [Developer Guide](/developer-guide/0)

#### [API reference](/documents/v2/v2.ams.get_open_campaign_added_product?module=127&type=1)

#### [Push Mechanism](/push-mechanism/5)

#### [Shopee Open Platform Data Protection Policy](/policy?policy_id=1)

### Shopee Markets

#### [Service Market](https://service.shopee.cn/)

#### [Seller Education Hub (Singapore)](https://seller.shopee.sg/edu)

#### [Seller Education Hub (Malaysia)](https://seller.shopee.com.my/edu)

#### [Seller Education Hub (Thailand)](https://seller.shopee.co.th/edu)

#### [Seller Education Hub (Vietnam)](https://banhang.shopee.vn/edu)

#### [Seller Education Hub (Indonesia)](https://seller.shopee.co.id/edu)

#### [Seller Education Hub (Philippines)](https://seller.shopee.ph/edu)

#### [Seller Education Hub (Brazil)](https://seller.shopee.com.br/edu)

#### [Seller Education Hub (Japan)](https://shopee.jp/edu)

#### [Seller Education Hub (Korea)](https://shopee.kr/edu)

#### [Seller Education Hub (Hongkong)](https://shopee.com.hk/edu)

#### [虾皮卖家学习中心](https://shopee.cn/edu)

### Support

#### [Announcement](/announcements)

#### [FAQ](/faq)

#### [Raise Ticket](/console/raise-ticket)

Copyright @ Shopee 2025

-   Developer Guide
-   API Reference
-   Push Mechanism
    
-   Terms of Use

-   Raise Ticket
-   FAQ

-   English
-   简体中文
-   繁體中文
-   Português (Brasil)
-   Korean
-   Bahasa Indonesia
-   ไทย

Requesting Access to Sensitive Data

-   Personal Center
-   Logout

Shopee On-Platform Ads API Guide

Como subir a NF-e através da OpenAPI e Mascaramento de Dados