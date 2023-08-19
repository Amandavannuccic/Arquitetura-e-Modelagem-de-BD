# Arquitetura-e-Modelagem-de-BD
Aula de 11/08/2023
Nunca armazena o dado computado 

Banco de dados: [e estruturado e tem um proposito (um caderno com senhas pode ser um banco de dados)

SGBD: Sistema gerenciador de banco de dados em ingles a sigla é DBMS Data base Menegement sistem = é um software/ programa  que gerencia os dados dentro dele.
Exemplo: MySQL, Oracle.

Por que surgiu?
Para digitalizar arquivos, guardar informações.

Utilitários em comum do SGBD:
- Backup
- Restore
- reorganização de arquivos: existe a criação de dados, exemplo criação de arquivos, no arquivo tem dados, se com o tempo um dado for apagado o tamanho do arquivo não é diminuido. a Reorganização de arquivos serve justamente para não acontecer essa ocupação de espaço de arquivos sem o numero de dados iniciais.
- Carregamento (loading)
- Transações: Possuiem atomissidade, consistencia, isolamento, durabiçlidade.
- Consistencia:

- Banco de dados não relacional não garente as propriedades de transação.
  
  Aula 17/08/2023

Quantos usuários o BD suporta?  
Banco de dados mono usuário : feito para um unico usuário

Multiusuários: Varios usuários, mesmo banco para todos

Quanto a localização dos dados:
Centralizados: Dados distribuídos em uma unica localidade fisíca.
Problemas: 
1) Quebrou perdeu .
2) Quanto mais longe estiver, mais lento.

Distribuídos: 
Dados distribuídos em várias localidades.
1) Não perde acesso, pois se o servidor consultado cair, ele busca o mais próximo. (Oracle)

Neste semestre trabalharemos com:
Banco de dados relacional, mono e multi usuários e localização centralizada.
 
BD Orientado a objeto:
Vantagem = ex: no git, todos vão mexer no mesmo arquivo e geralmente acontecem conflitos.
no caso o código está todo dividido, então dificilmente duas pessoas estrão mexendo no mesmo arquivo.


Componentes no SGBD 
Dentro do sgbd temos varios blocos, um deles é a segurança de usuário.
o usuário loga e conversa com o sgbd usando comandos sql, ou seja no sgbd não importa se quem envia comando é uma pessoa ou uma máquina.


Processador de consulta.
Verifica se o comando é valido, destrincha o que você escreveu e entende o que voccê quer.
após o entendimento ele vai para o gerenciador de armazenamento.

Gerenciador de aramazenamento.
Onde será armazenado, permissões (autorização de usuários), integridade de dados ( se tiver 10 registros e você pedir para apagar o 20 ele da erro, pois o 20 não existe),e mais.

Dicionário de dados: 
Os arquivos são traduzidos em tabelas.


Gerenciador de buffer:
O buffer aproveita resultados de pesquisas anteriores, e isso acontece em servidores com muita memória ran.

índices:
Índices você cria na mão, o profissional de DB é quem cria e a finalidade é aumentar a possibilidade de acessos.

Dados estatísticos;
São gravados o tempo de cada operação, e ele usa esses dados para sempre tornar as pesquisas mais rápidas.

Log:
Faz por transação e grava tudo o que você vai modificando o registro fica.

Como se trabalaha para criar um banco?
1) Analisa o problema e entende o negócio.
2) Mapeia como os dados circulam.
3) Defini tudo o que deve ser armazenado.
4) Agrupa os dados em conceitos. (Denominado em modelagem conceitual)
5) Onde serão guardados os dados, em que formato.
6) Criar o Banco fisicamente (SQL)

Sistema de banco de dados.
É o que iremos desenvolver aqui.


Aula 18/08 
Modelagem
Todo processo de modelagem de um problema começa em entender o problema.

Modelo Entidade de relacionamento.

Entidade é qualquer coisa que você tem com Dados a armazenar.
Nem tudo você vai armazenar, nem tudo você vai guardar.
Por exemplo: Uma pizzaria na parte de pedidos, o que você tem envolvido ali, pensando em conceitos?
- Cardápio
isso é algo que você deve armazenar?
Sim! 

- O pedido
Isso deve ser armazenado?
Sim

- O preço
Isso deve ser armazenado?
Sim!

Como você sabe as coisas que se deve armazenar?
No cardápio -> Pizzas -> Nome, Ingredientes, Preço.
Ainda no cardápio -> Bebidas -> nome, preço, tipo.

Comanda -> Mesa, Atendente, Itens -> quantidade, produto

Parece uma coisa boba, mas tem muitas informações envolvidas! 

O que entra em entidade?
O cardápio tem alguma lista armazenada nele?
Sim! 

Repare que em Pizza tem "ingredientes", cada ingrediente tem uma característica (nome) 
Como os ingredientes não variam de nome ou seja, tomate será tomate em todo lugar, isso indica que ele é uma entidade.
Geralmente entidades vem como título no plural, outro exemplo seria "Itens" em "Comanda".
Ou seja, itens e ingredientes são entidades.

Se por acaso sua pizzaria tivesse dois cardápios, então cardápios também seria uma entidade.

Se cardápios existir, Ingredientes continua sendo uma entidade?
Não tem problema, são coisas separadas.

#### Você pode pensar que cada entidade é uma tabela!

Banco de cados conceitual:
Não cadastra dois dados iguais.

Por isso é importante descobrir o que o torna único!

Se tem duas coisas que não podem repetir, uma deve ser a principal! 

Outro exemplo:
Digamos que eu tivesse uma entidade chamada Local, com latitude, longitude e nome.

Qual seria o identificador deste cara?
Latitude e longitude! 

E agora?
Neste caso podemos usar a união dos dois!
Exemplo: Digamos que latitude = 1, longitude = 1 e nome é lalala.
não poderá ser cadastrado latitude como 1 e longitude como 1, pois ja está cadastrado.
e assim em diante, ou seja se ja tiver lat = 10 e longi = 20, não poderá ser cadastrado lat = 10 e longi = 20,

Porém, neste caso, isso é possível para combinação dos dois, ou seja, seguindo o exemplo se lat = 10 e longi = 20, 
existe a possibilidade de cadastrar lat = 10 e longi = 21, pois isso é uma nova informação. 






