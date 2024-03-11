# Script integration guide

## Link
Script may be integrated via this link:
``` https://cdn.jsdelivr.net/gh/Getit-Tech/getit-script@main/getit-script.js ```

## Usage example
If you need to integrate multiple ad container, simply copy paste this code and increment slotId and change ad_container_name and add new div with this id
```
 window.getitAdScript.renderAdPlugin(
  {
    apiKey: {your_api_key_goes_here},
    walletConnected: {"" or pass an address from whatever wallet you are using on your website},
    slotId: "1" //pass the slot id from 1,
    isMobile: bool // this one is optional, may be used if you need to always display mobile or desktop ad. True if should always be mobile.
  },
  {ad_container_name} //here you should pass id of a container you want to display ad at
);
```
```
<div id="adContainer"></div>
```
## Mock integration
```
<!-- THIS SHOULD BE IN HEAD-->
<script src="https://cdn.jsdelivr.net/gh/Getit-Tech/getit-script@main/getit-script.js"></script>

<!-- THIS SHOULD BE IN BODY-->
<div id="adContainer"></div>
 <script>
   window.getitAdScript.renderAdPlugin(
     {
       apiKey:"",
       walletConnected: "",
       slotId: "0",
     },
     "adContainer"
   );
 </script>
```
