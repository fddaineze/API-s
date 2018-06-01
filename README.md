# Modal

## Exemplo:
[HTML](modal/example/index.html) - 
[CSS](modal/example/css/custom.css) - 
[JS](modal/example/js/modal.js)

## API
[JS](modal/modal.js)

## Documentação
A ideia desta API é ser leve e prática, ela permite a criação de um modal totalmente customizável utilizando pouco html para estruturação.

A montagem do html é feita desta forma:

```html
<p data-md="janela1" >Janela #1</p>

<div class="md-box" data-id="janela1">
  <p data-close>Clique aqui para Fechar X</p>
  <h1>Modal</h1>
</div>
```
#### Estrutura (HTML)
No item que abrirá o modal, você precisará de:
* **tag "data-md"** que que aponta o modal a ser aberto;

No modal em si, você precisará de:
* **class "md-box"**   que diz ao js que isso é um modal;
* **tag "data-id"**    que define a chamada do item (apontado em data-md);
* **tag "data-close"** que define que este item fechará o modal em questão;
> O data-close não precisa de atributos extras. Este último não é obrigatório, uma vez que é possível fechar o modal clicando fora da caixa criada

#### Estilo (CSS)

```css
.md-content {
  border-radius:5px;
  background-color: #fff;
  padding: 20px;
}
```
Uma vez que o API tem como intenção ser totalmente customizável, não existe nenhum estilo padrão para o modal, cores de fundo, tamanho, precisam ser definidos manualmente. Para conseguir um melhor dominio, atente-se para a estrutura FINAL do código (após processado pelo js):

```html
<div class="md-box" data-id="janela2" style="display: flex;">
  <div class="md-content " data-id="janela2" style="display: inline-block;">
    <p data-close="">Clique aqui para Fechar X</p>
    <h1>Modal</h1>
  </div>
</div>
```
A recomendação é que se edite via css a classe "md-content" para estilizar o modal, uma vez que o clique FORA DELA fechará o modal.<br>
Em caso de uso de frameworks, como bootstrap, a recomendação é que se use o "container" junto ao md-box, e defina o tamanho do modal em colunas direto pelo js, na variável disponível no início do código, por exemplo:

```javascript
$(document).ready(function () {
  // Aqui você pode colocar variáveis extras ao modal,
  // útil em utilizações de frameworks
  var complemento = 'col-xs-12 col-md-6';
  ...
```