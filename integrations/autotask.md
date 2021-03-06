---
title: Autotask Integration
seoTitle: 'iLert: Autotask Integration for Alerting | Incident Response | Uptime'
description: >-
  The iLert Autotask integration helps you to easily connect iLert with
  Autotask.
date: '2020-07-02T15:00:00.000Z'
weight: 1
---

# Autotask Integration

With the iLert Autotask integration, you can create incidents in iLert based on tickets from Autotask.

## In Autotask: Create an API user <a id="create-api-user"></a>

1. Sign in to Autotask and then go to **Admin -&gt; Resources \(Users\)**

![](../.gitbook/assets/autotask1.png)

1. Click the **New** button and then navigate to **New API User**

![](../.gitbook/assets/autotask2.png)

1. In the **First Name** section, enter a first name eg. iLert
2. In the **Last Name** section, enter a last name eg. API
3. In the **Email** section, enter an email eg. support@ilert.com
4. Click the **Generate key** button to generate a username and then the **Generate Secret** button to generate a password. You will need **Username** and **Secret** below when setting up the alert source.
5. In the **Integration Vendor** section, choose iLert or your custom internal integration

![](../.gitbook/assets/autotask3%20%281%29.png)

## In iLert: Create an Autotask alert source <a id="create-alert-source"></a>

1. Go to the "Alert sources" tab and click on "Create new alert source"

![](../.gitbook/assets/autotask4%20%281%29.png)

1. In the **Name** section, enter a name eg. iLert
2. In the **Integration Type** section, choose "Autotask"
3. In the **Autotask Settings -&gt; Username** section, paste the API user username generated above
4. In the **Autotask Settings -&gt; Secret** section, paste the API user secret generated above
5. select your desired escalation policy and click the **Save** button

![](../.gitbook/assets/ilert%20%281%29.png)

1. On the next page, a Webhook URL is generated. You will need this URL below when setting up the extension callout in Autotask.

![](../.gitbook/assets/autotask6.png)

## In Autotask: Create Extension Callout <a id="create-extension-callout"></a>

1. Go to Autotask and then to **Admin -&gt; Extensions & Integrations**

![](../.gitbook/assets/autotask7.png)

1. Click the **Other Extensions & Tools** panel and then click on the **Extension Callout \(Tickets\)** link

![](../.gitbook/assets/autotask8.png)

1. Click on **New Extension Callout** 

![](../.gitbook/assets/autotask9.png)

1. In the **Name** section, enter a name eg. iLert
2. In the **URL** section, paste the **Webhook URL** that you generated in iLert
3. Ensure that **Active** is selected and click the **Save & Close** button

![](../.gitbook/assets/autotask10.png)

## In Autotask: Create Workflow Rule <a id="create-workflow-rule"></a>

1. Go to Autotask and then to **Admin -&gt; Workflow Rules**

![](../.gitbook/assets/autotask11.png)

1. Click the **New** button

![](../.gitbook/assets/autotask12.png)

1. In the **General -&gt; Workflow Rule Name** section, enter a name eg. iLert
2. Ensure that **Active** is selected
3. In the **Events -&gt; CREATED/EDITED** section, activate the **Created by** and the **Edited by** fields and choose **Anyone**

![](../.gitbook/assets/autotask13.png)

1. Scroll down to the **Actions** panel and in the **Then Execute Extension Callout** section choose the **iLert Callout** that you created above
2. Click on the **Save & Close** button

![](../.gitbook/assets/autotask14%20%281%29.png)

## FAQ <a id="faq"></a>

**Will incidents in iLert be resolved automatically?**

Yes, as soon as an Autotask Ticket is completed, the incident in iLert will be resolved automatically.

**Can I connect Autotask with multiple alert sources from iLert?**

Yes, simply create more Extension Callouts in Autotask.

**Can I customize the incident messages?**

No.

