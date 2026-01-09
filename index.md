<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>USTI – Teste Chat Salesforce</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
<script>
 const OpenChat =
   new URLSearchParams(window.location.search).get("openChat") === "true";
 window.addEventListener("onEmbeddedMessagingReady", function () {
   if (!OpenChat) return;
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
