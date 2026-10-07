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

Getting Started

Getting Started

 > 

Requesting Access to Sensitive Data

Requesting Access to Sensitive Data

Eligibility Requirements

Eligibility Requirements

How to Submit a Penetration Test Report

How to Submit a Penetration Test Report

How to Enable IP Address Whitelisting

How to Enable IP Address Whitelisting

Good Practices for Penetration Test Report Submission

Good Practices for Penetration Test Report Submission

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

# Requesting Access to Sensitive Data

Last Updated: 2026-08-04

Language Supported: English / 简体中文 / ไทย

  

Shopee Open Platform safeguards sellers’ business data and users’ personal data considered sensitive (including customer name, phone number, email address, and address).

  

By default, sensitive data is masked. Developers must complete specific security requirements to request access to unmasked sensitive data.

### Eligibility Requirements

To request access to sensitive business data, developers must meet the following conditions:

1.  Submit Penetration Test Report

-   Required for Third-party Partner Platform (ISV) Developers serving, or planning to serve, sellers in Thailand, Malaysia, Singapore, or the Philippines, as well as ISVs from China Cross-Border (CNCB) and Hong Kong Cross-Border (HKCB)
-   A valid penetration test report must be submitted through the Open Platform Console

3.  Whitelist IP Address(es)

-   Required for all developers
-   The IP addresses of the servers hosting your application must be declared and whitelisted.

⚠️ Note: For Third-party Partner Platform (ISV) Developers, approved sensitive data access is valid for two (2) years from the penetration test report’s issue date.

### How to Submit a Penetration Test Report

Follow the steps below to upload your penetration test report:

-   Step 1: Log in to your Open Platform console using your developer account

Note: Member accounts do not have permission to upload reports.

-   Step 2: Navigate to Personal Center → Account Information (Chinese Mainland ISVs: [Link](https://open.shopee.cn/console/person/account), Other Region ISVs: [Link](https://open.shopee.com/console/person/account))
-   Step 3: Under Security Reports & Certifications Information, click "Add"

![](https://open.shopee.com/opservice/api/v1/image/download/?image_id=3nkzhcjEysHs%2BxVIeQP%2BiarSKdEmhwKjczzYD%2FJArvxFyZzMjDJFfVJ8RFX6cNqLFAYlHxz94fUYl8ONlEFGHw%3D%3D&image_type=png)

-   Step 4: Under Security Report & Certification Type, Choose “Penetration Test Report”
-   Step 5: Upload your latest penetration test report
-   Step 6: Click “Save”

![](https://open.shopee.com/opservice/api/v1/image/download/?image_id=ukOwqouxK6zyCz8GXhJf1UXdCDjwO%2F%2BPzT61qRe4vZHYPG6QovDt2Yd1bXTHPaxy3FKwqPXsb0870c350msmzQ%3D%3D&image_type=png)

Review Timeline

-   The submission status (Approved / Rejected) will be updated in the Account Information section.
-   Review results are typically available within 10 working days.

  

📌 Please refer to the bottom of this page for best practices and guidelines on penetration test report submissions.

### How to Enable IP Address Whitelisting

To enable IP address whitelisting for your application:

-   Step 1: Log in to your Open Platform console and go to App List
-   Step 2: Select the app that requires sensitive data access
-   Step 3: Click Go Live and fill up the required information

![](https://open.shopee.com/opservice/api/v1/image/download/?image_id=%2FqddWrd%2FufgszAu0EqzuJupG12wDspo8uOp0rwhl4yXC3cHHIcNRI0w7zkUxisCvrxrLP%2BbA4iWbP9O81Ow%2FaA%3D%3D&image_type=png)

-   Step 4: Under “IP Address Whitelist”, enter the IP address(es) of the server(s) hosting your application
-   Step 5: Toggle Enable IP Address Whitelist to ON
-   Step 6: Click Submit

![](https://open.shopee.com/opservice/api/v1/image/download/?image_id=eOiVyGkoK1KQYE4yDiBl3WZ2X70hP9izMdRLceS%2BAx%2BYAbodKDHQRgvNjOHvrxGJejEGnIRDiOS9ln81sc3zZA%3D%3D&image_type=png)

⚠️ Important: Once IP Address Whitelisting is enabled, API calls can only be made from applications hosted on the declared IP address(es).

  

### Good Practices for Penetration Test Report Submission

1\. Recommended Testing Providers

To improve report quality and review efficiency, ISVs are encouraged to engage reputable, accredited penetration testers, such as:

-   CREST Accredited Penetration Tester
-   Offensive Security Certified Professional (OSCP)
-   GIAC Certified Penetration Tester (GPEN)
-   Certified Ethical Hacker (CEH)
-   Certified Information Systems Security Professional (CISSP)
-   EC-Council Certified Security Analyst (ECSA)
-   CompTIA PenTest+
-   AWS Security Competency Partners
-   Alibaba Cloud Security Partners
-   Qianxin (奇安信)
-   360 数字安全
-   Sangfor (深信服)
-   Chaitin (长亭科技)

Reports from other penetration testers will still be reviewed and considered for approval on a case-by-case basis.

  

2\. Report Quality Requirements

A complete Penetration Test Report should:

-   Cover the application's externally exposed attack surface.
-   Assess all relevant systems and applications within the testing scope.
-   Document the testing methodology, testing process, scope, and detailed findings.
-   Include a comprehensive list of identified vulnerabilities.
-   Confirm that all Critical and High severity vulnerabilities have been remediated.
-   Be based on black-box penetration testing.

Please note: Vulnerability scan reports alone are not acceptable and will not satisfy this requirement.

  

3\. Recommended Report Issuance Date

-   ISVs are encouraged to submit a penetration test report issued within the last one (1) year.
-   Sensitive data access will be granted for two (2) years from the report issue date.

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