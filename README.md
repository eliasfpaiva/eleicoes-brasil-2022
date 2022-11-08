# eleicoes-brasil-2022
Análise das eleições

## Obtenção dos dados
Iniciei coletanto os endereços para a obtenção dos boletins de urnas disponíveis no painel de [dados abertos do TSE, que você pode acessar clicando aqui](https://dadosabertos.tse.jus.br/dataset/resultados-2022-boletim-de-urna).

Para realizar a coleta usei o seguinte script via console do navegador Chrome.

`const urlsZipBoletins = [...document.querySelectorAll('a[href$=".zip"]')];`

`const linhas = urlsZipBoletins.map(l => (l.parentElement.parentElement.parentElement.parentElement.children[0].title + ';' + l.href + ';'));`

`const linhasConcatenadas = linhas.join('&*&*&*&*&*');`

A string resultante eu utilizei o [Sublime Text](https://www.sublimetext.com/) para fazer as quebras de linha substituindo a sequência '&*&*&*&*&*' por uma quebra de linha, obtendo assim um arquivo CSV com todos os links dos boletins de urna do país do primeiro e do segundo turno.

## Análise do segundo turno
