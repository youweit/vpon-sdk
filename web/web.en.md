---
layout:         "default"
title:          "Web SDK"
lead:           "fantastic HTML5 ads you should not miss"
description:    ""
keywords:       "Keywords for this page, in the meta data"
permalink:       web/
lang:           "en"
---

#Overview
---
Vpon Mobile Web SDK enables mobile web developers to maximize their monetization on Android and iOS. <br>
<font color="red">* NOTE：It only supports ads on mobile site, it would not show any ad if you open your website on personal computer.</font>
<br>


#Requirement
---
1. The basic concept of HTML <br>
2. Registering a banner ID for Vpon Mobile Web<br>
3. Having the permission to modify code of mobile website
<br><br>

#Ad Formats
---
Vpon Mobile Web SDK supports the following formats:<br><br>

| Name              |    Size(WxH)  |
| :---------------- | :------------:|
| Banner            |    320x50     |  
| Medium Rectangle  |    300x250    |  


<br>
<br>

#Setups
---
##Basic Setup
1. You should insert the following snippet of code directly after the opening <body> tag on each page you want to load it:

```HTML
<body>
...
  <vpon vpon_ad_test="1"
        vpon_ad_licensy_key="your_first_vpon_banner_id_here"
        vpon_ad_format="320x50_mb"
        debug="true"></vpon>
...
  <vpon vpon_ad_test="1"
        vpon_ad_licensy_key="your_second_vpon_banner_id_here"
        vpon_ad_format="320x50_mb"
        debug="true"></vpon>
...
  <vpon vpon_ad_test="1"
        vpon_ad_licensy_key="your_third_vpon_banner_id_here"
        vpon_ad_format="300x250_mb"
        debug="true"></vpon>
...
  <script type="text/javascript"  src="http://m.vpon.com/sdk/vpadn-sdk.js"> </script>
</body>
```
Note:<br>
* You only allow to use 3 ads at most in one page and please use different banner ID for every ad.<br>
* You only need to put <font color="red">just one</font> JavaScript before "</body>" like the sample code above. <br>
* After saving the page, this code will load and initialize the SDK. You can load a test ad in the <vpon> tag. (If you want to see the official ad: vpon_ad_test="0")
<br>

## Advanced Setup

Name             |        Description                       | Necessary |  Example
:----------------------:| :-------------------------------:|:---:|:------------------------------------------------:
vpon\_ad\_licensy\_key| Banner ID                           |  Y   |<font color="red">Put your Vpon License Key</font>
vpon\_ad\_format      | Size：320x50\_mb, 300x250\_mb       |   Y |     “320x50\_mb”
vpon\_ad\_test        |   Test Ad                           | N   |   1(Yes)/0(No)，Default(Yes)
debug                 | Debugging information in console   |  N   |   true/false，Default:false
openTab               |If open a new tab to show ad's contents  |N    |  true/false，Default:true
<br>
<br>

#Sample Code
---
```HTML
<html>
  <head><meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
  </head>
  <body>
    <h1>The Test Page</h1>

    <div>
      <vpon vpon_ad_test="1"
            vpon_ad_licensy_key="Your Banner ID"
            vpon_ad_format="320x50_mb"
            debug="true"></vpon>
    </div>
    </br>
    <div>
      <vpon vpon_ad_test="1"
            vpon_ad_licensy_key="Your Banner ID"
            vpon_ad_format="300x250_mb"
            debug="true"></vpon>
    </div>
    <script type="text/javascript" src="http://m.vpon.com/sdk/vpadn-sdk.js"> </script>
  </body>
```

> **Note:**
>If you use iframe for embedding vpon's ad, please remember to modify the size of iframe to fit the right size of vpon's ad.
<br>
<br>


# Mobile Site DFP
---
This document provides instructions for using the mobile site DFP to display banner ads. If you're not familiar setting mobile web api, review the documents first: "Vpon Mobile Web SDK" to become familiar with this document. Then come back this page and follow the DFP setting steps.

## Generate tags
---
Check the "Enable single request" and place Header code into the HEAD element of the web page and Document body code into the page body where you want to show ad.


