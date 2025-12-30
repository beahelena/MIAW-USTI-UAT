<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>USTI – Teste Chat Salesforce</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
<!-- Salesforce Embedded Messaging -->
<script type="text/javascript">
       // 🔹 Lê parâmetro da URL
       const urlParams = new URLSearchParams(window.location.search);
       const openChat = urlParams.get('openChat') === 'true';

       if (!shouldAutoOpenChat) {
		console.log("Auto-open desativado para esta URL");
		  return;
		}
		
		if (sessionStorage.getItem("chatOpened")) {
		  return;
		}
		
        let attempts = 0;
        const maxAttempts = 10;

        const tryLaunchChat = () => {
          attempts++;
          try {
            embeddedservice_bootstrap.utilAPI.launchChat();
            console.log("✅ Chat aberto automaticamente");
          } catch (err) {
            if (attempts < maxAttempts) {
              setTimeout(tryLaunchChat, 500);
            } else {
              console.warn("❌ Não foi possível abrir o chat automaticamente");
            }
          }
        };

        setTimeout(tryLaunchChat, 500);
	  });
       
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
               console.error('Error loading Embedded Messaging: ', err);
           }
       }
</script>
<!-- Loader oficial -->
<script
       type="text/javascript"
       src="https://axaus-travel--uatt.sandbox.my.site.com/ESWUSTILiveAgent1716401253738/assets/js/bootstrap.min.js"
       onload="initEmbeddedMessaging()">
</script>
</body>
</html>
