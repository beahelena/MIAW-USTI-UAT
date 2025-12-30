<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>USTI – Teste Chat Salesforce</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
<script type="text/javascript">
   const urlParams = new URLSearchParams(window.location.search);
   const openChat = urlParams.get('openChat') === 'true';
   function initEmbeddedMessaging() {
       try {
           embeddedservice_bootstrap.settings.language = 'en_US';
           embeddedservice_bootstrap.init(
               '00DOu000001GFQj',
               'USTI_Live_Agent',
               'https://axaus-travel--uatt.sandbox.my.site.com/ESWUSTILiveAgent1716401253738',
               {
                   scrt2URL: 'https://axaus-travel--uatt.sandbox.my.salesforce-scrt.com'
               }
           );
       } catch (err) {
           console.error('Error loading Embedded Messaging:', err);
       }
   }
   window.addEventListener('onEmbeddedMessagingReady', function () {
       if (
           openChat &&
           window.embeddedservice_bootstrap &&
           embeddedservice_bootstrap.utilAPI &&
           typeof embeddedservice_bootstrap.utilAPI.launchChat === 'function'
       ) {
           embeddedservice_bootstrap.utilAPI.launchChat();
           console.log('✅ Chat aberto automaticamente via utilAPI');
       }
   });
</script>
<script
   type="text/javascript"
   src="https://axaus-travel--uatt.sandbox.my.site.com/ESWUSTILiveAgent1716401253738/assets/js/bootstrap.min.js"
   onload="initEmbeddedMessaging()">
</script>
</body>
</html>
