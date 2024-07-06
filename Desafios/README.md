# Modelo Relacional

# Etapa 1 elaboração das tabelas:

1. **Criação das tabelas**: Iniciei o processo analisando os possíveis fatos, dimensões e métricas.
   
3. **Organização de tabelas**: Cheguei à conclusão de que o correto é dividir a tabela a partir dos seguintes elementos: o objeto "carro", os indivíduos associados diretamente à ação principal da tabela, que são os clientes e os vendedores, e a ação principal, que é locar carros.


4. **Nome das tabelas**: Tabela "cliente" refere-se aos dados dos clientes, tabela "locacao" refere-se às ações de locar os carros, tabela "vendedor" refere-se às informações dos vendedores, e por último, a tabela "carro" trata de informações relacionadas aos carros da locadora.

# Etapa 2 normalização:

1. **Normalização 1**: Na normalização para a primeira forma normal (1NF), assegurei que cada coluna da tabela contenha apenas valores atômicos, ou seja, valores indivisíveis. Além disso, garanti que não existam grupos repetidos de colunas na tabela. Cada linha na tabela é única, atendendo assim aos requisitos da 1NF.

2. **Normalização 2**: Após a normalização para a segunda forma normal (2NF) em todas as tabelas, gerei as tabelas "cidade", "estado" e "país", referentes à tabela principal "cliente". Além disso, a tabela "estado" também tem relacionamento com a tabela "vendedor". 
Na modelagem de dados, os fatos representam as ocorrências ou eventos registrados, enquanto as dimensões fornecem contexto a esses fatos, como localização, tempo ou categoria. As métricas, por sua vez, são medidas quantitativas derivadas dos fatos para análise e avaliação. Com base nesses conceitos, adicionei as cardinalidades e relacionamentos à base de dados, garantindo uma estrutura coesa e significativa para o modelo.

3. **Normalização 3**: Efetuei a normalização para a terceira forma normal (3NF) da tabela "carro", utilizando a tabela "chassi" para armazenar o número do chassi e outra tabela chamada de "combustível". Três motivos para fazer isso são:

- Redução da redundância: Ao separar o número do chassi em uma tabela dedicada, evitamos a repetição desse dado em múltiplas linhas da tabela de carros, reduzindo a redundância e economizando espaço de armazenamento.
- Manutenção mais fácil: Com as informações normalizadas, é mais fácil atualizar os dados do número do chassi ou do tipo de combustível, pois precisamos fazer alterações em apenas uma tabela, em vez de várias.
- Integridade dos dados: A normalização reduz a chance de inconsistências e erros nos dados, garantindo maior integridade e confiabilidade nas informações armazenadas.

# Modelo Dimensional:

1. **Analise dos fatos, dimensões e métrica**: Ao analisar a tabela "locação", examinei-a sob a perspectiva dos fatos, métricas e dimensões, essenciais para a criação do modelo dimensional. Os fatos, representando eventos ou ocorrências, foram identificados como as locações de carros. As métricas, medidas quantificáveis derivadas dos fatos, incluíram informações como custo da locação e duração. Já as dimensões, fornecendo contexto aos fatos, compreenderam atributos como cliente, veículo e data da locação. Essa abordagem permitiu uma estruturação eficaz do modelo dimensional, capacitando análises detalhadas e insights significativos sobre as operações de locação.

2. **Analise dos fatos, dimensões e métrica**: Ao revisar a tabela, focalizei as informações essenciais associadas à locação de veículos, estruturando-as no fato principal. Posteriormente, procedi à criação de tabelas de dimensões distintas, destinadas a aspectos específicos da operação de locação. Estas incluíram uma tabela para informações temporais, abrangendo datas relevantes às locações, uma tabela para detalhes dos clientes envolvidos nas transações, outra para os vendedores responsáveis e uma última para os próprios veículos locados, cada qual representando uma dimensão crucial no contexto do modelo dimensional. Essa metodologia proporcionou uma organização sistemática dos dados, promovendo uma análise detalhada e fornecendo uma visão abrangente das operações de locação de veículos.

# Banco de dados com as views organizado no SQLITE

1. **Banco de Dados**: Ao transferir a base de dados do modelo relacional para o SQLite, mantive a fidelidade dos dados, garantindo uma transição sem perdas. Utilizei comandos específicos para essa tarefa, começando pela criação das tabelas no SQLite, replicando a estrutura do modelo relacional. Em seguida, inseri os dados existentes na base relacional para as respectivas tabelas SQLite, preservando a integridade e consistência dos registros. Durante o processo, ajustei eventuais diferenças de sintaxe entre os sistemas de gerenciamento de banco de dados. Após a importação, verifiquei a precisão dos dados transferidos, realizando testes e consultas para confirmar a correta migração. Concluí o procedimento com sucesso, assegurando que todas as informações originalmente presentes no modelo relacional estejam agora disponíveis de forma íntegra e acessível no SQLite, pronto para ser utilizado com eficiência.

2. **Views**: Criei views distintas para abordar cada aspecto do fato e das dimensões presentes na base de dados. Essas views foram projetadas para fornecer uma visão específica e detalhada de cada elemento, facilitando análises e consultas direcionadas. Ao criar uma view para cada ponto do fato e das dimensões, consegui organizar os dados de forma clara e acessível, permitindo uma compreensão mais aprofundada do conjunto de informações. Essa abordagem modular proporcionou uma maneira eficaz de explorar e extrair insights significativos da base de dados, de acordo com as necessidades específicas de análise.
