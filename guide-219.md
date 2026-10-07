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

-   Personal Center
-   Logout

Tables of Contents

API Guidelines and Flows

API Guidelines and Flows

 > 

Variant management

Variant management

1\. Adding variants with same tier structure

1\. Adding variants with same tier structure

2.Adding variants that change tier structure

2.Adding variants that change tier structure

3.Deleting variants with same tier structure

3.Deleting variants with same tier structure

4.Deleting variants that change tier structure

4.Deleting variants that change tier structure

5.Changing the order of variants

5.Changing the order of variants

6.Changing the option name of the variant

6.Changing the option name of the variant

Summary

Summary

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

# Variant management

Last Updated: 2024-05-28

Language Supported: English / 简体中文 / 繁體中文 / Português (Brasil) / ไทย

Shopee supports defining variant structures with up to two levels of specifications. The total number of variants cannot exceed 50.

For example, if an item has a color specification, the color is red, or blue, we call this 1-tier variation.

For example, if the product has color and size specifications, color is red, blue, size is L, XL, we call this 2-tier variation.

  

To add variants when creating an item, please refer to the article on [Creating product](https://open.shopee.com/developer-guide/211).

To manage variants after creating an item, please refer to this article.

To manage the stock and price of a variation, please refer to the [Stock and Price Management](https://open.shopee.com/developer-guide/223) article.

# 1\. Adding variants with same tier structure

Scenario 1: The product has already defined color specifications with red and blue colors, now you need to add black for the middle position of option.

Variant situation:

tier\_index

option

model\_id

tier\_index\[0\]

red

10000

tier\_index\[1\]  (To be added）

black (To be added）

\-

tier\_index\[2\]

blue

20000

API: [v2.product.update\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.update_tier_variation?module=89&type=1) + [v2.product.add\_model](https://open.shopee.com/documents/v2/v2.product.add_model?module=89&type=1)

  

1.1 Call the [v2.product.update\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.update_tier_variation?module=89&type=1) API to add a black option first

Request example:

Json

```
{

    "item_id": 800250275,

    "tier_variation": [

        {

            "name": "Color",

            "option_list": [

                {

                    "option": "red"

                },

                {

                    "option": "black"

                },

               {

                    "option": "blue"

                }

            ]

        }

    ],

    "model_list": [

        {

            "tier_index": [0],

            "model_id": 10000

        },

        {

            "tier_index": [2],

            "model_id": 20000

        }

    ]

}
```

  

  

1.2 Call the [v2.product.add\_model](https://open.shopee.com/documents/v2/v2.product.add_model?module=89&type=1) API to add price, stock, SKU information for the black variant:

Request example:

Json

```
{

"item_id": 800250275,

"model_list": [

{

"tier_index": [1],

"original_price": 30,

"model_sku": "sku-black",

"seller_stock": [
{
"stock": 300
}
]}]}
```

# 2.Adding variants that change tier structure

Scenario 2: The product has defined color specifications, the colors are red and blue, now you need to add size specifications, the sizes include L and XL.

  

Original Variant situation:

tier\_index

option

model\_id

tier\_index\[0\]

red

10000

tier\_index\[1\]

blue

20000

  

Variant situation that change after:

tier\_index

option

model\_id

tier\_index\[0,0\]

red,L

\-

tier\_index\[0,1\]

red,XL

\-

tier\_index\[1,0\]

blue,L

\-

tier\_index\[1,1\]

blue,XL

\-

  

\*Because the tier structure has been changed, the original model information will be removed after calling API: [v2.product.init\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.init_tier_variation?module=89&type=1),  which means the original model\_id: 10000 and model\_id: 20000 will be invalid.

  

API: [v2.product.init\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.init_tier_variation?module=89&type=1)

Request example:

Json

```
{

  "item_id": 100918691,

  "tier_variation": [

    {

      "option_list": [

        {

          "option": "red"

        },

        {

          "option": "blue"

        }

      ],

      "name": "color"

    },

    {

      "option_list": [

        {

          "option": "L"

        },

        {

          "option": "XL"

        }

      ],

      "name": "size"

    }

  ],

  "model": [

    {

      "original_price": 10,

      "model_sku": "sku-red-L",

      "normal_stock": 100,

      "tier_index": [0,0]

    },

    {

      "original_price":20,

      "model_sku": "sku-red-XL",

      "normal_stock":200,

      "tier_index": [0,1]

    },

    {

      "original_price":30,

      "model_sku": "sku-blue-L",

      "normal_stock":300,

      "tier_index": [1,0]

    },

   {

      "original_price":40,

      "model_sku": "sku-blue-XL",

      "normal_stock":400,

      "tier_index": [1,1]

    }

  ]

}
```

  

# 3.Deleting variants with same tier structure

Scenario 3: The product has defined color specifications with colors red, blue, and black, and now the blue color needs to be deleted.

  

Original variant situation:

tier\_index

option

model\_id

tier\_index\[0\]

red

10000

tier\_index\[1\] (To be deleted）

blue  (To be deleted）

20000

tier\_index\[2\]

black

30000

  

Because to delete the blue color, the tier\_index can only be tier\_index\[0\], tier\_index\[1\] after deletion, so we need to overwrite the information of the variant at tier\_index\[1\] with the information of the black variant.

  

Variants situation after deletion

tier\_index

option

model\_id

tier\_index\[0\]

red

10000

tier\_index\[1\]

black

30000

  

API: [v2.product.update\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.update_tier_variation?module=89&type=1) to remove option and overwrite the model information at the same time.

Request example:

Json

```
{

    "item_id": 800250275,

    "tier_variation": [

        {

            "name": "color",

            "option_list": [

                {

                    "option": "red"

                },  

               {

                    "option": "black"

                }

            ]

        }

    ],

    "model_list": [

        {

            "tier_index": [0],

            "model_id": 10000

        },

        {

            "tier_index": [1],

            "model_id": 30000

        }

    ]

}
```

  

Scenario 4: The product has defined color and size specifications, color is red, blue, size is L, XL, and now all the blue variants need to be deleted.

  

Original variant situation

tier\_index

option

model\_id

tier\_index\[0,0\]

red,L

10000

tier\_index\[0,1\]

red,XL

20000

tier\_index\[1,0\] (To be deleted）

blue,L (To be deleted）

30000

tier\_index\[1,1\] (To be deleted）

blue,XL  (To be deleted）

40000

  

API: [v2.product.update\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.update_tier_variation?module=89&type=1) to delete both option and model information at the same time.

Request example:

Json

```
{

    "item_id": 800250275,

    "tier_variation": [

        {

            "name": "color",

            "option_list": [

                {

                    "option": "red"

                }

            ]

        },

     {

            "name": "size",

            "option_list": [

              {

                    "option": "L"

                },

                {

                    "option": "XL"

                }

            ]

        }

    ],

    "model_list": [

        {

            "tier_index": [0,0],

            "model_id": 10000

        },

        {

            "tier_index": [0,1],

            "model_id": 20000

        }

    ]

}

```

  

Variants situation after deletion

tier\_index

option

model\_id

tier\_index\[0,0\]

red,L

10000

tier\_index\[0,1\]

red,XL

20000

tier\_index\[1,0\]

\-

\-

tier\_index\[1,1\]

\-

\-

# 4.Deleting variants that change tier structure

Scenario 5: The product has defined color and size specifications, color is red, blue, size is L, XL, and now all colors need to be deleted.

  

Original variant situation:

tier\_index

option

model\_id

tier\_index\[0,0\]

red,L

10000

tier\_index\[0,1\]

red,XL

20000

tier\_index\[1,0\]

blue,L

30000

tier\_index\[1,1\]

blue,XL

40000

  

Variant situation after deletion:

tier\_index

option

model\_id

tier\_index\[0\]

L

\-

tier\_index\[1\]

XL

\-

  

  

API: [v2.product.init\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.init_tier_variation?module=89&type=1)

Request example:

Json

```
{

  "item_id": 100918691,

  "tier_variation": [

    {

      "option_list": [

        {

          "option": "L"

        },

        {

          "option": "XL"

        }

      ],

      "name": "size"

  ],

  "model": [

    {

      "original_price": 10,

      "model_sku": "sku-L",

      "normal_stock": 100,

      "tier_index": [0]

    },

    {

      "original_price":20,

      "model_sku": "sku-XL",

      "normal_stock":200,

      "tier_index": [1]

    }  ]

}
```

# 5.Changing the order of variants

Scenario 6: The item has defined color specifications with colors red and blue. Now the color order needs to be changed to blue, red, with the original variant information retained.

  

Original variant situation

tier\_index

option

model\_id

tier\_index\[0\]

red

10000

tier\_index\[1\]

blue

20000

  

Variant situation after change:

tier\_index

option

model\_id

tier\_index\[0\]

blue

20000

tier\_index\[1\]

red

10000

  

API: [v2.product.update\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.update_tier_variation?module=89&type=1)

Request example:

Json

```
{

    "item_id": 800250275,

    "tier_variation": [

        {

            "name": "color",

            "option_list": [

                {

                    "option": "blue"

                },  

               {

                    "option": "red"

                }

            ]

        }

    ],

    "model_list": [

        {

            "tier_index": [0],

            "model_id": 20000

        },

        {

            "tier_index": [1],

            "model_id": 10000

        }

    ]

}
```

# 6.Changing the option name of the variant

  

Scenario 7: The item has defined a color specification with the colors red and blue. Now the color name needs to be changed to red-A, blue.

  

Original variant situation

tier\_index

option

model\_id

tier\_index\[0\]

red

10000

tier\_index\[1\]

blue

20000

Variant situation after change:

tier\_index

option

model\_id

tier\_index\[0\]

red-A

10000

tier\_index\[1\]

blue

20000

  

API: [v2.product.update\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.update_tier_variation?module=89&type=1)

Request example:

Json

```
{

    "item_id": 800250275,

    "tier_variation": [

        {

            "name": "color",

            "option_list": [

                {

                    "option": "red-A"

                },  

               {

                    "option": "blue"

                }

            ]

        }

    ],

    "model_list": [

        {

            "tier_index": [0],

            "model_id": 10000

        },

        {

            "tier_index": [1],

            "model_id": 20000

        }

    ]

}
```

# Summary

1.The function of [v2.product.init\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.init_tier_variation?module=89&type=1) API, including changing 0-tier variation to 1-tier variation / 0-tier variation to 2-tier variation / 1-tier variation to 2-tier variation / 2-tier variation to 1-tier variation.

2.The function of [v2.product.update\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.update_tier_variation?module=89&type=1) API, including add/delete/update the options, If you still need to keep the original variants information, please use the model\_list field.

3\. The function of [v2.product.add\_model](https://open.shopee.com/documents/v2/v2.product.add_model?module=89&type=1) API is adding the new model information, the function of  [v2.product.delete\_model](https://open.shopee.com/documents/v2/v2.product.delete_model?module=89&type=1) API is deleting the variant information.

4\. Sellers who have upgraded CNSC and KRSC can only add/delete variants through global products, so please use the global product API for management, otherwise an error will be reported.

Global Product API

Product API

[v2.global\_product.init\_tier\_variation](https://open.shopee.com/documents/v2/v2.global_product.init_tier_variation?module=90&type=1)

[v2.product.init\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.init_tier_variation?module=89&type=1)

[v2.global\_product.update\_tier\_variation](https://open.shopee.com/documents/v2/v2.global_product.update_tier_variation?module=90&type=1)

[v2.product.update\_tier\_variation](https://open.shopee.com/documents/v2/v2.product.update_tier_variation?module=89&type=1)

[v2.global\_product.add\_global\_model](https://open.shopee.com/documents/v2/v2.global_product.add_global_model?module=90&type=1)

[v2.product.add\_model](https://open.shopee.com/documents/v2/v2.product.add_model?module=89&type=1)

[v2.global\_product.delete\_global\_model](https://open.shopee.com/documents/v2/v2.global_product.delete_global_model?module=90&type=1)

[v2.product.delete\_model](https://open.shopee.com/documents/v2/v2.product.delete_model?module=89&type=1)

  

  

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