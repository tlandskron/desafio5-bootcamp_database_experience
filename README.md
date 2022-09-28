Desafio
Neste desafio, você terá a missão de compreender o papel dos Bancos de Dados Relacionais (SQL) e Não Relacionais (NoSQL) no contexto de um Engenheiro de Dados. Para isso, anote todos os conceitos, definições e insights que julgar relevantes em um novo repositório Git, aumentando assim seu portfolio de conhecimentos.

Super Dica: Organize tudo em seu README.md, é uma alternativa bem rápida e efetiva, pois, o GitHub provê uma interface bem simples e intuitiva para isso. Além de ampliar seu portifólio de projetos no GitHub!

Pré-requisitos:

Conhecimento Avançados(SQL, NoSQL);

Computador com SO de sua preferência(Windows, Linux, Mac OS);

Agora é a sua vez de ser o Protagonista! 🤩

Bons estudos!



Um Engenheiro de Dados transforma dados em um formato útil para análise. Imagine que você é um Engenheiro de Dados que irá trabalhar em um concorrente do Uber. Seus usuários têm um aplicativo através do qual eles acessam seu serviço. Eles pedem uma corrida para um destino através do aplicativo, que é encaminhado para um motorista, que os busca e os leva para onde foi solicitado. Após a corrida, eles são cobrados e têm a opção de avaliar como o motorista dirigiu.

Para manter um serviço como este, você precisa:

Um aplicativo para dispositivos móveis, para usuários.
Um aplicativo para dispositivos móveis, para motoristas.
Um servidor que pode passar pedidos de usuários para motoristas e lidar com outros detalhes, como atualizar informações de pagamento.
Aqui está um diagrama que ilustra esta comunicação:

Pipeline

Como você pode imaginar, esse tipo de sistema vai gerar enormes quantidades de dados. Você terá diferentes tipos de dados para serem armazenados:

O banco de dados do seu aplicativo principal. Ele deve conter informações sobre o usuário e o motorista.
Logs de análise de servidor:
Registros de acesso ao servidor. Estes contêm uma linha por solicitação feita ao servidor a partir do aplicativo.
Logs de erro do servidor. Estes contêm todos os erros do lado do servidor os quais foram gerados pelo seu aplicativo.
Registros de análise de aplicativos:
Registros de eventos da aplicação. Estes contêm informações sobre as ações que os usuários e os motoristas receberam no aplicativo. Por exemplo, você estava logado quando clicou em um botão ou atualizou suas informações de pagamento.
Logs de erro da aplicação. Estes contêm informações sobre erros no aplicativo.
Registros de corridas. Estes contêm informações sobre cada corrida para os usuários / motoristas e contêm informações sobre o status da corrida.
Registros de Serviços ao Cliente. Estes contêm informações sobre interações com clientes por agentes de atendimento ao cliente. Podem incluir transcrições de voz e registros de e-mail.
Digamos que um Cientista de Dados quer analisar o histórico de ação de um usuário com seu serviço e ver quais ações se correlacionam com os usuários que gastam mais. Para isso, será necessário combinar informações dos logs de acesso do servidor e dos logs de eventos do aplicativo. Será necessário:

Reunir regularmente logs de análise de aplicativos de dispositivos do usuário.
Combinar os logs da análise do aplicativo com todas as entradas de log do servidor que fazem referência ao usuário.
Criar uma API que retorna o histórico de eventos de qualquer usuário.
Para resolver isso, você precisará criar um pipeline que possa registrar o uso dos aplicativos móveis e logs do servidor em tempo real, analisá-los e anexá-los a um usuário específico. Em seguida, você precisará armazenar os registros analisados ​​em um banco de dados, para que possam ser facilmente consultados pela API. Você precisará configurar vários servidores em modo de balanceamento de carga para processar os logs recebidos.

A maioria dos problemas que você vai encontrar serão relativos à confiabilidade dos sistemas distribuídos. Por exemplo, se você tiver milhões de dispositivos para reunir logs e demanda variável (de manhã, você recebe uma tonelada de logs, e quase nenhum à meia-noite), você precisará de um sistema que possa escalar automaticamente a contagem de servidores para cima e para baixo.

Neste momento entra em cena a necessidade de ter um ambiente em nuvem, robusto e seguro, que possa processar esse grande volume de dados. Uma estrutura em nuvem, usando um provedor como a AWS (Amazon Web Services), pode ser a melhor alternativa custo/benefício. Os servidores são registrados com um balanceador de carga, e o balanceador de carga envia tráfego para eles com base em como eles estão ocupados. Isso significa que os servidores podem ser adicionados ou removidos conforme necessário.

Computação em Nuvem

Aproximadamente, as operações em um pipeline de dados consistem nas seguintes fases:

Entrada – isso envolve a coleta de dados necessários.
Processamento – isso envolve o processamento dos dados para obter os resultados finais desejados.
Armazenamento – isso envolve armazenar os resultados finais para recuperação rápida.
Acesso – você precisará habilitar uma ferramenta ou usuário para acessar os resultados finais do pipeline.
Para um exemplo mais complexo, imagine que um Cientista de Dados quer construir um sistema que encontre todos os serviços/corridas que terminaram prematuramente devido a problemas do aplicativo ou do motorista. Uma maneira de fazer isso é olhar para o banco de dados do serviço ao cliente para ver quais corridas terminaram com problemas e analisar o cruzar o login do usuário com os dados sobre o serviço/corrida.

Antes que o Cientista dos Dados possa fazer isso, ele precisa de uma maneira de combinar os logs no banco de dados de serviço ao cliente com serviços/corridas específicos. O Engenheiro de Dados, deve criar uma API que permita ao Cientista de Dados consultar todas as mensagens de serviço ao cliente relacionadas a uma determinada corrida. Para fazer isso, serás necessário:

