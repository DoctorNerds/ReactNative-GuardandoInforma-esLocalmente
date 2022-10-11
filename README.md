# ⚛️ React Native: Guardando informações localmente

Esse é o projeto do curso **Guardando informações localmente** da formação em **React Native** estudado pelo Fábio Mori na [Alura](https://www.alura.com.br/).

## 📱 Projeto

O objetivo deste projeto é criar um aplicativo que armazena notas no seu celular. A aplicação deste projeto para a Escola Matriz está em armazenar, alterar e salvar notas como lembrete das tarefas dos projetos MatrizKIDS, MatrizCast e Matriz4YOU para serem lembradas e consultadas.
Veja alguns prints de como ficou a aplicação.

<img src="https://user-images.githubusercontent.com/101336111/195085880-937f483e-fc20-466a-b042-65feda4c4c6c.png" width="300" height="600"> <img src="https://user-images.githubusercontent.com/101336111/195085902-56daa7f8-8745-4566-9c11-e68e5cb204fa.png" width="300" height="600"> <img src="https://user-images.githubusercontent.com/101336111/195085909-6328d039-d65c-432f-bb66-9216d7fcae6e.png" width="300" height="600">
<img src="https://user-images.githubusercontent.com/101336111/195085920-129bd198-e068-4827-bd0e-310ef54fb5b4.png" width="300" height="600">
<img src="https://user-images.githubusercontent.com/101336111/195085924-3e9df956-1ec3-47a8-9afe-6e97bcd40c7d.png" width="300" height="600">
<img src="https://user-images.githubusercontent.com/101336111/195085952-20ea9229-4914-49ea-935d-f69fa12887ff.png" width="300" height="600">
<img src="https://user-images.githubusercontent.com/101336111/195085963-02fdb633-2c9c-4df9-a4a7-48a62930c2ed.png" width="300" height="600">
<img src="https://user-images.githubusercontent.com/101336111/195085977-b0a87325-4d28-451f-bf9b-7118df6037a0.png" width="300" height="600">

## 🧑‍💻 Palavras-chave

As tecnologias e ferramentas ensinadas pela [Alura](https://www.alura.com.br/) no projeto são:

- React Native
- SQLite
- AsyncStorage
- JSON

## 📲 O aprendizado do aluno Fábio Mori
### Deixa eu te contar uma história

Quem nunca parou para pensar e se lembrou que esqueceu de fazer uma coisa que tinha planejado, mas acabou esquecendo de fazer? Pois é, muitas vezes a rotina de um dia cheio de tarefas pode fazer com que você esqueça alguns compromissos, ou mesmo acabe não conseguindo gerenciar bem seu tempo por não ter uma visão geral de tudo aquilo que precisa fazer.
Além disso, ter um "check list" é sempre importante para organizar e planejar o seu dia de forma eficiente, não é? E nada como um bom e velho "caderno de notas" para poder nos ajudar com isso, porém, que tal um caderno de notas um pouco mais tecnológico do que aqueles com lápis e papel?
E o melhor, um caderno que cabe no nosso bolso e estamos sempre em mão, ou seja, o nosso celular! Este curso da [Alura](https://www.alura.com.br/), que desenvolveu uma ferramenta para salvar, editar e deletar notas, será muito útil para os membros da [Escola Matriz](https://trakto.link/escolamatriz), que poderão organizar e consultar todas suas notas sobre os projetos [MatrizKIDS](https://www.youtube.com/channel/UCYGSXBBqCbPdhOZ-hBmjlig), [MatrizCast](https://www.youtube.com/c/MatrizCast) e Matriz4YOU.

### O que eu aprendi?

- AsyncStorage
  - É uma API, guarda sempre uma string com o conceito de chave e valor.
  - Guarda informações de uma maneira parecida com o objeto JSON, em chaves e valores ["chave":"valor"], porém ambos devem ser strings.
  - Não gera o ID automaticamente.
  - Existe uma maneira de guardar objetos contento mais informações, transformando um objeto JSON em uma string e depois guardando essa string no AsyncStorage (para
  recuperar essa informação podemos receber seu conteúdo e depois transformá-lo no novamente em um objeto JSON). Para isso é necessário utilizar a função 
  `JSON.stringify()` que vai transformar nosso objeto em uma string e depois utilizar a função `JSON.parse()` para fazer o processo reverso.
  - Algumas limitações do AsyncStorage:
    - Só guarda strings.
    - Limitação de espaço para Android:
      - Máximo de 6MB, sendo 2MB por entrada.
    - Informações não são criptografadas.
    - Não consegue fazer consultas (só pega a informação inteira) e não lida com o conceito de relacionamento de dados (diferentes objetos que possuem dados comuns
    que se relacionam entre eles).
  
- SQLite
  - É uma API que não guarda apenas strings, mas também imagens e vídeos, por exemplo.
  - Consegue lidar com relacionamentos de dados.
  - Permite fazer consulta e filtros.
  - Informações são criptografadas.
  
- Entidade (em Banco de Dados):
  - Em modelagem, entidade é tudo aquilo sobre o qual desejamos guardar alguma informação. É um objeto existente no mundo real, com uma identificação distinta e 
  significado próprio. São coisas que existem no negócio, ou ainda, que descrevem o negócio em si. Se algo existe e proporciona algum interesse em manter dados
  sobre ele, isso caracteriza como uma entidade deste negócio. Sendo assim, ela é uma tabela em nosso banco de dados.
  - Exemplo:
    - Pessoa: A, CPF: 0123456789, é uma entidade uma vez que só pode existir uma única pessoa com o mesmo nome e CPF.
    - Clientes, funcionários, departamentos, fornecedores, são entidades de um banco de dados de uma empresa.
    
- Atributos:
  - São propriedades/características que identificam as entidades. 
    - Exemplos:
      - Entidade: cliente / Atributos: nome, endereço, telefone e cidade.
      - Entidade: funcionário / Atributos: salário, cargo e departamento.
  - Existem 4 tipos de atributos: simples, composto, multivalorado e determinante.
    - Simples: a grade maioria, não possui características especiais.
    - Composto: pode ser desmembrado em vários atributos simples.
      - Exemplo:
        - Atributo: endereço (rua, n°, complemento, bairro, CEP e cidade).
    - Multivalorado: o seu conteúdo é formado por mais de um valor.
      - Exemplo: 
        - Atributo: telefone celular (uma pessoa pode ter mais de um número).
      - É indicado colocando-se um asterisco precedendo o nome do atributo.
    - Determinante: identifica de forma única uma entidade, ou seja, não pode haver outro repetido/igual.
      - Exemplo: Atributo: CNPJ ou CPF.
      - É indicado sublinhando-se o nome do atributo.
      - Serão as chaves primárias no banco de dados e toda tabela precisa ter um atributo determinante.

- Para saber mais sobre atributos e entidades, ler este [artigo](https://www.luis.blog.br/analise-de-entidade-atributos-simples-compostos-multivalorados.html)

- Banco de Dados:
  - Compreende uma coleção de conjuntos de entidades do mesmo tipo
  

### ▶️ Rodando o Projeto

Instalando o AsyncStorage:
```
npm install @react-native-async-storage/async-storage@1.15.17
```
Instalando o SQLite:
```
expo install expo-sqlite@10.1.0
```
Com a pasta do projeto no computador no terminal, digite:
```
npm install
```
Agora, digite para iniciar o projeto:
```
npm start
```
