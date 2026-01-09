<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>USTI – Teste Chat Salesforce</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
<script>
 const openChat =
   new URLSearchParams(window.location.search).get("openChat") === "true";
 function initEmbeddedMessaging() {
   try {
     embeddedservice_bootstrap.settings.language = "pt-BR";
     embeddedservice_bootstrap.init(
       "00DOu000001GFQj",
       "USTI_Live_Agent",
       "https://axaus-travel--uatt.sandbox.my.site.com/ESWUSTILiveAgent1716401253738",
       {
         scrt2URL:
           "https://axaus-travel--uatt.sandbox.my.salesforce-scrt.com"
       }
     );
   } catch (e) {
     console.error(e);
   }
 }
 window.addEventListener("onEmbeddedMessagingReady", () => {
   if (!openChat) return;
   setTimeout(() => {
     embeddedservice_bootstrap.utilAPI.launchChat();
   }, 500);
 });
</script>
<script
 type="text/javascript"
 src="https://axaus-travel--uatt.sandbox.my.site.com/ESWUSTILiveAgent1716401253738/assets/js/bootstrap.min.js"
 onload="initEmbeddedMessaging()">
</script>
</body>
</html>
