Arquivos d.ts indicam que dentro desse arquivo pode ter apenas tipagens de TypeScript e nunca um código javaScript
Ex: Interface


Como trabalhar com layout de rotas 
<!-- <Routes>
      <Route path="/" element={<DefaultLayout />}>
        <Route path="/" element={<Home />} />
        <Route path="/history" element={<History />} />
      </Route>
</Routes> -->
No exempli acima, estamos dizendo que todas a páginas dentro de 
<!-- <Route path="/" element={<DefaultLayout />}> -->
Vão exibir o que DefaultLayout tem. No nosso caso, dentro de DefaultLayout temos o Heade, e queremos que todas as páginas tenham ele.


controlled / uncontroled
controlled - manter em tempo real o estado, a informação que o usuário insere na aplicação dentro de uma variável.
Sempre que o usuário insere um valor no input o estado é atualizado pra receber esse novo valor.

uncontroled - busca a informação do valor do input, apenas quando precisarmos dela.

React-hook-form
É uma biblioteca react que nos permite criar formulários com mais habilidades e atributos

Nessa aplicação vamos usar o register e handleSubmit
Register controla os inputs, e ele permite colocar vários atributos com a sintaxe {...register}, estamos permitindo que tudo o que ele oferece seja usado na nossa oplicação.


useEffect - Funcionalidade do React 
O que é ? 
Ele lida com efeitos colaterias, ou seja, ele tem uma reação após uma ação.

Sempre que queremos que uma função seja executada quando a página carregar e sempre que queremos observar uma váriável, usamos o useEffect

não colocomos ele dentro de uma variável 
Ele recebe 2 paramêtros. 
1 - Qual função vai ser executada
2 - Quando essa função vai ser executada. Pra isso, ele recebe um array [] e dentro desse array, passamos qual variável queremos que seja monitorada.
Então, quando essa variável monitorada mudal, quero que a função seja executada

Fazemos: Sempre que list mudar, executmos a função avisarAPI()

useEffect(() => {
  avisarAPI()
} ,[list])

Colocamos isso dentro do useEffect para não precisar repetir códgo para todas as vezes que avisarAPI precisar ser usada. 

Ele executa assim que o componente for exibido em tela e toda vez que a varíavel for alterada. 

Podemos colocar condições dentro do useEffect para determinar em que momento ele irá executar minha função.

Sempre precisamos por o array de dependencias.

Podemos querer executar um componente uma única vez quando ele for renderizado em tela, pra isso, basta passar o array de dependências vazio.
Por exemplo que queremos puxar dados de uma API, queremos que essa renderização aconteça apenas uma vez. 
Então fazemos :

useEffect(() => {
  //acessamos o link da api
  fetch('https://api.github.com/users/diego3g/repos')
  //pegamos a resposta e transformamos em um json
  .then(response => response.json)
  //depois devidimos o que vamos fazer com a resposta
  .then( data => {
    setList(data.map((item) => item.full_name))
  })
}, [])

Dessa forma será renderizado em tela todos os 20 primeiros repositórios do usuário selecioando pelo link da API.

Prop Drilling -> É quando tepos muitas propriedades APENAS para comunicação entre componentes

Como resolver Prop Drilling ? 
Usando Context API -> Podemos compartilhar informações entre VÁRIOS componentes ao mesmo tempo.


useReducer
Usamos esse hook pra armazenar informações mais complexas. 
Quando eu percebo que um estado precisa ser alterado com base no seu estado anterior, e está muito denso, com muitas linhas, exigindo calculos e usando  muitas informações, é hora de usar o useReducer para simplificar esse código.
Com ele temos um local fixo com todas as alterações que podem acontecer dentro de um estado selecionado.

sintaxe

- useReducer() recebe 2 paramêtros : {
  1º state - ele é o valor atual e em tempo real do estado
  2º action - qual ação o usuário quer realizar de alteração dentro da variável. ela é única pra indicar a ação do usuário pra realizar a mudança do usuário
}

precisamos tipar o estado, indicando qual vai ser o tipo dos dados que vão ser armazenados no estado.

setVariavel, não vai mais servir para alterar variavel, agora ela vai servir para disparar a função action e por isso, seu nome vai ser dispatch

const [variavel, dispatch] = useReducer((state: Cycle[], action) => {
  return state
}, [])

Precisamos enviar um objetos e dentrod ele, um type com qual é a ação a ser realizada