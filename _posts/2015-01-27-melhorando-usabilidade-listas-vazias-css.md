---
layout: post
title:  "Melhorando a usabilidade de listas vazias com CSS"
date:   2015-01-27 22:00:00
categories: css ux usabilidade front
---

É bem interessante ver como você desenvolvedor pode evitar o uso de js em várias situações no seu dia a dia. Recentemente encontrei um problema de usabilidade, e queria criar uma solução genérica o bastante para ser aplicada a todo o sistema em que estava trabalhando, de maneira simples e rápida (o sistema é o Acelerato).

O problema se baseava em definir o comportamento de listagens do sistema que estavam despadronizados ao longo das páginas. E eu estava cansado de criar if else`s para verificar se a listagem possuia algum elemento ou não.

Imagine que o usuário entre em uma tela de listagem em seu sistema. O ideal é que mesmo que não existam nenhum registro naquela listagem, você ofereça um feedback para o usuário, informando que não existem registros ali. Isto também se aplica para quando você realiza uma busca.

Renderizar uma tabela sem registro algum, não me deixa feliz, como usuário.

{% gist bruno2ms/217a520ddbc204e145c0 gistfile1.jsp %}

Acabei pensando em uma solução simples de CSS puro, que pode ser aplicada a várias situações do seu dia a dia.

{% gist bruno2ms/ec22dbd20bf93da0665f gistfile1.css %}
{% gist bruno2ms/ec22dbd20bf93da0665f gistfile2.jsp %}

Este pequeno código de CSS garante que um elemento com a classe .empty seja sempre oculto, isso se ele tiver algum outro elemento antes dele. Ou seja, se a lista tiver apenas o seu elemento .empty, ele estará visível, caso contrário, não.

Segue um exemplo funcionando. Aproveitei e coloquei uma animação de css pra quando os elementos da lista aparecem :P

<iframe width="100%" height="300" src="http://jsfiddle.net/bruno2ms/ks4VJ/1/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

Obs:
Para este método funcionar, você deve sempre renderizar a sua lista, antes do elemento .empty para que a regra de css faça algum efeito.
Da mesma forma, sempre que vc for adicionar um novo elemento á lista, deverá ser antes do elemento .empty.

Espero que tenham curtido.E que seja útil.
