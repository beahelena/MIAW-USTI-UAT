<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>USTI – Teste Chat Salesforce</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
<script>
 /* ===============================
    CONTROLE VIA URL (?openChat=true)
 =============================== */
 const urlParams = new URLSearchParams(window.location.search);
 const openChat = urlParams.get("openChat") === "true";
 function initEmbeddedMessaging() {
   try {
     embeddedservice_bootstrap.settings.language = "en-US";
     embeddedservice_bootstrap.init(
       "00DOu000001GFQj",
       "USTI_Live_Agent",
       "https://axaus-travel--uatt.sandbox.my.site.com/ESWUSTILiveAgent1716401253738",
       {
         scrt2URL: "https://axaus-travel--uatt.sandbox.my.salesforce-scrt.com"
       }
     );
   } catch (err) {
     console.error("Error loading Embedded Messaging:", err);
   }
 }
 window.addEventListener("onEmbeddedMessagingReady", function () {
   if (!openChat) {
     console.log("Auto-open desativado (URL sem openChat)");
     return;
   }
   let attempts = 0;
   const maxAttempts = 10;
   const tryLaunch = () => {
     attempts++;
     try {
       embeddedservice_bootstrap.utilAPI.launchChat();
       console.log("✅ Chat USTI aberto automaticamente");
     } catch (e) {
       if (attempts < maxAttempts) {
         setTimeout(tryLaunch, 500);
       } else {
         console.warn("❌ Falha ao abrir chat automaticamente");
       }
     }
   };
   setTimeout(tryLaunch, 500);
 });
</script>
<script
 type="text/javascript"
 src="https://axaus-travel--uatt.sandbox.my.site.com/ESWUSTILiveAgent1716401253738/assets/js/bootstrap.min.js"
 onload="initEmbeddedMessaging()">
</script>
</body>
</html>
