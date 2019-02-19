# Uma introdução ao JavaScript

Vamos ver o que há de tão especial em relação ao JavaScript, o que podemos fazer com essa linguagem, e quais outras tecnologias a utilizam.

## O que é JavaScript?

*JavaScript* foi criado primeiramente para *"dar vida a páginas web"*.

Os programas nessa linguagem são chamados *scripts*. Eles podem ser escritos diretamente em uma página HTML e executados automaticamente enquanto a página carrega.

Scripts são criados e executados como texto simples. Eles não precisam de preparação especial ou serem compilados para executar.

Nesse sentido, JavaScript é bem diferente de outra linguagem chamada [Java](https://en.wikipedia.org/wiki/Java_(programming_language)).

```smart header="Por que <u>Java</u>Script?"
Quando foi criado, JavaScript tinha outro nome: "LiveScript". Só que Java era muito popular na época, então foi decidido que estabelecer essa nova linguagem como "irmã mais nova" de Java ajudaria.

Porém, conforme evoluiu, JavaScript se tornou uma linguagem totalmente independente, com suas próprias especificações, chamada [ECMAScript](http://en.wikipedia.org/wiki/ECMAScript), e, hoje em dia, efetivamente não tem nenhuma relação com Java.
```

Hoje, JavaScript pode ser executado não só no navegador, como também no server, ou em qualquer dispositivo com um programa chamado [JavaScript Engine](https://en.wikipedia.org/wiki/JavaScript_engine).

Os navegadores tem engines nativas, também chamadas de "JavaScript Virtual Machine", ou "Máquina Virtual de JavaScript".

Diferentes engines tem diferentes "codinomes". Por exemplo:

- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) -- no Chrome e Opera.
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- no Firefox.
- ...há outros codinomes, como "Trident" e "Chakra" para diferentes versões do IE, "ChakraCore" pro Microsoft Edge, "Nitro" e "SquirrelFish" pro Safari, etc.

É bom lembrar os termos acima porque eles são utilizados em artigos na internet. Nós também os usaremos. Para exemplificar, se "um script X é suportado em V8", então, provavelmente, funcionará no Chrome e Opera.

```smart header="Como as engines funcionam?"

Engines são complicadas, mas os conceitos básicos são simples.

1. A engine (nativa se for um navegador) lê ("analisa") o script.
2. Então converte ("compila") o script para linguagem de máquina.
3. Então a máquina (geralmente um computador) executa o programa de maneira rápida.

A engine realiza otimizações para diferentes partes do processo. Até mesmo acompanha o script compilado conforme sua execução acontece, analisa os dados que são produzidos, e aplica otimizações no código de máquina de acordo com o que foi observado. Quando terminado, esse processo garante uma alta velocidade na execução do script.
```

## O que JavaScript PODE fazer dentro do navegador?

JavaScript Moderno é uma linguaggem de programação "segura". Não concede acesso de baixo nível à memória interna ou à CPU, já que foi criado para ser executado em navegadores, os quais não requerem esse tipo de acesso.

As funcionalidades de JavaScript dependem do ambiente em que está rodando. Por exemplo, [Node.js](https://wikipedia.org/wiki/Node.js) suporta funções que permitem JavaScript ler/escrever arquivos, fazer requisições na rede, etc.

No navegador, JavaScript pode fazer tudo relacionado à manipulações de péginas, interações com o usuário e o webserver.

Por exemplo, no navegador JavaScript pode:

- Adicionar HTML à página, alterar seu conteúdo, modificar estilos.
- Reagir à ações do usuário (clicks, movimentos do cursor, pressionar teclas).
- Enviar requisições através da rede para servers remotos, fazer download e upload de arquivos (também conhecido como [AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) e [COMET](https://en.wikipedia.org/wiki/Comet_(programming)))
- Obter e definir coockies, fazer perguntas ao visitante, exibir mensagens.
- Gravar dados no lado do cliente (client-side), também conhecido como "armazenamento local".

## O que JavaScript NÃO PODE fazer dentro do navegador?

As capacidades do Javascrpit no navegador são limitadas para a segurança do usuário. O objetivo é prevenir que uma página com más intenções acesse dados sensíveis ou prejudique as informações do usuário.

Como exemplos dessas restrições, temos:


- Javascript de um página web não consegue ler/escrever arquivos no disco rígido, copiá-los ou executar programas. Não tem acesso direto para as funções do SO (Sistem Operacional).

    Navegadores modernos permitem que o Javascript lide com arquivos, mas o acesso é limitado e só acontece se o usuário realizar certas ações, como "arrastar" arquivos dentro no navegador ou selecioná-lo através da tag `<input>`.
    
    Há formas de interagir com câmera/microfone ou outros dipositivos, mas para isso é necessário uma autorização explícita do usuário. Logo, uma página web que utiliza Javacript não pode acessar sua câmera sorrateiramente, observar suas ações e enviar para a [NSA](https://pt.wikipedia.org/wiki/Ag%C3%AAncia_de_Seguran%C3%A7a_Nacional).
    
- Diferentes tabs/janelas geralmente não sabem da exitência uma das outras. Há exceções, por exemplo quando uma janela usa Javascript para abrir outra. Mas mesmo nesses casos, Javascript de uma página pode não ter acesso à outra se elas são de diferentes origens (domínio, protocolo ou porta).

    Isso é chamado de "Política de Mesma Origem". Para contornar esse problema, *ambas as páginas* devem conter um código Javascript especial que lida com a troca de informações.

    Essa limitação é, relembrando, para a segurança do usuário. Uma página do `http://sitegenerico.com.br` que o usuário abriu não pode ser capaz de acessar outra tab aberta com `https://www.mail.google.com/` e roubar informações de lá.
    
- Javascript pode facilmente se comunicar através da rede com o servidor da página aberta. Porém, a capacidade de receber dados de outros sites/domínios é desencorajada. Apesar de possível, necessita de concordância explícita (expressa com os cabeçalhos HTTP) do lado remoto. Mais uma vez, isso é uma medida de segurança.

![](limitations.png)

Esses limites não existem se JavaScript for usado fora do navegador, por exemplo num servidor. Navegadores modernos também permitem plugins/extensões que podem requisitar mais permissões.

## O que torna JavaScript único?

Há pelo menos *três* grandes pontos sobre JavaScript:

```compare
+ Integração total com HTML/CSS.
+ Coisas simples de formas simples.
+ Suportado por todos os grandes navegadores.
```
JavaScript é a única tecnologia para navegadores que combina essas três características.

Isso é o que torna JavaScript único. Por isso é a ferramenta para criação de interfaces de navegadores mais difundida.

Quando se planeja aprender uma nova tecnologia, é importante verificar suas perspectivas. Então vamos ver ps tópicos mais modernos que afetam JavaScript, incluindo novas linguagens e capacidades dos navegadores.


## Linguagens "abaixo" do JavaScript

A sintaxe do JavaScript não se encaixa para todas as necessidades. Diferentes pessoas querem diferentes características.

Isso é algo esperado, porque projetos e seus requisitos são diferentes para cada um.

Por isso, uma enorme quantidade de novas linguagens surgiram, e por sua vez são *convertidas* para JavaScript antes de serem executadas no navegador.

Ferramentas modernas fazer a conversão ser bem rápida e transparente, permitindo que desenvolvedores programem em outras linguagens e auto-convertam seus programas "por baixo dos panos".

Exemplos de tais linguagens:

- [CoffeeScript](http://coffeescript.org/) é um "açúcar sintático" para JavaScript. Ele introduz uma sintaxe mais simples, permitindo escrever códigos mais claros e precisos. Normalmente desenvolvedores Ruby gostam. 
- [TypeScript](http://www.typescriptlang.org/) é focada em adicionar "tipagem de dados rigorosa" para simplificar o desenvolvimento e suporte de sistemas complexos. Foi desenvolvida pela Microsoft.
- [Dart](https://www.dartlang.org/) é uma linguagem autosuficiente, possuindo seus próprios mecanismos que executam em ambientes externos ao navegador (como aplicativos móveis). Foi inicialmente oferecido pelo Google como substituto do JavaScript, mas hoje em dia os navegadores requerem que seja convertido para JavaScript como os outros acima.

E há mais. Claro que, mesmo que se use uma dessas linguagens, deve-se também saber JavaScript para realmente entender o que está acontecendo.

## Resumo
- JavaScript foi inicialmente criado como uma linguagem apenas para navegadores, mas agora é usado em diversos outros ambientes também.
- Hoje, JavaScript tem uma posicão de destaque como a linguagem para navegadores mais adotada, com integração total ao HTML/CSS.
- Há muitas linguagems que são "traduzidas" para JavaScript e oferencem certas características. É recomendado que se dê uma olhada nelas, pelo menos brevemente, depois de dominar JavaScript.
