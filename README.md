# Weather-Widget

README: Integração do OpenWeather com Softwares sem Suporte a JavaScript

Descrição

Este repositório demonstra como utilizar o serviço OpenWeather para exibir informações meteorológicas em aplicações que não suportam diretamente JavaScript, como o Power BI. Para contornar a limitação, utilizamos a API do OpenWeather e/ou um widget hospedado em HTML, que pode ser incorporado via iframe ou utilizado como uma fonte de dados.

# Como Funciona

O OpenWeather oferece diferentes formas de integração, incluindo:

API REST: Para obter dados meteorológicos em formato JSON ou XML.

Widget em HTML: Um recurso visual pronto que pode ser hospedado externamente.

Neste exemplo, o widget foi hospedado no GitHub Pages, tornando-o acessível via URL pública. Este URL pode ser utilizado em softwares sem suporte direto ao JavaScript.

# Configuração do Widget HTML

O widget foi gerado com o seguinte código:

<div id="openweathermap-widget-21"></div>
<script src='//openweathermap.org/themes/openweathermap/assets/vendor/owm/js/d3.min.js'></script>
<script>
    window.myWidgetParam ? window.myWidgetParam : window.myWidgetParam = [];
    window.myWidgetParam.push({
        id: 21,
        cityid: '3453643',
        appid: '1dac116f3328449e4e5ab79d1b0d9394',
        units: 'metric',
        containerid: 'openweathermap-widget-21',
    });
    (function() {
        var script = document.createElement('script');
        script.async = true;
        script.charset = "utf-8";
        script.src = "//openweathermap.org/themes/openweathermap/assets/vendor/owm/js/weather-widget-generator.js";
        var s = document.getElementsByTagName('script')[0];
        s.parentNode.insertBefore(script, s);
    })();
</script>

Este código foi hospedado no GitHub Pages e está disponível em:https://gabrielferrarezi.github.io/Weather-Widget/.

# Como Integrar em Softwares sem Suporte a JavaScript

# 1. Utilizar o Widget via iFrame

Se o software suporta HTML, mas não JavaScript, o widget pode ser incorporado como um iframe:

<iframe src="https://gabrielferrarezi.github.io/Weather-Widget/" width="100%" height="400px" frameborder="0"></iframe>

Exemplo de uso:

Power BI: Use um visual de conteúdo HTML ou um visual customizado para incorporar o iframe.

# 2. Consumir Dados da API do OpenWeather

Para softwares que suportam integração via API (como Power BI, Excel ou aplicações em Python), você pode consumir diretamente os dados JSON/XML da API OpenWeather.

Exemplo de URL da API:

http://api.openweathermap.org/data/2.5/weather?id=3453643&appid=1dac116f3328449e4e5ab79d1b0d9394&units=metric

# Passos:

Substitua o id pelo código da cidade desejada.

Utilize o appid da sua conta OpenWeather.

Consuma os dados em ferramentas como:

Power BI: Através da opção Obter Dados > Web.

Excel: Utilizando o recurso de consulta web.

Python: Usando bibliotecas como requests para consumir a API.

Dados Retornados (Exemplo JSON):

{
    "coord": {"lon": -46.6333, "lat": -23.5505},
    "weather": [{"description": "nuvens dispersas"}],
    "main": {"temp": 24.0, "humidity": 78},
    "name": "São Paulo"
}

# Casos de Uso

# 1. Dashboards em Power BI ou Excel:

Visualize dados meteorológicos atualizados em tempo real.

Personalize gráficos e tabelas com informações como temperatura, umidade e condições climáticas.

# 2. Aplicações Python:

Consuma os dados para análises avançadas.

Crie notificações automatizadas baseadas no clima.

# 3. Sites e Portais Web:

Incorpore o widget ou exiba dados meteorológicos usando a API.

# Vantagens

Flexibilidade: O OpenWeather pode ser usado tanto via API quanto widgets prontos.

Integração Simples: Funciona com diversas ferramentas, mesmo sem suporte direto a JavaScript.

Dados em Tempo Real: Informações atualizadas continuamente.

# Considerações

Certifique-se de proteger sua chave de API (appid) ao utilizar a API do OpenWeather, especialmente em aplicações públicas.

Ajuste os parâmetros de unidade (metric, imperial) e idioma conforme necessário.

Se tiver dúvidas ou quiser aprimorar a integração, sinta-se à vontade para contribuir com este repositório! 😊
