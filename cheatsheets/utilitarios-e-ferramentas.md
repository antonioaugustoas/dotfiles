# Utilitários e Ferramentas

## converters/temperature.html
```html
﻿<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>temperature</title>
</head>
<body>

    <script src="https://cdn.jsdelivr.net/npm/@@popperjs/core@2.11.6/dist/umd/popper.min.js"></script>

    <div class="container mt-5">
        <div class="row">
            <div class="col-md-6 offset-md-3">
                <h1 class="text-center mb-4">Temperature Converter</h1>
                <div class="card">
                    <div class="card-body">
                        <form id="temperature-converter-form">
                            <div class="mb-3">
                                <label for="temperature-input" class="form-label">Temperature</label>
                                <input type="number" class="form-control" id="temperature-input" placeholder="Enter temperature">
                            </div>
                            <div class="mb-3">
                                <label for="unit-input" class="form-label">Unit</label>
                                <select class="form-select" id="unit-input">
                                    <option value="celsius">Celsius</option>
                                    <option value="fahrenheit">Fahrenheit</option>
                                </select>
                            </div>
                            <button type="submit" class="btn btn-primary">Convert</button>
                        </form>
                        <div id="conversion-result" class="mt-4 d-none">
                            <h5 class="text-center">Converted Temperature:</h5>
                            <p class="text-center" id="converted-temperature"></p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
    document.getElementById('temperature-converter-form').addEventListener('submit', function (event) {
        event.preventDefault();

        const temperatureInput = parseFloat(document.getElementById('temperature-input').value);
        const unitInput = document.getElementById('unit-input').value;
        const conversionResultElement = document.getElementById('conversion-result');
        const convertedTemperatureElement = document.getElementById('converted-temperature');

        let convertedTemperature;

        if (unitInput === 'celsius') {
            convertedTemperature = (temperatureInput * 9 / 5) + 32;
            convertedTemperatureElement.textContent = `${convertedTemperature.toFixed(2)} °F`;
        } else {
            convertedTemperature = (temperatureInput - 32) * 5 / 9;
            convertedTemperatureElement.textContent = `${convertedTemperature.toFixed(2)} °C`;
        }

        conversionResultElement.classList.remove('d-none');
    });
    </script>
</body>
</html>```

## time-conversion.html
```html
﻿<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title></title>
</head>
<body>
    elastic
</body>
</html>

foco: as 20h estar plugado na aula com uma tela para inserir e-mail


budismo
saúde
time bounded

01  email confirmation automatic
02. celular confirmation
03. form
04. firstname
05. lastname
06. email++
07. phone++
08. cpf
09. rg
10. address complete
    5. donation
    6. login

o usuário preencher e-mail e clicar em submit
o sistema receber o email
    validar a entrada=inspeção minuciosa
    registrar no banco
    gerar token
    disparar um e-mail para o usuário com esse token
o usuário recebe o e-mail, abre o e-mail e clica no link com esse token
o sistema receber o token
    validar o token
    se válido
        move e-mail de tabela temporária para fixa
        envia e-mail bem-vindo
    se nao válido, encerra```

## utm-generator.html
```html
﻿<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UTM Link Generator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f9f9f9;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            background: #ffffff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        h1 {
            font-size: 24px;
            color: #333;
        }

        label {
            display: block;
            margin-top: 10px;
            font-weight: bold;
        }

        input[type="text"], select {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 14px;
        }

        button {
            background-color: #007BFF;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 16px;
            border-radius: 4px;
            cursor: pointer;
        }

            button:hover {
                background-color: #0056b3;
            }

        .output {
            background-color: #f4f4f4;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            margin-top: 15px;
            font-family: monospace;
        }

        .hint {
            font-size: 12px;
            color: #666;
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>UTM Link Generator</h1>
        <p>Use this tool to generate UTM links for your marketing campaigns. Fill in the fields below to create a fully formatted UTM link.</p>

        <form id="utmForm">
            <label for="baseUrl">Base URL *</label>
            <input type="text" id="baseUrl" placeholder="E.g., https://www.example.com, https://store.mybusiness.com">

            <label for="utmSource">UTM Source *</label>
            <input type="text" id="utmSource" placeholder="E.g., google, facebook, newsletter, partner-site">

            <label for="utmMedium">UTM Medium *</label>
            <input type="text" id="utmMedium" placeholder="E.g., cpc (cost per click), email, social, banner, affiliate">

            <label for="utmCampaign">UTM Campaign *</label>
            <input type="text" id="utmCampaign" placeholder="E.g., blackfriday, launch2025, spring_sale, product_x_release">

            <label for="utmTerm">UTM Term (Optional)</label>
            <input type="text" id="utmTerm" placeholder="E.g., running shoes, premium account, 50% off">

            <label for="utmContent">UTM Content (Optional)</label>
            <input type="text" id="utmContent" placeholder="E.g., banner1, buttonA, text_link, video_ad">

            <button type="button" onclick="generateUTM()">Generate UTM Link</button>
        </form>

        <div id="outputContainer" style="display: none;">
            <h2>Your UTM Link</h2>
            <div class="output" id="utmOutput"></div>
            <button onclick="copyToClipboard()">Copy to Clipboard</button>
        </div>

        <div class="hint">
            <strong>Tips:</strong>
            <ul>
                <li><strong>Source:</strong> Define where the traffic comes from (e.g., google, facebook).</li>
                <li><strong>Medium:</strong> Specify the marketing medium (e.g., cpc, email).</li>
                <li><strong>Campaign:</strong> Use a clear and consistent campaign name (e.g., product_launch).</li>
                <li><strong>Term:</strong> For paid search campaigns, specify the keyword.</li>
                <li><strong>Content:</strong> Differentiate ads or links within the same campaign (e.g., button_top, banner_footer).</li>
            </ul>
        </div>
    </div>

    <script>
        function generateUTM() {
            const baseUrl = document.getElementById('baseUrl').value.trim();
            const utmSource = document.getElementById('utmSource').value.trim();
            const utmMedium = document.getElementById('utmMedium').value.trim();
            const utmCampaign = document.getElementById('utmCampaign').value.trim();
            const utmTerm = document.getElementById('utmTerm').value.trim();
            const utmContent = document.getElementById('utmContent').value.trim();

            if (!baseUrl || !utmSource || !utmMedium || !utmCampaign) {
                alert('Base URL, UTM Source, UTM Medium, and UTM Campaign are required fields.');
                return;
            }

            let utmLink = `${baseUrl}?utm_source=${encodeURIComponent(utmSource)}&utm_medium=${encodeURIComponent(utmMedium)}&utm_campaign=${encodeURIComponent(utmCampaign)}`;

            if (utmTerm) {
                utmLink += `&utm_term=${encodeURIComponent(utmTerm)}`;
            }

            if (utmContent) {
                utmLink += `&utm_content=${encodeURIComponent(utmContent)}`;
            }

            document.getElementById('utmOutput').textContent = utmLink;
            document.getElementById('outputContainer').style.display = 'block';
        }

        function copyToClipboard() {
            const utmOutput = document.getElementById('utmOutput');
            navigator.clipboard.writeText(utmOutput.textContent).then(() => {
                alert('UTM link copied to clipboard!');
            });
        }
    </script>
</body>
</html>```