## Setting Inventory
---
Go to DFP [Here](https://www.google.com/dfp/):

1. Create Inventory.
2. Setting Name, Size, and other items.
3. Generate tags (choose Google Publisher Tag)

![MobileDPF_Eng]

## Setting Orders, Items and Creatives
To run a new ad campaign through DFP Small Business, you'll first need to create a new order. After creating the order, you'll need to create line items, add creatives, and approve the order before it can serve. For reserved line item types (sponsorship and standard), DFP will not reserve inventory until the order is approved.

### Creat Orders Manually
To create an order before running an inventory forecast:

1. In your DFP Small Business account, click the `Orders` tab.
2. Click `New order`.
3. Enter your order information in the appropriate fields.
> Order names must be unique within your network.
4. Enter your line item information.
5. Click Check inventory to ensure the order will have enough available impressions.
![Warning]
6. Click `Save`。Once you've created an order, you'll need to approve it before the line items are eligible to serve. See Approve an order to learn how.

### Create a Line Item

To create a line item:

1. In your DFP Small Business account, click the Orders tab.
2. Create a new order or click an existing order in the table.
3. Click New line item.
4. Enter a line item name. Line item names must be unique within your network.
5. Enter the inventory sizes of the creatives you plan to upload.
6. (Optional) Enter some comments about the line item that might help with trafficking the line item.
7. Enter the line item type, dates, quantity and cost.
8. Under Adjust delivery, configure your delivery settings (optional). See Optional delivery settings below for more information.
9. Select the inventory you want to target.

You can target at ad units, placements, or both. To find inventory to target at, you can either browse through your network’s inventory or perform a search.

The ad unit named after your network represents all of the ad units in your network. If you target the line item to this network-level ad unit, the line item will target any ad unit in your network.

Example：
![AppType.png]

10.Enter additional targeting criteria to target a specific audience (optional). If you don’t target the line item to any ad units or placements, then the line item will be set to serve as run-of-network. This means the line item can serve to any ad unit on your website.

11.Click `Save`.

### Upload a Creative

1. Click the line item where you'd like to add the creative. You can also create a new line item if needed.
2. Click Add creatives. All creatives and ad unit dimensions associated with your line item will be listed on the left-hand column. You can upload creatives to any unit size in this list.
3. You can either drag and drop multiple creatives into the line item or just add one at a time.

### Add only one creative
Click New creative and select the creative's dimensions. (Choose All → Third party)
![Moblie_DFP_creative]

### Creative settings
Input the snippet of code:

```html
<vpon vpon_ad_test="0"
       vpon_ad_licensy_key="Your license Key"
       vpon_ad_format="320x50_mb"
       debug="true"></vpon>
      <script type="text/javascript"  src="http://m.vpon.com/sdk/vpadn-sdk.js"> </script>
```
> **Note**: vpon vpon_ad_test="1" 爲開啓測試廣告， vpon vpon_ad_test="0"爲拉取正式廣告。

Example：
![MobileDFP_creativeSetting]


### Callback for traffic remnant ads
snippet of code is provided below:

```html
    <div id="Vpadn_tag"></div>
    <script src="https://www.googletagservices.com/tag/js/gpt.js"></script>
    <script type='text/javascript'>
    googletag.cmd.push(function() {
    googletag.defineSlot('write_your_ad_unit', [320, 50], 'Vpadn_tag').addService(googletag.pubads());
    googletag.pubads().enableSingleRequest();
    googletag.enableServices();
    });
    </script>

    <script>
    function vponCallBackMethod(adStatus){
    if (adStatus != 0) {
    googletag.cmd.push(function() { googletag.display('Vpadn_tag');});
    }
    }
    </script>

           <vpon vpon_ad_test="1"
            vpon_ad_licensy_key="write_your_license_key"
            vpon_ad_format="320x50_mb"
            debug="true"
            ad_request_callback="vponCallBackMethod"
            is_rotate="false"></vpon>

    <script type="text/javascript" src="http://m.vpon.com/sdk/vpadn-sdk.js"> </script>
```
> **Note**：

> 1. write_your_ad_unit: put the other ad unit, which got from inventory. This ad unit formate is like: `/network_ID/ad_unit` And this ad unit is target by the line item, which is the next ads you want to show when vpon lack of ads. For example, in this line item it includes Adsense script. Make sure that the subsequent ad requests that are passed-back from the third-party ad server to DFP are unique and therefore do not call that same third party for an ad.
> 2. [320, 50]： change it to the ad size you want.
> 3. vpon vpon_ad_test="1" is for test ad， vpon vpon_ad_test="0" is to get official ad
> 4. write_your_license_key：please put the vpon's Banner ID here
> 5. 320x50_mb：change it to the ad size you want: 320x50_mb or 300x250_mb

Example：
![DFP_WEB_CALLBACK]

Need more details to understand how its working, please take a look at this page:[GAM tags](https://support.google.com/dfp_sb/answer/1693146?hl=en)

# Getting Support
---
[DFP Small Business](https://support.google.com/dfp_sb/) <br>
[Google Developers DFP Banner Ads](https://developers.google.com/mobile-ads-sdk/docs/dfp/fundamentals#android)





# FAQ
---
## Still can't see any ad
Please check the following items:

* Please open the page by mobile browser not the personal computer.<br>
* Clean the cache, delete cookie and reload the page.

## Still can't solve it
Open the debug mode and send all of  "Vpadn-" informations to [Vpon FAE]




[Vpon FAE]: mailto:fae@vpon.com
[MobileDPF_Eng]: {{site.imgurl}}/MobileDPF_Eng.png
[AppType.png]: {{site.imgurl}}/AppType.png
[Moblie_DFP_creative]: {{site.imgurl}}/Moblie_DFP_creative.png
[MobileDFP_creativeSetting]: {{site.imgurl}}/MobileDFP_creativeSetting.png
[DFP_WEB_CALLBACK]: {{site.imgurl}}/DFP_WEB_CALLBACK.png
