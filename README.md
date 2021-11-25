# Scrap_sites_noticias

## Sobre o projeto

Esse projeto visa fazer a raspagem de dados dos seguintes  sites de notícias: g1, r7, folha, estadão, metro, globo, uol, terra, msn, buzzfeed, veja, ig, antagonista, oglobo, ny times, washington, cnn br, cnn en, bbc br e bbc en.

Os dados extraídos dessas páginas serão preferencialmente os da home page e a de últimas notícias. Quando disponível utilizaremos o feed RSS.

Para cada site foi criada uma função que gerará um arquivo .XLSX. Essa escolha foi feita porque cada site a ser raspado necessita de especificidades para a obtenção dos dados.

## Bibliotecas utilizadas:

O projeto utiliza Python 3 e as seguintes bibliotecas:

-   [selenium](https://www.selenium.dev/)
-   [requests](https://docs.python-requests.org/en/latest/)
-   [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
-   [re](https://docs.python.org/3/library/re.html)
-   [time](https://docs.python.org/3/library/time.html)
-   [urlib](https://docs.python.org/3/library/urllib.html)
-   [datetime](https://docs.python.org/3/library/datetime.html)


## Instruções

Caso o ambiente de execução não esteja em execução basta rodar todas as células. Com o ambiente em execução basta rodas a última célula.
Os arquivos são salvos na aba de arquivos do Colab.

## Funcionamento

O cerne de cada função é entender como cada página a ser pesquisada funciona e a partir disso extrair os dados com base em uma busca pelo código HTML da página.
Por exemplo, na página do G1 temos o seguinte código na home que é encapsulado e posteriormente extraídos os itens de interesse:

<br/><br/>

![image](https://user-images.githubusercontent.com/48839817/143485471-3d52fadb-b7a5-4c07-a4a5-88d0b461bbc6.png)

<br/><br/>
---

No caso do site apresentar opção RSS é possível fazer a extração de maneira semelhante à anterior, mas a estrutura se apresenta de maneira mais organizada, bastando extrair o código HTML que encapsula a notícia:

<br/><br/>

![image](https://user-images.githubusercontent.com/48839817/143485846-8c911a9d-3d3e-4a06-9b80-ccaf6c777c77.png)

<br/><br/>
---

Os sites que utilizam Java necessitam ser acessados pelo Selenium (utilizando o driver). Isso faz com que necessitem emular um navegador, e portanto esperar o carregamento da página. Excetuando esse aspecto o modo de acessar o item de interesse é semelhante ao do site regular:

<br/><br/>

![image](https://user-images.githubusercontent.com/48839817/143486209-d4d3f2b6-efd9-4ed2-95b6-9e62f7d6873d.png)

<br/><br/>
---

É preciso lembrar que cada página segue um padrão. Portanto, é possível que hajam diversos itens de interesse na página - o que necessita mais de uma busca por elementos HTML.


## Nota sobre privacidade

O script desenvolvido foi pensado para uso pessoal/pesquisa. Apesar disso, todos os arquivos robots.txt dos sites utilizados foram pesquisados para verificar a permissão de acesso. Portanto, não há restrição de acesso na data de criação desse script.
