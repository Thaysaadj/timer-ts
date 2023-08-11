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