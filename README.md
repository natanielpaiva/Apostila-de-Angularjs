Apostila de AngularJs
====
![](AngularJS-large.png)
===

AngularJs é um framework Javascript criado pelos desenvolvedores do Google.
Hoje em dia temos vários frameworks que são para o desenvolvimento do lado cliente (client-side) e o Angular é um dos que mais tem se destacado nos últimos anos.

A idéia dessa apostila é mostrar o quanto o AngularJs é últil para que o desenvolvedor front-end consiga criar conteúdos dinâmicos de uma forma mais simples do que seria ele desenvolver o mesmo apenas em Javascript ou até mesmo utilizando algumas bibliotecas como Jquery, Backbonejs e etc.

#Por que aprender AngularJs?

Criar um sistema nunca é uma tarefa tão simples, pois é o tipo de coisa que as vezes começa pequeno mas ao longo do tempo a criança vai crescendo e tomando forma. A diferença é que alguns tomam forma de verdadeiros "monstrinhos" e outros são um pouco mais "bonitinhos", simples de entender, manutenível e etc.

Quando você aprende uma determinada linguagem é importante verificar se já existe algum framework criado para a mesma e se ele tem um número considerável de pessoas que contribuem com o seu aperfeiçoamento.

Existem muitos outros frameworks em Javascript atualmente no mercado, porém o Angular é um dos mais utilizados pelos desenvolvedores e é mantido por nada mais nada menos do que o Google, ou seja, pode ter certeza que você irá aprender um framework que realmente está no mercado e que é constantemente atualizado.

Algumas das vantagens de se utilizar o AngularJs são:

* Separação de conteúdo feita utilizando o padrão MVC(Separa model, controller e view).
* Two-way databinding: A alteração em alguma model reflete em sua view e caso a alteração seja feita na view também refletirá na model.
* Utiliza um modelo de programação declarativa, ou seja, utiliza templates que podem consumir dados e redesenhar sua forma atual de maneira simples e rápida.
* SPA (Single Page Application): Uma página na web que proporciona ao usuário uma experiência mais fluida, semelhante ao desktop tendo apenas uma página e assim recarregando seu conteúdo sem precisar carregar a página inteira.

Criando o primeiro projeto
===

Vamos criar o nosso primeiro projeto em AngularJs.
Não será necessário conhecimento prévio em alguma linguagem de programação( Sugiro que estude um pouco sobre HTML ), basta você seguir os passos do livro que você vai conseguir se adaptar com o framework e com a linguagem em si, o Javascript.

Siga cada passo sitado abaixo:

* Entre no site do AngularJs clicando [[aqui](https://angularjs.org/)](http://).
* Faça o Download da versão mais atual e estável no momento. Nesse momento a versão mais atual estável é a 1.3.x.
* Crie uma pasta em seu computador com o nome Estudos Angular.
* Crie na pasta de estudos uma outra pasta escrita projeto1.
* Dentro da projeto1 crie uma pasta chamada vendor e coloque o arquivo que você baixou chamado angular.min.js dentro dessa pasta vendor.


Arquivos para utilizar o Angular
===

Crie dentro da pasta do seu projeto um arquivo chamado index.html com o seguinte código:

~~~html
<!-- //projeto1/index.html -->
<!doctype html>
<html ng-app="Projeto1">
	<head>
		<title>Título da sua página</title>
	</head>
	<body ng-controller="PrimeiraController">
		Corpo da sua página <br />
		{{mensagem}}

		<script src="vendor/angular.min.js"></script>
		<script src="main.js"></script>
	</body>
</html>
~~~

Crie um outro arquivo na pasta raiz do seu projeto chamado main.js e coloque o seguinte código:

~~~javascript
//projeto1/main.js
var app = angular.module('Projeto1',[]);
app.controller('PrimeiraController', function($scope) {
	$scope.mensagem = "Olá, esse é o meu primeiro projeto em Angular";
});
~~~

Abra o seu arquivo index.html em algum navegador, de preferência que seja o google chrome. Note que em seu navegador vai aparecer o texto que estava na tag body e também o texto que você colocou dentro da variável $scope.mensagem que está dentro do seu arquivo main.js.
Como vimos anteriormente o Angular é Two-way databinding, ou seja, o conteúdo que estiver em sua model irá refletir na view e vice versa. Vamos ver isso de uma forma mais clara no seguinte código:

No index.html vamos colocar o seguinte trecho de código:

~~~html
<input type="text" ng-model="mensagem" /> 
~~~

Seu index.html completo ficará assim:

~~~html
<!doctype html>
<html ng-app="Projeto1">
	<head>
		<title>Título da sua página</title>
	</head>
	<body ng-controller="PrimeiraController">
		<input type="text" ng-model="mensagem" /> <br />
		{{mensagem}}

		<script src="vendor/angular.min.js"></script>
		<script src="main.js"></script>
	</body>
</html>
~~~

Agora recarregue o seu navegador e repare que o que está escrito em seu input é exatamente a mensagem que haviamos colocado anteriormente na variável $scope.mensagem e caso você altere o texto do input o mesmo é modificado também abaixo do input. Isso porque o Angular é Two-way databinding.

Você pode baixar o projeto1 clicando [aqui](https://github.com/natanielpaiva/curso-angular/tree/master/projeto1).

Conhecendo Controllers
====

Em angular uma controller é simplesmente um construtor em Javascript( uma function ) que você pode utilizar o argumento do angular chamado $scope.

Quando você coloca em seu HTML o ng-controller que é uma directive do Angular, o mesmo instancia um objeto de Controller com o construtor específico.

A utilidade da controller é:
* Setar o estado inicial do objeto $scope.
* Adicionar comportamentos ao objeto $scope.

Não utilize sua controller para:
* Manipulação do DOM. As controllers devem conter apenas as lógicas de negócio.
* Formatar input.
* Filtrar output.
* Compartilhar códigos entre controllers.
* Gerenciar o ciclo de vida dos componentes.




