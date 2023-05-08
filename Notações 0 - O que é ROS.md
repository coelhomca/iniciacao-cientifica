- O que é ROS?

  - *Robot Operating System*

  - É um meta sistema operacional. Tem funcionalidades, como:

    - Abstração de hasrdaware (abstração=ignorar detalhes; só trabalha com tarefas de alto nível de abstração; algoritmos que não trabalha direto com o mundo físico);
    - Comunicação entre processos (vários processos rodando e se omunicando entre si);
    - Bibliotecas de funções comumente usadas (controle de atuadores, servomotores).s

  - É um framework para desenvolvimento, reuso e compartilhamento de software em contexto de robótica.

    - Um framework é um conjunto de bibliotecas e estruturas padronizadas ("investir tempo na forma, só no conteúdo").
    - Com ROS, o código de diferentes robôs segue a mesma estrrutura e é possível reutilizar bibliotecas em diferentes projetos.
    - Quem desenvolve o projeto investe mais seu tempo com o seu robô (agregando valor e vencendo os desafios das suas tarefas) do que "inventando a roda".

  - Dentro do ecossistema ROS, temos a biblioteca de controle e trajetória *Movelt*.

  - Ferramentas do ecossistema ROS (para saber os dados estão chegando no robô):

    - Gazebo - Transformação de sistemas de cordenadas.
    - Rviz - Visualização de dados 3D.
    - PlotJuggler - Temperatura, velocidade, ...

  - A estrutura do ROS

    - Como construir um software reutilizável?

      - Modularidade
      - Um projeto ROS é dividido em diversos processos quase independentes.
      - Cada processo possui uma tarefa específica, com entradas e saídas definidas.
      - Dessa forma, quando for necessário resolver o mesmo problema já existirá um módulo/pedaço de código que vai resolver este problema.

    - A unidade mínima de um projeto ROS é um node (=o módulo descrito anteriormente).

    - Os nodes se comunicam por meio de tópicos.

    - Ou seja, a ideia do ROS é construir um projeto descentralizado (vários processos acontecendo em paralelo) e o fluxo de dados/informação entre cada processo é feito por meio de tópicos (por exemplo, leitura de informações dos sensores).

    - Estrutura usual de uma aplicação ROS:

      1. Aquisição de dados (por meio de um conjunto de sensores)
      2. Processamento 
      3. Ações de controle

    - Ex:

      - (em vermelho) Nós de aquisição de dados (sensores de distância=quanto a roda girou,medida do acelerometro, câmera)

      - (em amarelo) Nós de processamento de dados (fusão de sensores para melhorar a qualidade e ter uma estimativa da localização e rede neural reconhecimento de imagem ponto de interesse está proximo ou onde está); (seta amarela) lógica de negocio, algoritmos de alto nível de abstração, máquina de estados, algoritmos de controle;

      - (em azul) Nós de ação de controle - node que manda os comandos para motores de trassão e server, esquerda e direita.

        ![image-20230508105350497](/home/mariaclara/.config/Typora/typora-user-images/image-20230508105350497.png)

- Referências:

Documentação ROS Humble: https://docs.ros.org/en/humble/Tutorials/Intermediate/Composition.html#run-time-composition-using-ros-services-with-a-publisher-and-subscriber

Wiki ROS: https://docs.ros.org/en/humble/Tutorials/Intermediate/Composition.html#run-time-composition-using-ros-services-with-a-publisher-and-subscriber

Material de aula da turma PMR3100 USP: https://edisciplinas.usp.br/course/view.php?id=84236