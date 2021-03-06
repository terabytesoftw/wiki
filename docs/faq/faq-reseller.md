---
layout: default
title: How to use NetLicensing in reseller mode
parent: FAQ & Troubleshooting
nav_order: 100
description: "Setup NetLicensing reseller mode via Predefined Licensee or Auto-Created Licensee"
permalink: faq-reseller
---

{{ page.title }}
=============

## Question

Our products are being distributed via partners and resellers network.
The time between distributors receive the license, and users start using the products, there might be some days or even months. Maintenance starts when users start using our products.
How this reseller scenario can be achieved with NetLicensing?

## Answer

You can setup NetLicensing reseller mode with the two options outlined below:

**Option 1: Predefined Licensee**

_This option is suitable for resellers with a low number of customers._

With this option, you'd need to create needed [Licensees](object-model) via [NetLicensing Management Console](https://ui.netlicensing.io) and share _Licensee Numbers_ numbers with your resellers.


**Option 2: Auto-Created Licensee**

_This option is suitable for resellers with a high number of customers, where pre-creation of hight number of the Licensees isn't feasible._

With this option, you need to create an APIKey with Role `"ROLE_APIKEY_OPERATION"` ( see also [Security](security) ) and allow your resellers to create Licensees whenever they need a new one.
