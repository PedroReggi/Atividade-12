# HTML5 Local Storage – Armazenamento de dados no navegador

## 

Com HTML 5 é possível fazer um armazenamento de dados no lado do cliente. Para isso usamos a API Web Storege. Essa API acessa a área de armazenamento local do navegador sem limite de tempo, ou seja, os dados armazenados estarão disponíveis sempre que você usar essa página.

localStorage é também chamado de Web Storage ou Armazenamento local. localStorage é um objeto JavaScript que usamos para armazenar dados no navegador. Ele fornece métodos para armazenar e recuperar a informação. O uso da API é bem simples, é baseada em chave-valor.


---

## Método setItem

Esse é o método que usamos para armazenar valores. Sempre devemos passar uma chave como referência. No exemplo abaixo usei nome e idade como chaves.

```
window.localStorage.setItem(‘nome’, ‘Marta Silva Rocha’);
window.localStorage.setItem(‘idade’, 28);
```

Caso use o mesmo código acima, trocando apenas o nome “Marta Silva Rocha” e a idade “28” os dados anteriormente gravados serão sobre escritos, já que as chaves “nome” e “idade” permanecem as mesmas


---

## Debugando localStorage

Uma maneira rápida e fácil para ver o banco de dados localStorage no Chrome é usando as Ferramentas do Desenvolvedor do Chrome. Clique na guia Resources , selecione Local Storage. O painel da direita deverá exibir chave-valor. 


Agora o melhor mesmo é usar JSON para trabalhar com armazenamento local, assim podemos trabalhar com objetos. E outro detalhe, o tipo padrão de armazenamento é String. Isso deve ser considerado se você pretende usar os dados para fazer alguma operação matemática, por exemplo. Com JSON você foge dessa dificuldade com os métodos JSON.stringify e JSON.parse.
```
var usuario = { nome: "John Smith da Silva", idade: 29 };
window.localStorage.setItem('usuario', JSON.stringify(usuario));
```
Para recuperar o valor armazenado no objeto usamos o método parse:

```
var usuario = JSON.parse(window.localStorage.getItem('usuario'));
console.log(usuario.nome); // John Smith da Silva
console.log(usuario.idade); // 29
```

---

## Removendo valores

removeItem() tem o objetivo de apagar da área de transferência o par armazenado nome/valor. Segue o exemplo:

```
window.localStorage.removeItem('nome')//apaga o valor armazenado em nome
window.localStorage.removeItem('idade') //apaga o valor armazenado em idade
```

Podemos usar o método clear() também. Esse método não requer parâmetros e destina-se a apagar todo o conteúdo da área de armazenamento.
```
localStorage.clear();
```
---

## length()

Propriedade que mostra a quantidade de dados armazenados no objeto localStorage.

```
localStorage.length
```

--- 

## key()

Método que mostra o nome da chave que foi armazenada na posição passada. O Exemplo abaixo iria retornar o nome da primeira chave.

```
localStorage.key(0)
```
Caso queira ver o valor que foi armazenado nessa chave pode fazer:

```
localStorage.getItem(localStorage.key(0))
```
Todas as informações salvas no localStorage só serão removidas utilizando os métodos vistos ou se o usuário limpar os dados do seu navegador. Caso contrário ele pode fechar e abrir o navegador, as informações armazenadas continuarão no navegador.

---

 ### REFERÊNCIAS
  Site:
  https://www.kadunew.com/blog/html/html5-local-storage-armazenamento-de-dados-no-navegador
