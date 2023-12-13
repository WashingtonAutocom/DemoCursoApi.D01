# esistem_curso_D01
# Desafio Back-end eSistemCurso
Parabéns por ter chegado até aqui. Estamos empenhados dentro de nosso possível para que toda nossa equipe possa chegar junto a um novo conhecimento de forma a crescer como equipe e time.

## Avisos antes de começar

-   Crie um repositório no seu GitHub **sem citar nada relacionado ao eSistem**.
-   Faça seus commits no seu repositório.
-   Envie o link do seu repositório para o email **eduprog@gmail.com**  c/c **helio.ribeiro@autocom-mg.com.br**.
-   Você poderá consultar o Google, Stackoverflow ou algum projeto particular na sua máquina.
-   Pode assistir as aulas novamente para esclarecer dúvidas.
-   Fique tranquilo, respire, assim como você, também já passamos por essa etapa. Boa sorte! :)


### Sobre o ambiente da aplicação:

-   Deve ser utilizado **Framework .net 7 ou superior**, em contraponto com nossos estudos.
- Lembre-se que valorizamos um bom padrão de projeto.

## Objetvo: eSistem Simplificado

Temos 3 (três) tipos de usuários, *Administradores*, *Gerentes* e *Vendedores*, todos tem acesso ao sistema, podem se utilizar de vários pontos, mas vamos atentar **somente** em alguns fluxos de alguns tipos de usuários.

## Requisitos:

### Usuários
- Para todos usuários deveremos ter Nome completo, Apelido, e-mail, CPF, Senha. CPF/CNPJ, e-mail e apelido, devem ser únicos no sistema. Sendo assim, seu sistema deverá permitir apenas um cadastro com estes dados. 
- Usuários do tipo *Administriadores* podem logar no sistema, cadastrar novos usuários e trocar senha de qualquer usuário. Claro que usuários *Administradores* podem acessar qualquer outra parte do sistema.
- Usuários do tipo *Gerentes*, podem listar usuários. Além de listar outros todos usuários, este tipo de usuário, poderá acessar todas as partes do sistema. Exceto criar novos usuários.
- Usuários do tipo *Vendedores* poderam acessar o sistema, listar pessoas do tipo cliente, mas não podem alterar seus dados e efetuar cadastros.
- Todos usuários podem logar no sistema e listar seus próprios dados.
- A senha é um segredo que após ser definida, nem mesmo seu dono poderá acessar.   
- Somente usuários que não são *Vendedores* podem liberar o cadastro de pessoas do tipo Cliente.
- Ao cadastrar um usuário o sistema deverá avaliar se sua senha é forte e deverá conter no mínimo 8 caracteres, contendo letras Maíusclas, Minusculas, Números e Símbolos. 
- Para se cadastrar um usuário a senha deverá ser verificada se está válida e bate com a repetição da mesma.

### Pessoas
- Teremos um cadastro de pessoas que terá os campos, Nome completo, documento, nome da cidade. ativo, liberado venda, observações, código alternativo.
- Código Alternativo e Documento que deverá ser aceito somente CPF ou CNPJ válidos e não poderam se repetir. Ou seja cada pessoa somente poderá ter um número de documento e um código alternativo. Ambos podem ser vazios.
- A pessoa a ser incluida deve ter sua propriedade ativo como verdadeiro e sua propriedade liberado venda como falso.
- Nome completo e nome da cidade não podem ser vazios.
- Poderá existir pessoa homonimas no cadastro.
- Somente usuários que não sejam *Vendedores* podem excluir uma pessoa, desde que liberado venda esteja como false.
- Somente usuários do tipo *Administradores* ou *Gerentes* podem liberar a pessoa para venda.
- Somente usuários do tipo *Administradores* ou *Gerentes* podem  desativar uma pessoa.
- Toda pessoa já será considaderada um cliente desde que liberado para venda.

### Produtos
- Teremos um cadastro de produtos com os campos, Descricao Completa, Descricao Resumida, Unidade, Preco de venda, Quantidade em Estoque, Ativo, Vendável, Código Barras.
- Código Barras não poderam se repeti ou podem ser vazios. 
- Descrição completa, descrição resumida e unidade não poderam ser vazias.
- Ao se cadastrar um produto, sua unidade deverá ser cadastrada e na tabela  produto deverá ser armazenada a sigla da unidade, que deverá existir na tabela de unidades.  
- Ao se cadastrar um produto a propriedade Ativo deverá ser true e vendável false. 
- Somente usuários que não sejam *Vendedores* podem excluir um produto.
- Somente usuários do tipo *Administradores* ou *Gerentes* podem liberar o produto para venda.
- Somente usuários do tipo *Administradores* ou *Gerentes* podem  desativar um produto.
- o *Preço de venda* não pode ser negativo.

