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

