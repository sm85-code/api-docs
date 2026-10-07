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

First Mile Binding

First Mile Binding

Terminology

Terminology

Best Practise

Best Practise

For pick up mode:

For pick up mode:

For drop off mode:

For drop off mode:

For self deliver mode:

For self deliver mode:

FAQ

FAQ

Data definition

Data definition

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

# First Mile Binding

Last Updated: 2026-07-29

Language Supported: English / 简体中文 / 繁體中文 / ไทย

\*This article only applies to cross-border sellers.

  

Currently, for cross-border sellers in Mainland China and South Korea, Shopee provides the first-mile tracking bind function, you can check the following API call flow.

![](https://open.shopee.com/opservice/api/v1/image/download/?image_id=Wu0r%2BxqH%2FmCDxIH6%2BV9VeaIfAT494HYyMt3kIS6v6JGYBCU8NexqXDzcUPsOuoTL%2B9odvYtWCMctV4fvm8zW%2Fw%3D%3D&image_type=png)

# Terminology

  

Pick up: Channel door-to-door collection, only "logistics\_channel\_name": "shopee" ("logistics\_channel\_id": 813) support pick up.

  

Drop off: Delivered to channel outlets, expect "logistics\_channel\_name": "shopee"（"logistics\_channel\_id": 813）和"logistics\_channel\_name": "Self Deliver"（"logistics\_channel\_id": 0), other channels you get are drop off.

  

Self deliver: Self-delivered, not using third-party logistics, "logistics\_channel\_name": "Self Deliver".

  

first\_mile\_tracking\_number: first-mile tracking number

# Best Practise

For different types of first-mile shipping methods, they can be classified as

-   Pick up
-   Drop off
-   Self deliver

  

Developers can get the list of channels for first-mile and the shipping methods supported by the corresponding channels through the first\_mile.get\_channel\_list API.

## For pick up mode:

Step 1: Generate the first mile tracking number via [v2.first\_mile.generate\_first\_mile\_tracking\_number](https://open.shopee.com/documents/v2/v2.first_mile.generate_first_mile_tracking_number?module=96&type=1) API and [v2.first\_mile.get\_tracking\_number\_list](https://open.shopee.com/documents/v2/v2.first_mile.get_tracking_number_list?module=96&type=1) API can be used to query the list of generated first mile tracking numbers.

Step 2: [v2.first\_mile.get\_unbind\_order\_list](https://open.shopee.com/documents/v2/v2.first_mile.get_unbind_order_list?module=96&type=1) API provides the list of orders to be bound with the first-mile tracking number, and then please bind them through [v2.first\_mile.bind\_first\_mile\_tracking\_number](https://open.shopee.com/documents/v2/v2.first_mile.bind_first_mile_tracking_number?module=96&type=1) API; v2.first\_mile.get \_detail API can be used to query the first mile tracking number details.

Step 3: Call [v2.first\_mile.get\_waybill](https://open.shopee.com/documents/v2/v2.first_mile.get_waybill?module=96&type=1) API to print the first mile package label.

## For drop off mode:

Step 1: The seller obtains the channel tracking number offline.

Step 2: Get the list of orders to be bound with the first-mile tracking number through [v2.first\_mile.get\_unbind\_order\_list](https://open.shopee.com/documents/v2/v2.first_mile.get_unbind_order_list?module=96&type=1) API and binding them through [v2.first\_mile.bind\_first\_mile\_tracking\_number](https://open.shopee.com/documents/v2/v2.first_mile.bind_first_mile_tracking_number?module=96&type=1) api. v2.first\_mile. get\_detail API can be used to query the first-mile tracking number details.

## For self deliver mode:

Step 1: The seller gets the list of orders to be bound with the first-mile tracking number through the [v2.first\_mile.get\_unbind\_order\_list](https://open.shopee.com/documents/v2/v2.first_mile.get_unbind_order_list?module=96&type=1) API.

Step 2: Generate the first mile tracking number via [v2.first\_mile.generate\_first\_mile\_tracking\_number](https://open.shopee.com/documents/v2/v2.first_mile.generate_first_mile_tracking_number?module=96&type=1) API and [v2.first\_mile.get\_tracking\_number\_list](https://open.shopee.com/documents/v2/v2.first_mile.get_tracking_number_list?module=96&type=1) API can be used to query the list of generated first mile tracking numbers. (shipping\_method need to be uploaded self-deliver,logistics\_channel\_id need to be uploaded null).

# FAQ

Q: Is it allowed to bind orders across shops for a first-mile tracking number?A: Yes, but make sure that orders across shops use the same transshipment warehouse. Because the API has authentication, when calling the [v2.first\_mile.bind\_first\_mile\_tracking\_number](https://open.shopee.com/documents/v2/v2.first_mile.bind_first_mile_tracking_number?module=96&type=1) API, only one shop's order can be called for one call, so please make sure that order\_sn and shop\_id match for each time you call.

  

Q: Will the order status change after successful binding?

A: Yes, after binding FM successfully and being scanned, the order status of all orders being bound will be updated from PROCESSED to SHIPPED.

  

Q: Should I ship the order and print the airway bill first or first mile bind first?

A: The correct order is to ship the order first, then print the airway bill, then bind the first mile tracking number for order.

  

Q: How can I check the first-mile tracking number of an order?

A: You can use v2.logistics.get\_tracking\_number API and upload the request parameter response\_optional\_fields: first\_mile\_tracking\_number then you can get the first-mile tracking number of an order.

  

Q: What can first\_mile\_tracking\_number status be bound?

A: You can query the first-mile tracking number status through v2.first\_mile.get\_detail API.

1\. If ship\_method is a pickup:

-   If the first\_mile\_tracking\_number is just generated, the status is NOT\_AVAILABLE, at that time, the order can be bound.
-   If the first\_mile\_tracking\_number tracking status is ORDER\_RECEIVED, it means that there are orders that have already been bound, and you can continue to bind other orders.
-   If the first\_mile\_tracking\_number status is PICKED\_UP, indicating that the parcels have been collected by the channel, and can no longer bind the order.
-   If the first\_mile\_tracking\_number status is DELIVERED, which means that the parcel has arrived at the warehouse, and orders can no longer be bound.

  

2\. If ship\_method is drop off or self-deliver: there is no status restriction.

  

Q: Does self-deliver still need to call the API for first mile binding?A: Yes, even self-delivery is the offline ship action for sellers, but you still need to call [v2.first\_mile.bind\_first\_mile\_tracking\_number](https://open.shopee.com/documents/v2/v2.first_mile.bind_first_mile_tracking_number?module=96&type=1) API for the first-mile binding.

  

Q: In what state can I unbind the first mile tracking number for an order?

A: 1\. If ship\_method is a pick up, only if the first\_mile\_tracking\_number status is ORDER\_RECEIVED can be unbind.

2\. If ship\_method is drop off or self-deliver, there is no first\_mile\_tracking\_number status restriction.

# Data definition

First Mile tracking number status

-   ORDER\_RECEIVED
-   PICKED\_UP
-   DELIVERED

  

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