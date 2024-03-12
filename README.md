# Getit ad plugin
This guide describes how to integrate with our ad plugin via HTML script or natively.

At the moment, for maximum compatibility, we use 728x90 banners for desktop and 270x90 for mobile screens.

## HTML integration
### Step 1 
```
<!-- PLACE THIS ELEMENT IN HEAD-->
<script src="https://cdn.jsdelivr.net/gh/Getit-Tech/getit-script@main/getit-script.js"></script>
```

### Step 2
For each ad unit you create within your dApp, you will need to place the below HTML.
```
<!-- PLACE THIS IN BODY, FOR EACH AD UNIT YOU CREATE-->
<div id="ad_unit_name"></div>
 <script>
   window.getitAdScript.renderAdPlugin(
     {
       apiKey: {your_api_key_goes_here},
       walletConnected: {address ? address : ""},
       isMobile: {false | true}
       slotId: "1",
     },
     "ad_unit_name"
   );
 </script>
```
1. ```apiKey``` - will be given to you by the Getit team, it should be stored in privately.
2. ```walletConnected``` - here you should pass the connected wallet's address in the Ethereum format. Or nothing if the wallet is not connected.
3. ```isMobile``` - this is an optional parameter. If set to true, the ad request will always return a banner of the mobile format, regardless of the actual user's device type. Can be useful if the mobile banner format fits your desktop UI better.
4. ```slotId``` - the enumerator for the banner. If you are using multiple banners the number should be incremented by +1 for each next banner.
5. ```ad_unit_name``` - the name of your ad unit where the ad is going to be displayed. Shall be passed both inside the enclosing ```<div>``` tag and at the end of the rendering function.

## Native integration
If you prefer to integrate the script natively, then you can absolutely do it using the below guide.

### Script
You can download the script via this link:
``` https://cdn.jsdelivr.net/gh/Getit-Tech/getit-script@main/getit-script.js ```

### Usage example
If you plan to display ads in several places, for each place, you will need its own ad unit. Simply copy-paste the below code and increment ```slotId``` and change ```ad_unit_name```.
```
 window.getitAdScript.renderAdPlugin(
  {
    apiKey: {your_api_key_goes_here},
    walletConnected: {address ? address : ""},
    slotId: "1",
    isMobile: {false | true}
  },
  {ad_unit_name}
);
```
Finally, for each ad unit, add a new div with ```id="ad_unit_name"```.
```
<div id="ad_unit_name"></div>
```