Criar um sistema que extraia dados do banco de dados e descubra informações sobre a corrida, como por exemplo, quanto tempo e se o destino correspondia à solicitação inicial do usuário.
Combinar as estatísticas calculadas em cada corrida com informações do usuário, como nome e identificação do usuário.
Extrair informações de erro dos logs de análise do aplicativo e do servidor pertencentes ao usuário durante o período de tempo da corrida.
Encontrar todas as consultas de atendimento ao cliente por um usuário.
Criar alguma heurística para combinar corridas com consultas de atendimento ao cliente.
Armazenar os valores conforme necessário para garantir que a API seja executada rapidamente, mesmo para futuras corridas.
Criar uma API que retorne todas as mensagens de serviço ao cliente relacionadas a uma corrida particular.
Um Engenheiro de Dados qualificado será capaz de construir um pipeline que execute cada uma das etapas acima sempre que uma nova viagem seja adicionada. Isso garantirá que os dados atendidos pela API estejam sempre atualizados e que qualquer análise que o Cientista de Dados faça será válida. 

Habilidades do Engenheiro de Dados
Um Engenheiro de Dados precisa ser bom em:

Arquitetar sistemas distribuídos
Criar pipelines confiáveis
Combinar fontes de dados
Criar a arquitetura de soluções
Colaborar com a equipe de Data Science e construir as soluções certas para essas equipes
Observe que não mencionamos nenhuma ferramenta. Embora ferramentas como Hadoop e Spark e linguagens como Scala e Python sejam muito importantes para o Engenheiro de Dados, é importante também entender bem os conceitos e saber como construir sistemas do mundo real, além de habilidade em Cloud Computing.

Embora os Engenheiros de Dados precisem ter as habilidades listadas acima, o dia a dia de um Engenheiro de Dados irá variar dependendo do tipo de empresa para a qual trabalham. Em geral, você pode classificar os Engenheiros de Dados em algumas dessas categorias:

Generalista
Um Engenheiro de Dados generalista normalmente trabalha em uma equipe pequena. Sem um Engenheiro de Dados, Cientistas e Analistas de Dados não têm nada a analisar, tornando oEngenheiro de Dados um primeiro membro crítico de uma equipe de Data Science.

Quando um Engenheiro de Dados é a única pessoa focada em dados em uma empresa, eles geralmente acabam tendo de fazer mais trabalho de ponta a ponta. Por exemplo, um Engenheiro de Dados generalista pode ter que fazer tudo desde analisar a entrada dos dados até processá-los para fazer a análise final. Isso requer mais habilidade em Data Science do que a maioria dos Engenheiros de Dados. No entanto, também requer menos conhecimento de arquitetura de sistemas – pequenas equipes e empresas não têm uma tonelada de usuários, então a engenharia para escala não é tão importante. Este é um bom papel para um Cientista de Dados que deseja migrar para a Engenharia de Dados.

Centrado no Pipeline
Os Engenheiros de Dados centrados em pipeline tendem a ser necessários em empresas de médio porte que possuem necessidades complexas de Ciência de Dados. Um Engenheiro de Dados centrado em pipeline trabalhará com equipes de Cientistas de Dados para transformar dados em um formato útil para análise. Isso implica um conhecimento aprofundado de sistemas distribuídos e ciência da computação.

Baseado em Banco de Dados
Um Engenheiro de Dados centrado no banco de dados é focado em configurar e preencher bancos de dados analíticos. Isso envolve algum trabalho com pipelines, trabalho com bases de dados de ajuste para análise rápida e criação de esquemas de tabelas. Envolve também o trabalho com ETL para obter dados em Data Warehouses. Este tipo de Engenheiro de Dados geralmente é encontrado em empresas maiores com muitos Analistas de Dados que têm seus dados distribuídos em vários bancos de dados.

Quer se Tornar um Engenheiro de Dados?
Neste artigo, nós definimos o que é Engenharia de Dados e quais as habilidades necessárias para praticá-la em um alto nível. Se você está interessado em arquitetar sistemas de grande escala, ou trabalhar com enormes quantidades de dados, a Engenharia de Dados é um excelente campo de trabalho para você.

Pode ser muito interessante ver seu pipeline de dados de autoscaling lidar com um pico de tráfego ou começar a trabalhar com máquinas que possuem terabytes de RAM. Há uma satisfação enorme na construção de um sistema robusto que pode funcionar por meses ou anos com ajustes mínimos. A Engenharia de Dados lida com escala e eficiência, e pode ser difícil encontrar material de boas práticas por conta própria. Mas não desista – é possível aprender Engenharia de Dados aqui na DSA com a Formação Engenheiro de Dados. Clique no link abaixo e comece agora mesmo:

Formação Engenheiro de Dados
Equipe DSA

Referências:

The Rise of the Data Engineer - https://medium.freecodecamp.org/the-rise-of-the-data-engineer-91be18f1e603

Google Certified Professional – Data Engineer - https://cloud.google.com/certification/data-engineer

Data Scientist vs. Data Engineer: Here’s How the Difference Matters - https://www.linkedin.com/pulse/data-scientist-vs-engineer-heres-how-difference-matters-ripal-vyas/

What is Data Engineering? - https://www.dataquest.io/blog/what-is-a-data-engineer/

Data Scientists vs. Data Engineers - http://www.datasciencecentral.com/profiles/blogs/data-scientists-vs-data-engineers

fonte: https://blog.dsacademy.com.br/o-que-faz-um-engenheiro-de-dados/