# eleicoes-brasil-2022
Análise das eleições

## Obtenção dos dados
Iniciei coletanto os endereços para a obtenção dos boletins de urnas disponíveis no painel de [dados abertos do TSE, que você pode acessar clicando aqui](https://dadosabertos.tse.jus.br/dataset/resultados-2022-boletim-de-urna).

Para realizar a coleta usei o seguinte script via console do navegador Chrome.

`let urlsZipBoletins = [...document.querySelectorAll('a[href$=".zip"]')];`

`let linhas = urlsZipBoletins.map(l => (l.parentElement.parentElement.parentElement.parentElement.children[0].title.replace('Boletim de Urna - ', '') + ';' + l.href + ';'));`

`let linhasConcatenadas = (['Estado e turno;link'].concat(linhas)).join('&*&*&*&*&*');`

Com a string resultante em mãos eu utilizei o [Sublime Text](https://www.sublimetext.com) para fazer as quebras de linha substituindo a sequência '&*&*&*&*&*' por uma quebra de linha, obtendo assim um arquivo CSV com todos os links dos boletins de urna do país do primeiro e do segundo turno.

O arquivo resultante [pode ser acessado clicando aqui](./linksBoletinsUrnas.csv).

Este arquivo foi carregado no Jupter Notebook que criei para fazer as análises e pode ser acessado [clicando aqui](https://colab.research.google.com/drive/1wVW5QNYDLzCYTCWGxG83P8XowoXy-3Z2?usp=sharing).

## Análise do segundo turno
