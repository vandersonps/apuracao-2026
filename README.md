# Apuração Presidencial 2026 por Região

Painel estático para acompanhar a apuração da eleição para presidente do Brasil em 2026. Os resultados são consultados diretamente nos dados oficiais do Tribunal Superior Eleitoral (TSE), pelo navegador.

## Funcionalidades

- Exibe resultados do Brasil e das cinco regiões, com mapas por região e estado.
- Mostra os dois candidatos mais votados, percentuais, votos e urnas/seções apuradas.
- Permite abrir uma região para ver os resultados por estado e, quando disponíveis, os resultados para governador.
- Permite alternar entre o primeiro e o segundo turno. O painel seleciona o segundo turno automaticamente a partir de 25 de outubro de 2026.
- Atualiza os dados a cada dois minutos enquanto a página está aberta e oferece atualização manual. Se o TSE limitar as consultas (HTTP 429), aumenta temporariamente o intervalo entre tentativas.
- Adapta-se a telas pequenas e respeita as preferências de tema escuro e movimento reduzido do dispositivo.

## Como executar

O projeto não requer instalação de dependências nem processo de build. Sirva o arquivo `index.html` em um servidor web estático e abra a página no navegador. Por exemplo, com Python:

```sh
python3 -m http.server 8000
```

Em seguida, acesse `http://localhost:8000`. É necessária uma conexão com a internet para carregar os dados e as fotos publicados pelo TSE. O painel não possui backend nem salva dados localmente.

## Fonte e interpretação dos dados

- Resultados e fotos: [resultados.tse.jus.br](https://resultados.tse.jus.br/).
- O cartão Brasil soma os dados dos estados e inclui o exterior quando disponível; os totais regionais consideram os estados que carregaram.
- O percentual de cada candidato é calculado sobre os votos válidos já totalizados. O percentual de urnas é calculado com as seções totalizadas em relação ao total de seções.
- Os dados de governador são consultados apenas para os estados da região aberta e podem não estar disponíveis.
- Os contornos dos mapas são baseados em `@svg-maps/brazil`, de Victor Cazanave, sob licença [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

## Arquivos

- `index.html` — aplicação completa, incluindo estrutura, estilos, mapas e lógica de consulta e renderização.
