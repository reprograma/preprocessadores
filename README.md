# SEMANA 9 - Pré-processadores

> Nessa semana aprenderemos sobre pré-processadores, utilizando como base o exercício do [Mundo Gelado](https://github.com/reprograma/responsivo/tree/master/exercicio-responsivo-do-zero/mundo-gelado-exercicio-resolvido).
Conforme formos aprendendo, as branches de cada aula serão atualizadas com os conteúdos vistos.

---

### [Aula 1](#aula-01)
#### Resumo:
Nessa aula pegaremos o execício do Mundo Gelado e analisaremos, tirando qualquer dúvida que ainda sobrou sobre CSS. 
Após isso começaremos a ver um pouco sobre pré-processadores, utilizando na prática o [SCSS](https://sass-lang.com/), aprendendo da [instalação](#instalação) até alguns conceitos como:
* [Variáveis](#variáveis)
* [Aninhamento/Nesting](#aninhamento)
* [Mixins](#mixins)

### [Aula 2](#aula-02)
#### Resumo:
Nessa aula aprendemos sobre:
* [Partials](#partials)
* [Imports](#imports)
* [Placeholders e Extends](#placeholders-e-extends)
* [Funções de cor do SASS](#funções-de-cor-do-sass)

---

## Aula 01
Utilizamos o pré-processador [SASS](https://sass-lang.com/) com a sintáxe .scss para poder aproveitar das vantagens desse recurso, mas quais são as vantagens ?
  * Utilizar funcionalidades que o css puro não suporta, como: variáveis, aninhamento, mixins, funções, imports, extends.
  * Evitar duplicação de código
  * Facilidade de código limpo
  * Manutenção de código
#### Instalação
Podemos utilizar dois gerenciadores de pacote para fazer a instalação do SASS.<br />
  * [gem](https://rubyinstaller.org/), baixando o rubyinstaller.<br />
  * [npm](https://nodejs.org/en/), baixando o node.<br />
Para verificar se a instalação ocorreu bem é só escrever <code>gem --version</code> ou <code>npm --version</code> no terminal, o resultado será a versão instalada:<br />

![gem_version](imagens-exemplo/gem--version.PNG)<br />

![npm_version](imagens-exemplo/npm--version.PNG)<br />

Após isso é só escrever **gem install sass** ou **npm install -g sass** e utilizar o *--version* para verificar se a instalação foi concluída:<br />
![sass_version](imagens-exemplo/sass-gem--version.PNG)<br />

Para gerar o arquivo scss da raiz do projeto podemos fazer o seguinte comando no terminal:<br />
sass {pasta do scss}/{nome do arquivo scss}.scss:{pasta onde você quer que o arquivo css seja gerado}/{nome do arquivo css que você quer que seja gerado}.css<br />
EX:<br />
  <code>sass scss/style.scss:css/style.css</code> <br />
E para que qualquer modificação gere um .css enquanto você edita o arquivo scss é só utilizar o *--watch*<br />
sass --watch {pasta do scss}/{nome do arquivo scss}.scss:{pasta onde você quer que o arquivo css seja gerado}/{nome do arquivo css que você quer que seja gerado}.css<br />
EX:<br />
  <code>sass --watch scss/style.scss:css/style.css</code><br />
  
#### Variáveis
SCSS:<br/>
![vars--example](imagens-exemplo/vars--example.PNG)<br />
CSS:<br />
![vars--example--css](imagens-exemplo/vars--example--css.PNG)<br />
#### Aninhamento
SCSS:<br/>
![navegacao--scss](imagens-exemplo/navegacao--scss.PNG)<br />
CSS:<br />
![navegacao--css](imagens-exemplo/navegacao--css.PNG)<br />

#### Mixins
Sem parametros:<br/>
![mixin--sem-parametros](imagens-exemplo/mixin--sem-parametros.PNG)<br />
Com parametros:<br/>
![mixin--com-parametros-sem-valor-padrao](imagens-exemplo/mixin--com-parametros-sem-valor-padrao.PNG)<br />
Com parametros e valor padrão:<br/>
![mixin--com-parametros-com-valor-padrao](imagens-exemplo/mixin--com-parametros-com-valor-padrao.PNG)<br />
[Para mais exemplos de mixins](http://blog.caelum.com.br/10-mixins-sass-que-voce-deveria-usar-em-seus-projetos/)

## Aula 02
#### Partials
Para modularizar nosso código e deixar mais fácil de configurar, conseguimos separar em arquivos chamados partials, que são pedaços de css separados em arquivos e que recebem um _ no começo do nome, para que o sass entenda que não deve gerar o código no css, só quando chamarmos por @import.<br/>
Ex: _base.scss <br/>
![exemplo-pasta](imagens-exemplo/sass-partials.PNG)<br />

#### Imports
Para fazer com que os nossos partials sejam gerados no css é necessário importá-los no arquivo .scss principal. <br/>
![imports](imagens-exemplo/imports-sass.PNG)<br />
**OBS: Lembrando que a ordem que a gente chama os @imports é a ordem que será gerado no css**

#### Placeholders e Extends
Assim como o mixin, os placeholders também são trechos de código que podemos reutilar, mas se ele faz a mesma coisa que o mixin, por que utilizarmos ? <br/>
Vamos exemplificar, criamos o seguinte mixin:<br/>
![mixin-height-display](imagens-exemplo/mixin-height-display.PNG)<br />
Quando aplicamos ele em dois lugares: <br/>
![chamada-mixin](imagens-exemplo/mixincall-height-display.PNG)<br />
O css gerado é o seguinte: <br/>
![css-resultado](imagens-exemplo/banner-destination-css.PNG)<br />
O ideal seria: <br/>
![css-resultado-ideal](imagens-exemplo/ideal-css.PNG)<br />
E é que os Placeholders fazem a partir do extend, para criar um placeholder fazemos o seguinte: <br/>
![placeholder-height-display](imagens-exemplo/placeholder-height-display.PNG)<br />
E chamamos assim: <br/>
![chamada-placeholder](imagens-exemplo/placeholdercall-height-display.PNG)<br />
O resultado gerado no css agora é como queriamos: <br/>
![css-resultado-ideal](imagens-exemplo/ideal-css.PNG)<br />
<br/>
Apesar de bem útil, o placeholder possui duas limitações:<br/>
  * Não podemos criar placeholders com parâmetros, como fazemos com os mixins.
  * Os placeholders possuem conflitos ao utilizar junto do @media, podendo gerar esse erro: <br/>
  You may not @extend an outer selector from within @media.<br/> 
  You may only @extend selectors within the same directive.<br/>
  
[Para mais exemplos de placeholders](https://blog.teamtreehouse.com/extending-placeholder-selectors-with-sass/)
<br/>
#### Funções de cor do SASS
O SASS possui algumas funções nativas e algumas dela são as de cores: <br/> 
http://sass-lang.com/documentation/Sass/Script/Functions.html</br>
Exemplo da função para deixar mais claro: <br/>
<code>lighten(#829dad, 20%);</code>


