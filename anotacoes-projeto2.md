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