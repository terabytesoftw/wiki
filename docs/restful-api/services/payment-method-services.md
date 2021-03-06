---
layout: default
title: Payment Method Services
parent: Services
grand_parent: NetLicensing API (RESTful)
nav_order: 80
description: "Payment Method Services"
permalink: payment-method-services
---

Payment Method Services
=======================

-   [Payment methods list](#payment-methods-list)
-   [Get payment method](#get-payment-method)
-   [Update payment method](#update-payment-method)

### Payment methods list

Return a list of all payment methods for the current vendor.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>HTTP Method / URL</p></td>
<td><p>GET /core/v2/rest/paymentmethod</p></td>
</tr>
<tr class="even">
<td>Security</td>
<td><ul>
<li>Basic Authentication</li>
<li><a href="security">API Key Identification</a>
<ul>
<li>ROLE_APIKEY_ADMIN</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Request Header</p></td>
<td><p>Accept: application/json | application/xml</p></td>
</tr>
<tr class="even">
<td><p>Request Parameters</p></td>
<td><p>- None -</p></td>
</tr>
<tr class="odd">
<td><p>HTTP Status Code</p></td>
<td><p>200 - Successful request<br />
400 - Malformed or illegal request<br />
403 - Access is denied<br />
404 - Resource not found<br />
500 - Internal service error</p></td>
</tr>
</tbody>
</table>

See also
JavaDoc: <a href="https://go.netlicensing.io/javadoc/v2/com/labs64/netlicensing/service/PaymentMethodService.html#list-com.labs64.netlicensing.domain.vo.Context-java.lang.String-" class="external-link">PaymentMethodService.list</a>

<span
class="expand-control-icon"><img src="assets/images/icons/grey_arrow_down.png" class="expand-control-image" /></span><span
class="expand-control-text">Example</span>

<div>Request</div>
{: .code-example .ml-5 .code-header }
```http
GET https://go.netlicensing.io/core/v2/rest/paymentmethod
Accept: application/xml
```
{: .ml-5 }

<div>Response</div>
{: .code-example .ml-5 .code-header }
```xml
<netlicensing xmlns="http://netlicensing.labs64.com/schema/context">
    <infos/>
    <items>
        <item type="PaymentMethod">
            <property name="number">PAYPAL_SANDBOX</property>
            <property name="active">false</property>
        </item>
        <item type="PaymentMethod">
            <property name="number">PAYPAL</property>
            <property name="active">true</property>
            <property name="paypal.subject">sample_paypal_subject</property>
        </item>
    </items>
</netlicensing>
```
{: .ml-5 }

<div>Try it now</div>
{: .code-example .ml-5 .code-header }
```bash
$ curl --header "Accept: application/xml" --insecure --user demo:demo --request GET https://go.netlicensing.io/core/v2/rest/paymentmethod
```
{: .ml-5 }

### Get payment method

Return a payment method info by paymentMethodNumber.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>HTTP Method / URL</p></td>
<td><p>GET /core/v2/rest/paymentmethod/{paymentMethodNumber}</p></td>
</tr>
<tr class="even">
<td>Security</td>
<td><ul>
<li>Basic Authentication</li>
<li><a href="security">API Key Identification</a>
<ul>
<li>ROLE_APIKEY_ADMIN</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Request Header</p></td>
<td><p>Accept: application/json | application/xml</p></td>
</tr>
<tr class="even">
<td><p>Request Parameters</p></td>
<td><p>paymentMethodNumber (string) - Payment method number.</p></td>
</tr>
<tr class="odd">
<td><p>HTTP Status Code</p></td>
<td><p>200 - Successful request<br />
400 - Malformed or illegal request<br />
403 - Access is denied<br />
404 - Resource not found<br />
500 - Internal service error</p></td>
</tr>
</tbody>
</table>

See also
JavaDoc: <a href="https://go.netlicensing.io/javadoc/v2/com/labs64/netlicensing/service/PaymentMethodService.html#get-com.labs64.netlicensing.domain.vo.Context-java.lang.String-" class="external-link">PaymentMethodService.get</a>

<span
class="expand-control-icon"><img src="assets/images/icons/grey_arrow_down.png" class="expand-control-image" /></span><span
class="expand-control-text">Example</span>

<div>Request</div>
{: .code-example .ml-5 .code-header }
```http
GET https://go.netlicensing.io/core/v2/rest/paymentmethod/PAYPAL
Accept: application/xml
```
{: .ml-5 }

<div>Response</div>
{: .code-example .ml-5 .code-header }
```xml
<netlicensing xmlns="http://netlicensing.labs64.com/schema/context">
    <infos/>
    <items>
        <item type="PaymentMethod">
            <property name="number">PAYPAL</property>
            <property name="active">true</property>
            <property name="paypal.subject">sample_paypal_subject</property>
        </item>
    </items>
</netlicensing>
```
{: .ml-5 }

<div>Try it now</div>
{: .code-example .ml-5 .code-header }
```bash
$ curl --header "Accept: application/xml" --insecure --user demo:demo --request GET https://go.netlicensing.io/core/v2/rest/paymentmethod/PAYPAL
```
{: .ml-5 }

### Update payment method

Sets the provided properties to a payment method. Return an updated
payment method.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>HTTP Method / URL</p></td>
<td><p>POST /core/v2/rest/paymentmethod/{paymentMethodNumber}</p></td>
</tr>
<tr class="even">
<td>Security</td>
<td><ul>
<li>Basic Authentication</li>
<li><a href="security">API Key Identification</a>
<ul>
<li>ROLE_APIKEY_ADMIN</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Request Header</p></td>
<td><p>Accept: application/json | application/xml<br />
Content-Type: application/x-www-form-urlencoded</p></td>
</tr>
<tr class="even">
<td><p>Request Parameters</p></td>
<td><p>paymentMethodNumber (string) - Payment method number.</p>
<p><span style="color: rgb(0,0,0);">active (boolean) - If set to 'false', the payment method is disabled.</span></p>
<p><span style="color: rgb(0,0,0);">paypal.subject (string) - The e-mail address of the PayPal account for which you are making the API calls.</span></p></td>
</tr>
<tr class="odd">
<td><p>HTTP Status Code</p></td>
<td><p>200 - Successful request<br />
400 - Malformed or illegal request<br />
<span>402 - Not allowed within your pricing plan</span><br />
403 - Access is denied<br />
404 - Resource not found<br />
500 - Internal service error</p></td>
</tr>
</tbody>
</table>

See also
JavaDoc: <a href="https://go.netlicensing.io/javadoc/v2/com/labs64/netlicensing/service/PaymentMethodService.html#update-com.labs64.netlicensing.domain.vo.Context-java.lang.String-com.labs64.netlicensing.domain.entity.PaymentMethod-" class="external-link">PaymentMethodService.update</a>

<span
class="expand-control-icon"><img src="assets/images/icons/grey_arrow_down.png" class="expand-control-image" /></span><span
class="expand-control-text">Example</span>

<div>Request</div>
{: .code-example .ml-5 .code-header }
```http
POST https://go.netlicensing.io/core/v2/rest/paymentmethod/PAYPAL
active=false
Accept: application/xml
Content-Type: application/x-www-form-urlencoded
```
{: .ml-5 }

<div>Response</div>
{: .code-example .ml-5 .code-header }
```xml
<netlicensing xmlns="http://netlicensing.labs64.com/schema/context">
    <infos/>
    <items>
        <item type="PaymentMethod">
            <property name="number">PAYPAL</property>
            <property name="active">false</property>
            <property name="paypal.subject">sample_paypal_subject</property>
        </item>
    </items>
</netlicensing>
```
{: .ml-5 }
