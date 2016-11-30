---
layout: post
title:  "Workshop: Modelo de negócio para Blog de Moda"
date:   2016-11-29 20:30:23 -0300
categories:
  - Negócios
image: negociosblog.jpg
---

Durante esses meus anos afastada do blog eu fiz várias coisas, uma delas foi trabalhar com desenvolvimento de aplicativos. Mas que relação isso tem com modelo de negócios? Como eu era uma pessoa de humanas no meio dos desenvolvedores, acabei me direcionando mais para a área de negócios e estudei bastante sobre planos, modelos, canvas, proposta única de valor e como reter usuários.

Como eu sempre tive contato com algumas blogueiras, decidi aproveitar esse conhecimento que adquiri e aproximadamente 1 ano atrás eu ministrei um workshop para preparar um **plano de negócio para blog de moda** e hoje decidi compartilhar com vocês o material que preparei.

O workshop é direcionado para o estrutura de um business model canvas e como preenchê-lo. Para isso, você deve entender que o seu blog é a sua empresa e que todas as áreas do canvas são relativas ao funcionamento dele. Confira a definição de canvas ;)

### Business Model Canvas

A ferramenta chamada de Quadro de Modelo de Negócios (Business Model Canvas), criada por Alex Osterwalder e Yves Pigneur, serve para planejar e visualizar as principais funções de um negócio e suas relações.

Ao fornecer uma visão holística e flexível do modelo de negócios, o Quadro auxilia os empreendedores nos processos de criação, diferenciação e inovação, aprimorando seu modelo de negócios para conquistar mais clientes e lucros.

Fonte: [Sebrae](http://www.sebrae.com.br/sites/PortalSebrae/bis/quadro-de-modelo-de-negocios-para-criar-recriar-e-inovar,a6df0cc7f4217410VgnVCM2000003c74010aRCRD)

Ah, além disso, no workshop eu ainda abordo estratégias de **aquisição, retenção e monetização de usuários**. E aí, não dá para perder essa!

### Faça o download gratuito!


<style>
		.emailTxt {
			border: 1px solid #34EE8A;
			border-radius: 10px;
			background-color: white;
			width: 500px;
			color: #303030;
			text-align: center;
			padding: 5px;
			margin-bottom: 10px;
			font-size: 14px;

		}

		.centerAlign {
			text-align: center;
		}

		.sendButton { 
			width: 200px;
			border: 0;
			border-radius: 10px;
			background-color: #F831D3;
			color: white;
			text-align: center;
			padding: 5px;
			font-size: 16px;
			margin-top: 10px;

		}

		.hidden { 
			display: none;
		}

		.downloadA {
			font-size: 24px;
			color: #34EE8A;
			text-decoration: none;
			padding-top: 10px;

		}

</style>


<p class="centerAlign">
	<input type="text" class="emailTxt" id="nameInput" placeholder="Nome"><br>
	<input type="text" class="emailTxt" id="emailInput" placeholder="Email"><br>
	<button class="sendButton" id="sendBtn">Download</button></p>

<div class="download hidden" id="downloadDiv">
	<p class="centerAlign"><a class="downloadA" href="http://dudseofusca.com/arquivos/bmcanvas_dudseofusca.pdf">Clique para fazer download</a></p>
</div>

<script src="https://www.gstatic.com/firebasejs/3.6.2/firebase.js"></script>
<script>
  // Initialize Firebase
  var config = {
    apiKey: "AIzaSyAGNKdjRHKUP0aakrxVeXLxTu_eQghz5M0",
    authDomain: "leads-duds-e-o-fusca.firebaseapp.com",
    databaseURL: "https://leads-duds-e-o-fusca.firebaseio.com",
    storageBucket: "",
    messagingSenderId: "793449281415"
  };
  firebase.initializeApp(config);

var download = document.querySelector('#downloadDiv')

document.querySelector('#sendBtn').addEventListener('click', function() {
 	download.classList.remove('hidden');
 });

var name = document.querySelector('#nameInput')
var email = document.querySelector('#emailInput')

document.querySelector('#sendBtn').addEventListener('click', function() {
	firebase.database().ref().child('leads').push().set({
		name: document.querySelector('#nameInput').value,
		email: document.querySelector('#emailInput').value, 
	});
});
</script>

Qualquer dúvida no preenchimento do canvas é só deixar um comentário aqui ou na [fanpage do Duds e o Fusca](https://www.facebook.com/dudseofusca/). **Bora monetizar** o/

Tem uma sugestão de conteúdo para blog? Conta aqui nos comentários!