### Unidades
- O cadastro de unidade deverá constar Sigla, descrição.
- Sigla e descrição deverão ser preenchidas.
- Sigla não poderá se repetir em toda base, ou seja, somente haverá um sigla para cada unidade.
- Somente usuários que não sejam *Vendedores* podem incluir, alterar, excluir unidades.
- Unidades que já foram utilizadas em um produto não podem ser excluidas. 


# Endpoints

* Deveremos ter todos endpoints de Create Read Update e Delete com suas validações, permissões e autorizações.
* Para pessoas
	* Endpoint que lista os clientes
	* Endpoint que lista todas pessoas
	* Endpoint que lista um pessoa
	* Endpoint que lista um cliente
* Produtos
	* Endpoint que lista todos produtos
	* Endpoint que lista todos produtos vendáveis.
* Usuários
	* Endpoint que lista todos usuários
	* Endpoint que lista todos usuários do Tipo Vendedores
	* Endpoint que lista todos usuários do Tipo Gerentes
	* Entpoint que lista todos usuários do Tipo Administradores


# Diretrizes principais para projeto

* Não deverá ser função do banco de dados validções do domínio.
* Não deverá ser função do banco de dados o controle de sequência de registros. 
* O sistema deverá rodar para 3 (três) bancos de dados, Sqlite, PostGresql e InMemory
* A base de dados de usuários a qual iremos chamar de eSistem_Identidade, deverá ficar em uma base separada da base de dados que conterá as demais tabelas e iremos chamar de eSistem. Escolham a melhor abordagem.
* Deveremos utiliza EF 7, FluentValidation, MediatR (Este caso se sintam confortáveis), padrões projeto CQRS e Clean code devem ser prioridade.
* Todo registro no banco de dados deverá ter uma chave primária sendo um GUID único. 
* Todo registro no banco de dados deverá ter um indice único de nome short_id que deverá ser gerado em base64 e ter no maximo 10 dígitos, podendo ser letras e números e não conter caracteres especiais, nem espaço em branco.
* Poderam ser criados quantos projetos acharem necessários.
* Tudo que foi passado aqui, não cabe discussão se pode ser melhorado ou feito de outra forma, para o todo, temos de usar o que aprendemos até o momento e criar de acordo com a necessidade. 
* 
* **Caso encontre algo que não vá funcionar e tenham certeza de uma melhor abordagem nos entregue a melhoria. A ideia aqui é ter um cadastro de usuário e cadatro de pessoas e produtos, para que possamos logar e consultar produtos e clientes para vendas**

## O que será avaliado e valorizamos :heart:

-   Documentação
-   **desenho de arquitetura**
-   Código limpo e organizado (nomenclatura, etc)
-   Conhecimento de padrões (CQRS, design patterns, SOLID)
-   Ser consistente e saber argumentar suas escolhas
-   Apresentar soluções que domina
-   Modelagem de Dados
-   Manutenibilidade do Código
-   Tratamento de erros
-   Cuidado com itens de segurança
-   Arquitetura (estruturar o pensamento antes de escrever)
-   Carinho em desacoplar componentes (outras camadas, service, repository)

## O que NÃO será avaliado :warning:

-   Fluxo de cadastro de usuários
-   Frontend (só avaliaremos a (API Restful)[https://www.devmedia.com.br/rest-tutorial/28912])


## O que será um Diferencial

-   Uso de Design Patterns
-   Documentação
-   Proposta de melhoria na arquitetura e no projeto


# Tempo para desenvolvimento

Para desenvolvimento deste projeto será dado 36 (Trinta e Seis) horas para o desenvolvimento do todo, desde a criação dos bancos de dados em todos os 3 tipos, assim como a estrutura de todo o projeto. O projeto em si poderá ser discutido entre os envolvidos, exceto Hélio e Eduardo por motivos óbivos. Cabe a cada um desenvolver seu projeto, dar sua melhor proposta como passado. 

Ao final faremos uma call com todos para apresentação e explicação de cada projeto e apresentaremos a melhor proposta de funcionamento. 

A melhor proposta e funcionamento terá um dia de folta entre o natal/2023 e ano novo/2024.

Boas festas.
