<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Teste Chat Salesforce</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
       body {
           font-family: Arial, Helvetica, sans-serif;
           margin: 0;
           padding: 40px;
           background-color: #f5f5f5;
       }
       h1 {
           color: #333;
       }
       p {
           color: #555;
       }
</style>
</head>
<body>
<script type="text/javascript">
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
               // Se tiver ?openChat=true na URL, tenta abrir o chat
               if (shouldOpenChat()) {
                   tryOpenChat();
               }
           } catch (err) {
               console.error('Error loading Embedded Messaging: ', err);
           }
       }
       function shouldOpenChat() {
           const params = new URLSearchParams(window.location.search);
           return params.get('openChat') === 'true';
       }
       function tryOpenChat() {
           if (
               window.embeddedservice_bootstrap &&
               typeof embeddedservice_bootstrap.open === 'function'
           ) {
               embeddedservice_bootstrap.open();
           } else {
               // Aguarda o bootstrap estar pronto
               setTimeout(tryOpenChat, 500);
           }
       }
</script>
<script
       type="text/javascript"
       src="https://axaus-travel--uatt.sandbox.my.site.com/ESWUSTILiveAgent1716401253738/assets/js/bootstrap.min.js"
       onload="initEmbeddedMessaging()">
</script>
</body>
</html>
