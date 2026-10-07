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

Guidelines for Creating Product

Guidelines for Creating Product

API call flow overview

API call flow overview

1\. Creating Product

1\. Creating Product

2\. Creating global product

2\. Creating global product

3\. Publishing global product

3\. Publishing global product

Data Definition

Data Definition

Attribute value data type

Attribute value data type

Attribute input type

Attribute input type

Logistics type

Logistics type

Item status type

Item status type

Translation language

Translation language

Stock type

Stock type

Product promotion type

Product promotion type

Market Code

Market Code

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

# Guidelines for Creating Product

Last Updated: 2022-11-01

Language Supported: English / 简体中文 / 繁體中文 / Português (Brasil) / ไทย

1) We recommend cross-border sellers who have upgraded CNSC/KRSC to read the following articles to create products:

-   [Product creation preparation](https://open.shopee.com/developer-guide/209)
-   [Creating global product](https://open.shopee.com/developer-guide/213)
-   [Publish global product](https://open.shopee.com/developer-guide/215)

2）For other types of sellers, we recommend reading the following articles:

-   [Product creation preparation](https://open.shopee.com/developer-guide/209)
-   [Create product](https://open.shopee.com/developer-guide/211)

# API call flow overview

\*Solid line is required process, dashed line is not required process

## 1\. Creating Product

![](https://open.shopee.com/opservice/api/v1/image/download/?image_id=h6oVTrljpWY5S0tzciqOnG9YqfQGBKY0kK2R7CZfSaYxi3MuWqsNzSN%2BPL50gXxhG1ImXimQ2aQtAhsB2uRKEA%3D%3D&image_type=png)

## 2\. Creating global product

![](https://open.shopee.com/opservice/api/v1/image/download/?image_id=Gu3z%2FttxxOY0eNPh7vBiitjykBI5B9m4U%2FJjIQu1hZGBw%2FSLdo2rBIjGjIgRnHUYaizhVXpQd7iTSbqmKX6dIw%3D%3D&image_type=png)

## 3\. Publishing global product

  

  

  

  

![](https://open.shopee.com/opservice/api/v1/image/download/?image_id=canaYd%2FLXy8qTVaTeWvYhivWE4ZMNJtKdBdYo0dtqMLMRjGozjA9Zb3KWiKAkWccuhYqnfzgxeLv1KWH2tPxHw%3D%3D&image_type=png)

# Data Definition

# Attribute value data type

(input\_validation\_type)

-   INT\_TYPE
-   STRING\_TYPE
-   ENUM\_TYPE
-   FLOAT\_TYPE
-   TIMESTAMP\_TYPE
-   DATE\_TYPE

## Attribute input type

(input\_type)

-   DROP\_DOWN
-   TEXT\_FILED
-   COMBO\_BOX
-   MULTIPLE\_SELECT
-   ﻿MULTIPLE\_SELECT\_COMBO\_BOX

## Logistics type

(fee\_type)

-   SIZE\_SELECTION
-   SIZE\_INPUT
-   FIXED\_DEFAULT\_PRICE
-   CUSTOM\_PRICE

## Item status type

(item\_status)

-   NORMAL
-   DELETED
-   BANNED
-   UNLIST

## Translation language

(language)

-   zh-hans：Simplified Chinese
-   zh-hant: Traditional Chinese
-   ms-my：Malay
-   en-my: English (Malaysia)
-   en: English
-   id: Indonesian
-   vi: Vietnamese
-   th: Thai
-   pt-br: Portuguese
-   es-mx: Spanish (Mexican)
-   pl: Polish
-   es-CO: Spanish (Colombia)
-   es-CL: Spanish (Chile)

## Stock type

(stock\_type)

-   1: Shopee Warehouse stock
-   2: Seller stock

## Product promotion type

(promotion\_type)

-   Campaign
-   Discount Promotions
-   Flash Sale
-   Whole Sale
-   Group Buy
-   Bundle Deal
-   Welcome Package
-   Add-on Discount
-   Brand Sale
-   In ShopFlash Sale
-   Gift with purchase
-   ﻿Exclusive Price

## Market Code

-   SG: Singapore
-   MY: Malaysia
-   TW: Taiwan
-   ID: Indonesia
-   VN: Vietnam
-   TH: Thailand
-   BR: Brazil
-   PH: Philippines
-   MX: Mexico
-   CO: Colombia
-   CL: Chile
-   PL: Poland

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