# UTFPRCT-TEX

O UTFPRCT-TEX é um template LaTeX não oficial para trabalhos acadêmicos (teses, disser, trabalhos de conclusão, etc.) da Universidade Tecnológica Federal do Paraná (UTFPR) - Curitiba.

Este trabalho apresenta modificações do projeto [UTFPRPG-TEX](https://pt.overleaf.com/latex/templates/federal-university-of-technology-parana-ic-report/gkjvhwrtkvps)) mantido por Luiz. E. M. Lima, o qual é o maior responsável pelo estado atual do projeto. As alterações do template foram necessárias para alinhar as diferentes interpretações da ABNT presentes mesmo entre diferentes campi da UTFPR e implementar a NBR6023/2018 (referências).

A estrutura principal de ambos os trabalhos é baseada no template de trabalhos acadêmicos [abnTeX2](http://www.abntex.net.br), que atende aos requisitos das normas da Associação Brasileira de Normas Técnicas (ABNT) para produção de documentos técnicos e científicos brasileiros.

## Arquivos do Projeto

A pasta `utfprct-tex` contém os arquivos do template deste projeto e um exemplo de uso escrito pelo prof. Luiz. E. M. Lima (UTFPRPG-TEX).

Os arquivos do template são:

- `utfprct.cls`: arquivo de classe do template UTFPRCT-TEX
- `utfprct.tex`: arquivo LaTeX de trabalho acadêmico utilizando o template UTFPRCT-TEX
- `utfprct-dados.tex`: arquivo de dados do trabalho acadêmicos
- `abntex2-alf.bst`: arquivo com pequenas alterações do estilo alfanumérico *bibtex* do pacote `abnTeX2` para se adaptar a NBR6023/2018 (estilo *bibtex* padrão)
- `abntex2-num.bst`: arquivo com pequenas alterações do estilo numérico *bibtex* do pacote `abnTeX2` para se adaptar a NBR6023/2018
- `abntex2-alf-en.bst`: arquivo `abntex2-alf.bst` com conectores e termos traduzidos para o inglês
- `abntex2-num-en.bst`: arquivo `abntex2-num.bst` com conectores e termos traduzidos para o inglês
- `make.bat` (`makefile`): possui comandos para converter o arquivo `utfprct.tex` (default) para PDF e um comando para limpar os arquivos intermediários (`clean`) (vide comando `help`)

## Normas vigentes do Sistema de Bibliotecas da UTFPR (2020)

A orientação para entrega de trabalhos acadêmicos pode ser encontrada no [portal do aluno](http://portal.utfpr.edu.br/biblioteca/trabalhos-academicos/orientacao-para-trabalhos-academicos), publicada em 18/09/2017. No qual, estabele-se que os trabalhos devem estar de acordo com as normas da Associação Brasileira de Normas Técnicas (ABNT):

- **NBR 6023/2018**: Informação e documentação - Referências
- **NBR 6024/2012**: Informação e documentação - Numeração progressiva das seções de um documento - Apresentação
- **NBR 6027/2012**: Informação e documentação - Sumário - Apresentação
- **NBR 6028/2003**: Informação e documentação - Resumo - Apresentação
- **NBR 6034/2004**: Informação e documentação - Índice - Apresentação
- **NBR 10520/2002**: Informação e documentação - Citações em Documentos - Apresentação
- **NBR 14724/2011**: Informação e documentação - Trabalhos Acadêmicos - Apresentação
- **NBR 15287/2011**: Informação e documentação - Projeto de Pesquisa - Apresentação

É possível consultar as normas ABNT no site da biblioteca da UTFPR através dos seguintes passos:

1. Acesse o site da biblioteca da UTFPR: http://biblioteca.utfpr.edu.br/
2. Faça o login no sistema da biblioteca
3. Na barra de "Pesquisa Geral", insera a norma (e.g., NBR 6023/2018) e clique no botão "Pesquisar"
4. Ao terminar a busca, clique em "Pesquisa Target GEDWeb" (veja [figura](./docs/img/access_abnt_utfpr_bib.png))
5. Verifique se é a versão correta da norma procurada no atributo *Data*
6. Clique na imagem do documento para consultar

## Compatibilidade do projeto UTFPRCT-TEX com as normas vigentes

O projeto UTFPRCT-TEX envolve o projeto `abnTeX2` (v. 1.9.7). Sendo o pacote `abnTeX2` compatível com quase todas as normas vigentes na UTFPR, exceto a `NBR 6023/2018` (referências).

Por este motivo, modificações no pacote `abnTeX2` e no código do `UTFPRPG-TEX` foram necessárias para tornar o UTFPRCT-TE compatível com as principais características de formatação e os principais tipos de entrada *bibtex* da `NBR 6023/2018`. No entanto, a norma `NBR 6023/2018` é extensa e possui muitos novos recursos que podem ser referenciados, inexistentes na norma anterior `NBR 6023/2002` e, por isso, possíveis melhorias podem ainda ser necessárias neste aspecto para cobrir a norma no seu total.

## Formato de Entrega

A Instrução Normativa Conjunta nº 01/2018 – PROPPG/PROGRAD dispõe sobre o formato das versões finais enviadas às bancas de avaliação e depósito no Sistema de Bibliotecas da UTFPR [link](http://portal.utfpr.edu.br/documentos/pesquisa-e-pos-graduacao/proppg/instrucoes-normativas-conjuntas/in-conjunta-proppg-prograd-01-2018.pdf).

> Art. 1) As versões de Trabalhos de Conclusão de Cursos de Graduação, de Trabalhos de Conclusão de Cursos de Especialização, de Dissertações de Mestrado e de Teses de Doutorado enviadas aos integrantes das respectivas bancas examinadoras de qualificação e defesa final devem, obrigatoriamente, estar em **formato digital**.
>
>   * Faculta-se o envio em **formato impresso** apenas aos integrantes das bancas examinadoras externos ao quadro de servidores da UTFPR, desde que requerido pelos mesmos.
>
> Art. 2) O depósito das versões finais de Trabalhos de Conclusão de Cursos de Graduação, de Trabalhos de Conclusão de Cursos de Especialização, de Dissertações de Mestrado e de Teses de Doutorado no Portal de Informação em Acesso Aberto da UTFPR e nas Bibliotecas dos Câmpus será feito apenas no **formato digital**.

Para que o template UTFPRCT-TEX produza documentos no formato digital ou impresso  de entrega, as seguintes opções devem ser definidas na declaração da classe (`\documentclass`) do arquivo `utfprct.tex`:

#### Formato Digital

Implica na remoção de todas as páginas em branco, a fim de não dar a impressão de faltar informação durante a leitura do documento.

* `openany`: impressão da primeira página dos capítulos em qualquer posição (anverso ou verso)
* `pretextualoneside`: impressão dos elementos pré-textuais para começar em qualquer posição (anverso ou verso)

#### Formato Impresso

* `oneside` ou `twoside`: impressão dos elementos textuais e pós-textuais `oneside` (anverso) ou `twoside` (anverso e verso, se mais de 100 páginas)
* `openright`: impressão da primeira página dos capítulos no anverso.
* `pretextualtwoside`: impressão dos elementos pré-textuais para começar sempre no anverso


#### Formato PDF-A

Além do `formato digital`, a entrega de TCC, dissertação ou tese deve ser feita no formato **PDF/A**.

> O PDF/A é um formato de arquivo definido pela norma ISO 19005 para arquivamento de longo prazo de documentos eletrônicos, a fim de garantir que poderão ser reproduzidos com precisão no futuro. Um elemento fundamental para alcançar este objetivo é a exigência de que documentos PDF/A devam ser 100% autocontidos, ou seja, todas as informações necessárias para visualizar o documento de forma consistente devem estar presentes no arquivo. Isso inclui, entre outras coisas, o conteúdo propriamente dito (texto, imagens e gráficos vetoriais), as fontes utilizadas e as informações de cor. Não é permitido que um documento PDF/A dependa de fontes externas (por exemplo, programas de tipografia e hiperlinks).

Existem diversas categorias de [**PDF/A**](https://en.wikipedia.org/wiki/PDF/A) (e.g., PDF/A-1A, PDF/A-2, PDF/A-3), sendo que cada um deles possui diferentes requisitos para serem aceitos. A biblioteca da UTFPR não especifica nenhuma categoria, desde que esteja em algum formato PDF/A.

Uma das categorias mais básicas dentro do PDF/A-2 é o PDF/A-2B (*Basic*) e que já torna o arquivo adequado para o longo prazo de armazenamento, enquanto mantém seu aspecto visual. Para converter um PDF para **PDF/A-2B**, sugiro a ferramenta online da **PDFEN**: https://www.pdfen.com/

Outra categoria é o **PDF/A-1B**, cujo formato pode ser gerado ao tentar imprimir o documento PDF para outro PDF com o `Foxit Reader PDF Printer` (impressora de PDF do Foxit) e nas propriedades escolher na "Qualidade de Impressão" a categoria padrão `PDF/A-1b` (cuidado para não imprimir em escala de cinza). A mesma funcionalidade pode estar presente em outras impressoras de PDF (e.g., o *Adobe Acrobat Reader*).

Para validar se o PDF/A foi gerado corretamente, o programa [VeraPDF](https://verapdf.org/) pode detectar e validar a categoria do PDF/A do documento de entrada. Outra opção é abrir o arquivo no *Abobe Acrobat Reader*, no qual aparecerá um aviso informando que o documento PDF aberto é um PDF/A.

A conversão para PDF/A poderia ser feita através de algum procedimento de compilação do LaTeX, porém tive algumas dificuldades e não  consegui validar o arquivo gerado como PDF/A. A falta da ferramenta não é tão negativa, pois o procedimento só é necessário no momento de gerar a versão final e as alternativas citadas já satisfazem bem o requisito (*fico aberto à sugestões*).


# UTFPR-CT Latex Template

Unofficial LaTeX template for academic works (doctoral, master, and bachelor thesis, etc.) production of the Universidade Tecnológica Federal do Paraná (UTFPR), campus Curitiba.

This work was based on the UTFPR-PG project ([utfprpgtex](https://pt.overleaf.com/latex/templates/federal-university-of-technology-parana-ic-report/gkjvhwrtkvps)) maintained by Luiz E. M. Lima. The main foundation is based the [abnTeX2](http://www.abntex.net.br/) academic works template, which meets the standards requirements of the Brazilian Association of Technical Standards (ABNT) for development of technical and scientific Brazilian documents.