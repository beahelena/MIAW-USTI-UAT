<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>USTI – Teste Chat Salesforce</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
<!-- Salesforce Embedded Messaging -->
<script type="text/javascript">
   // 🔹 Parâmetro da URL
   const urlParams = new URLSearchParams(window.location.search);
   const openChat = urlParams.get('openChat') === 'true';
   function initEmbeddedMessaging() {
       try {
           embeddedservice_bootstrap.settings.language = 'en_US';
           // ✅ ÚNICA forma suportada de auto-open
           if (openChat) {
               embeddedservice_bootstrap.settings.prechatDisplay = 'expanded';
               sessionStorage.setItem('chatOpened', 'true');
           }
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
</script>
<!-- Loader oficial (NÃO TRUNCAR) -->
<script
   type="text/javascript"
   src="https://axaus-travel--uatt.sandbox.my.site.com/ESWUSTILiveAgent1716401253738/assets/js/bootstrap.min.js"
   onload="initEmbeddedMessaging()">
</script>
</body>
</html>
