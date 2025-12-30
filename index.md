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
<h1>Teste do Chat Salesforce</h1>
<p>Esta página serve apenas para validar o Embedded Messaging.</p>
<!-- Salesforce Embedded Messaging -->
<script type="text/javascript">

        function initEmbeddedMessaging() {

            try {

                embeddedservice_bootstrap.settings.language = 'en_US'; // ou pt_BR se estiver habilitado

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
<script

        type="text/javascript"

        src="https://axaus-travel--uatt.sandbox.my.site.com/ESWUSTILiveAgent1716401253738/assets/js/bootstrap.min.js"

        onload="initEmbeddedMessaging()">
</script>
</body>
</html>
 
