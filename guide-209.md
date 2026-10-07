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

Product creation preparation

Product creation preparation

1\. Category

1\. Category

1.1 Global category data

1.1 Global category data

1.2 Category tree

1.2 Category tree

1.3 Recommend categories

1.3 Recommend categories

2\. Attribute

2\. Attribute

2.1 Required and optional Attributes

2.1 Required and optional Attributes

2.2 Type of attributes

2.2 Type of attributes

2.3 Data types of attribute values

2.3 Data types of attribute values

2.4 Attribute value units

2.4 Attribute value units

2.5 Parent attribute and parent brand

2.5 Parent attribute and parent brand

2.6 Recommend attributes

2.6 Recommend attributes

3\. Brand

3\. Brand

4\. Days to ship

4\. Days to ship

5\. Size chart

5\. Size chart

6\. Product restrictions

6\. Product restrictions

7\. Product logistics

7\. Product logistics

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

# Product creation preparation

Last Updated: 2025-09-19

Language Supported: English / 简体中文 / 繁體中文 / Português (Brasil) / ไทย

Before creating a product, you need to get the category, attributes, brand,days to ship, whether the category supports size chart and other information through API to get prepared for creating products.

# 1\. Category

Each product must have a unique category, please get Shopee category data by [v2.product.get\_category](https://open.shopee.com/documents/v2/v2.product.get_category?module=89&type=1) API. Each node's category has a unique category\_id.

## 1.1 Global category data

Shopee's category tree data applies to all markets, but according to the local policies of the market, some of the categories we set to market prohibited. That is, when you call  [v2.product.get\_category](https://open.shopee.com/documents/v2/v2.product.get_category?module=89&type=1) API with a Malaysian shop, you can get category A, but through a Singapore shop, you can not get it.Policies for cross-border and domestic sales are also different, so category data will also vary. For different types of sellers, there are also small differences in the supported category data.

  

So, in order for you to get the most accurate category data, it is recommended to obtain it according to shop\_id.

## 1.2 Category tree

[v2.product.get\_category](https://open.shopee.com/documents/v2/v2.product.get_category?module=89&type=1) API returns all available categories for the shop.

parent\_category\_id\=0, it means this is the first level category, otherwise, it will return the parent category id of this category.

has\_children\=false means the last level category, otherwise, it means that this category has children. Please note that only the category\_id with has\_children\=false can be used to create or update products.

  

For example, if the category tree path is Level 1 category→Level 2 category→Level 3 category, the API return will be

  

"category\_list": \[

     {

       "display\_category\_name": "Level 1 category",

       "has\_children":true,

       "category\_id": 105899,

       "original\_category\_name": "Level 1 category",

       "parent\_category\_id": 0

     },

     {

       "display\_category\_name": "Level 2 category",

       "has\_children": true,

       "category\_id":109889,

       "original\_category\_name": "Level 2 category",

       "parent\_category\_id":105899

     },

     {

       "display\_category\_name": "Level 3 category",

       "has\_children":false,

       "category\_id":107839,

       "original\_category\_name": "Level 3 category",

       "parent\_category\_id":109889

     }

  

\]

​​

## 1.3 Recommend categories

In order to help sellers quickly find the category of the product, you can also call ​​​​​​​​[v2.product.category\_recommend](https://open.shopee.com/documents/v2/v2.product.category_recommend?module=89&type=1) API, API will return a list of recommended categories based on the product name and product image.

# 2\. Attribute

Each product category has different attribute data. The “[v2.product.get\_attribute\_tree](https://open.shopee.com/documents/v2/v2.product.get_attribute_tree?module=89&type=1)” API will return the attribute data for the given “category\_id”. However, please note that only last-level categories can retrieve attribute data. A last-level category is defined as one where the value of the “has\_children” field under the “category\_list” section returned via the “v2.product.get\_category” API is false.

## 2.1 Required and optional Attributes

When creating or updating products, all required attributes must be uploaded, while optional attributes can be provided based on your needs. In the “[v2.product.get\_attribute\_tree](https://open.shopee.com/documents/v2/v2.product.get_attribute_tree?module=89&type=1)” API response, “is\_mandatory”: true indicates a required attribute, and “is\_mandatory”: false indicates an optional attribute.

## 2.2 Type of attributes

We classify attribute types based on factors such as whether the attribute value supports multiple selections, whether it allows custom input, and whether the attribute value is provided. You can check the “input\_type” field in the “[v2.product.get\_attribute\_tree](https://open.shopee.com/documents/v2/v2.product.get_attribute_tree?module=89&type=1)” API response for relevant information.

  

input\_type

Type

Definition

Description

Custom value is allowed

Attribute values are provided

1

int

SINGLE\_DROP\_DOWN

Single-select dropdown; Sellers can only choose one option from the list of attribute values (“attribute\_value\_list”) returned by the API to upload.

No

Yes

2

int

SINGLE\_COMBO\_BOX

Single-select dropdown + text input field; Sellers can either choose one option from the list of attribute values (“attribute\_value\_list”) returned by the API to upload, or set a custom value.

Yes

Yes

3

int

FREE\_TEXT\_FILED

Text input field; Sellers can set a custom value.

Yes

No

4

int

MULTI\_DROP\_DOWN

Multi-select dropdown; Sellers can select multiple options from the list of attribute values (“attribute\_value\_list”) returned by the API to upload.

No

Yes

5

int

MULTI\_COMBO\_BOX

Multi-select dropdown + text input field; Sellers can select multiple options from the list of attribute values (“attribute\_value\_list”) returned by the API to upload, or set a custom value.

Yes

Yes

  

\*The following figure shows an example with “input\_type”: 2 (SINGLE\_COMBO\_BOX). Sellers can select a value from the attribute list (Elliptical Trainers), or set a custom value by clicking the 'Add a new item' button and filling it in.

  

![](https://open.shopee.com/opservice/api/v1/image/download/?image_id=fRwCwghzuvErysDyVPBF2ekbN12lbJrXL15qMKgrWbSiwZq6ZTGwaxbUJZI6QdU%2Fac%2Fc%2BpJxBDqZIJdo03fSeA%3D%3D&image_type=png)

  

![](https://open.shopee.com/opservice/api/v1/image/download/?image_id=gHzROWZC734oayOGwYWIEEJ4aOfLKJ9Ot4vs2%2Fq7W6ebnpH8B%2B8l8ulTy0D%2BjHXcVys8w2r%2FiVecwMDBjG12Og%3D%3D&image_type=png)

Please note:

-   For product attributes that support multi-select dropdowns, you can get the maximum number of attribute values that can be uploaded through the “max\_value\_count” parameter.
-   You can get the list of attribute values provided by Shopee for upload through the “attribute\_value\_list” parameter.

  

## 2.3 Data types of attribute values

Attribute values have defined data types, and you need to upload the attribute values according to the required data type. You can obtain the data type of the attribute value through the “input\_validation\_type” field returned by the “[v2.product.get\_attribute\_tree](https://open.shopee.com/documents/v2/v2.product.get_attribute_tree?module=89&type=1)” API.

  

input\_validation\_type

Type

Description

Remarks

0

int

VALIDATOR\_NO\_VALIDATE\_TYPE

  

1

int

VALIDATOR\_INT\_TYPE

  

2

int

VALIDATOR\_STRING\_TYPE

  

3

int

VALIDATOR\_FLOAT\_TYPE

  

4

int

VALIDATOR\_DATE\_TYPE, including two formats：

-   DD/MM/YYYYY, e.g. 31/06/2021
-   MM/YYYYY, e.g. 06/2021

When adding or editing a product, for attributes with a date data type, please enter the timestamp in Unix timestamp format. However, when retrieving detailed product attribute values, the “original\_value\_name” will return the value in a readable date format.

  

Please note:

-   For the date type attribute, there are two formats: one is MONTH/YEAR (06/2021) and the other is DAY/MONTH/YEAR (31/06/2021). You can check the “date\_format\_type” field in the “[v2.product.get\_attribute\_tree](https://open.shopee.com/documents/v2/v2.product.get_attribute_tree?module=89&type=1)” API response for details.
-   When creating or updating a product, you need to upload the attribute value as a Unix timestamp in the “original\_value\_name” field. However, when retrieving product information, the “original\_value\_name” field in the “v2.product.get\_item\_base\_info” API response will return the date in a format such as 06/2021 or 31/06/2021.

## 2.4 Attribute value units

For example, for the length attribute, we provide sellers with options to choose units such as “cm” and “m”. Therefore, you need to first understand which attribute values require a unit and which units are available for these attribute values. You can call the ” [v2.product.get\_attribute\_tree](https://open.shopee.com/documents/v2/v2.product.get_attribute_tree?module=89&type=1)” API to obtain this information.

  

When the returned parameter “format\_type”: 2 (FORMAT\_QUANTITATIVE\_WITH\_UNIT) is present, it means the attribute value requires a unit, and the” attribute\_unit\_list” parameter will return the available units for that attribute value. When the returned parameter “format\_type”: 1 (FORMAT\_NORMAL) is present, it means the attribute value does not require a unit.

  

\*In the attribute value list provided by Shopee, we display the value and the unit separately. Specifically, the “name” field in the “attribute\_value\_list” will return the value of the attribute (i.e. 5kg), while the “value\_unit” field will return the unit of the attribute value (i.e. kg).

  

  

## 2.5 Parent attribute and parent brand

For example, for the “Weight Type” attribute, the available attribute values are “Body Weights” and “Barbells”. The “Body Weights Type” attribute is associated with the “Body Weights” value. Therefore, when the seller selects “Body Weights” for the “Weight Type” attribute, the “Body Weights Type” attribute will be displayed, and we recommend that the seller fill in the corresponding value.

  

\*Selecting “Barbells” value does not show the Body Weights Type attribute

![](https://open.shopee.com/opservice/api/v1/image/download/?image_id=hmDs%2Fh2CSentvXEC9ZHnwxO9KKB1rT2MnXME5uEp68EnKwcypJjEmyTWTM1l%2B1F9yJU1ifPB%2FFMQI2fOqINacw%3D%3D&image_type=png)

\*Selecting “Body Weights” value displays the Body Weights Type attribute

![](https://open.shopee.com/opservice/api/v1/image/download/?image_id=K4udxonCC%2FcKdl%2BCL2DocRZMT8HAdwWp%2BOLWTsvEYWDbwP8xl0uS2Hl2Y8ZnqYciisl%2B14pwZOXTgK6WM3v1UA%3D%3D&image_type=png)

”v2.product.get\_attribute\_tree” API partial response

Json

```
{
    "attribute_id": 100643,
    "mandatory": false,
    "name": "Weight Type",
    "attribute_value_list": [
        {
            "value_id": 3300,
            "name": "Barbells",
            "multi_lang": [
                {
                    "language": "zh-Hant",
                    "value": "槓鈴"
                }
            ]
        },
        {
            "value_id": 3341,
            "name": "Body Weights",
            "child_attribute_list": [
                {
                    "attribute_id": 100602,
                    "mandatory": false,
                    "name": "Body Weights Type",
                    "attribute_value_list": [
                        {
                            "value_id": 3164,
                            "name": "Ankle",
                            "multi_lang": [
                                {
                                    "language": "zh-Hant",
                                    "value": "腳踝"
                                }
                            ]
                        }
                    ],
                    "attribute_info": {
                        "input_type": 5,
                        "input_validation_type": 2,
                        "format_type": 1,
                        "max_value_count": 5,
                        "is_oem": false,
                        "support_search_value": false
                    },
                    "multi_lang": [
                        {
                            "language": "zh-Hant",
                            "value": "重訓輔助配件類型"
                        }
                    ]
                }
            ],
            "multi_lang": [
                {
                    "language": "zh-Hant",
                    "value": "穿戴負重器材"
                }
            ]
        }
    ],
    "attribute_info": {
        "input_type": 2,
        "input_validation_type": 2,
        "format_type": 1,
        "is_oem": false,
        "support_search_value": false
    },
    "multi_lang": [
        {
            "language": "zh-Hant",
            "value": "重訓器材種類"
        }
    ]
}
```

  

In this example, “Weight Type” is the parent attribute, and “Body Weights Type” is the child attribute. To upload the child attribute, you must also upload the associated parent attribute.

  

  

## 2.6 Recommend attributes

To help sellers quickly find the recommended attributes for the product, you can call ​​​​​​​​[v2.product.get\_recommend\_attribute](https://open.shopee.com/documents/v2/v2.product.get_recommend_attribute?module=89&type=1) API, sellers can upload the product name and product image, the API will return a list of recommended attributes. Note that this API may not return the required attributes.

# 3\. Brand

You can upload the brand information for the product, but we will require certain categories to fill in the brand information, and each category supports a different list of brands, so please call [v2.product.get\_brand\_list](https://open.shopee.com/documents/v2/v2.product.get_brand_list?module=89&type=1) API to get the brand list data supported by a category (can only be requested with the last level category).

  

is\_mandatory: true true means that this category must be filled with brand information.

  

\* If the brand list provided by Shopee does not contain the brand you need, you can submit a registered brand application to Shopee, please call [v2.product.register\_brand](https://open.shopee.com/documents/v2/v2.product.register_brand?module=89&type=1) API and refer to [FAQ](https://open.shopee.com/faq?top=162&sub=166&page=1&faq=211) for QC process.

  

\*If your product does not have a registered brand, Shopee provides a list of brands, including No Brand option (brand\_id: 0) , you can choose this option to upload.

  

[v2.product.get\_brand\_list](https://open.shopee.com/documents/v2/v2.product.get_brand_list?module=89&type=1) API

status: 1 for the list of brands provided by Shopee, status: 2 the list of brands waiting for review after you submit your registration.

# 4\. Days to ship

We have shipping days requirements for different categories and different seller types, sellers need to fulfill orders within the shipping days, for specific categories, we support you to set the goods as pre-sale goods, shipping time will be longer. You can get the shipping days information through the [v2.product.get\_item\_limit](https://open.shopee.com/documents/v2/v2.product.get_item_limit?module=89&type=1) API.

  

If days\_to\_ship\_limit min\_limit and max\_limit return a value of -1, it means that the category does not support pre-sale, when the return value is greater than 0, this category can fill in the range of pre-sale days. If the category does not support pre-sales, The non\_pre\_order\_days\_to\_ship parameter will return the shipping days set by Shopee for this category.

# 5\. Size chart

For some categories,we support sellers uploading one size chart image for a product, you can use [v2.product.support\_size\_chart](https://open.shopee.com/documents/v2/v2.product.support_size_chart?module=89&type=1) API to check whether the category (leaf category) supports size chart.

  

\*Please note that we are rolling out the size chart of table type, and now only some whitelisted sellers can add through the seller center, open api does not support returning the categories that support the table size chart and uploading. So whitelisted sellers please ignore the results from the [v2.product.support\_size\_chart](https://open.shopee.com/documents/v2/v2.product.support_size_chart?module=89&type=1) API.

# 6\. Product restrictions

We have certain restrictions on product information, such as the length of characters that can be filled in the product name, the range of product price, etc. We have different restrictions for different markets and different types of sellers. You can get the limits we set through [v2.product.get\_item\_limit](https://open.shopee.com/documents/v2/v2.product.get_item_limit?module=89&type=1) API.

# 7\. Product logistics

You can get the logistics\_channel\_id through [v2.logistics.get\_channel\_list](https://open.shopee.com/documents/v2/v2.logistics.get_channel_list?module=95&type=1) API, you can only choose the channel with enabled=true and mask\_channel\_id=0 for product.

  

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