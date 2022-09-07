# Mini2dGameEngine

Uma mini *Game Engine* 2d, o principal intuito foi aprender mais sobre [ECS](https://en.wikipedia.org/wiki/Entity_component_system), colisões, computação gráfica etc.

Um dos grandes focos é a otimização do código, fazendo algo sem muitas funcionalidades que ficarão sem ser utilizadas.

## Entity component system (ECS)
* ECS foi a arquitetura escolhida para sistema de gerenciamento de dados dessa *engine*;
* Todas as **entidades** e **componentes** herdam as seguintes função:
  * ```beforePlay()```: Executa antes do inicio do programa;
  * ```beginPlay()```: Executa no inicio do programa;
  * ```process()```: Executa todo *frame*, essa função fica responsavel pelo *update*, física, colisão etc;
  * ```endPlay()```: Executa ao fim go programa.
* Todos os dados são divididos nessas 3 opções:
  * ### **Entidades**
    * São todos os objetos da aplicação, qualquer instância é criada como uma entidade, todas as entidades herdam da classe ```EntityMaster```;
    * A classe ```EntityHanddler``` é o responsavel por todas as manipulações dentro do programa, por exemplo, se uma entidade quer alterar outra essa deverá enviar uma mensagem ao ```EntityHanddler``` para que esse realize a operação;
    
  * ### **Componentes**

  * ### **Sistemas**


## Colisão
* A escolha, até o momento, foi uma implementação que não encontrei muito sobre, porem pode ser vista [nesse video](https://www.youtube.com/watch?v=7Ik2vowGcU0&t=1282s&ab_channel=javidx9);
* De forma simplificada ela gera segmentos de linha do centro do objeto até os vértices do colisor, a colisão é detectada no momento que uma dessas linhas intersecta o colisor de um outro objeto;
  ![Captura de tela 2022-09-07 202711](https://user-images.githubusercontent.com/107453198/189002399-0a78e72a-e488-4d3a-ac5f-e72611f6c815.jpg)

* Também foi implementada a colisão de pontos, permitindo maior performance para objetos pequenos como projeteis por exemplo.

