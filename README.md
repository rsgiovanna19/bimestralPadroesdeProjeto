                                   -------------Bimestral Padrões de projeto-------------
                                    -------------Giovanna Rosa - 35874716 -------------

------------- Questão 01 -------------

**Design Pattern escolhido**: Strategy
**Justificativa**: O design pattern Strategy tem como objetivo definir uma interface com todos os pré requisitos que todas as que a derivarem da mesma, adicionando novos métodos dentro das classes que derivam a interface. Neste caso, um dos pré requisitos era a fácil e extendida troca de algoritmos de cálculos de risco em tempo de execução. Sem alterar, mas sim extender o código. 
**Como é aplicado na questão?** O cliente decide qual implementação vai utilizar, sem ao menos se preocupar como ela funciona, definido na interface 'AlgoritmoRisco', pois não é necessário. Neste caso, o cliente é a classe 'CalculadoraRisco'. 

------------- Questão 02 -------------

**Design Pattern escolhido**: Adapter
**Justificativa**: O adapter tem como função adaptar duas interfaces incompatíveis, sendo condizente com o SOLID, em não alterar o codigo ja existente, mas sim estendê-lo. 
**Como é aplicado na questão?**: Neste caso, utilizamos a interface 'ProcessadorTransacoes' com a 'processarTransacao(HashMap)'. Contudo, como elas sao incompatíveis entre si, o adapter foi adicionado: A classe 'AdaptadorProcessadorTransacoes converte chamadas e respostas entre os dois formatos.

------------- Questão 03 -------------

**Design Pattern escolhido**: State
**Justificativa**: O design pattern State permite que o comportamento de algum objeto seja alterado quando seu estado também é alterado, parecendo que "muda de classe"... Ao inves de utilizarmos If/Else/Switch, tomamos a decisão do que realizar\fazer a partir de uma variável de estado. 
**Como é aplicado na questão?**: O Padrão State é aplicado para modelar a Máquina de Estado Finito da usina, o ControleUsina atua como o Contexto principal, entregando o comportamento para o estado atual e controlando as transições. Cada estado concreto (como EstadoAlertaAmarelo) encapsula sua própria lógica, definindo o comportamento da usina e determinando quando e para qual próximo estado deve ocorrer a transição, com base nas leituras de sensores cruciais (temperatura, falha de resfriamento e tempo). Esse mecanismo garante que todas as regras e limites operacionais sejam rigorosamente respeitados durante a transição

------------- Questão 04 -------------

**Design Pattern escolhido**: Chain of Responsibility
**Justificativa**: O padrão Chain of Responsibility foi escolhido por ser ideal para organizar e gerenciar uma sequência de validações interdependentes e condicionais de forma desacoplada.
**Como é aplicado na questão?**: O Padrão Chain of Responsibility é aplicado na validação da NF-e ao criar uma cadeia sequencial de Validadores (Handlers), onde o documento fiscal é a requisição. Essa estrutura organiza etapas de verificação (Schema XML, Certificado, etc.) de forma modular e com baixo acoplamento. A principal função é permitir validações condicionais e incorporar mecanismos complexos de controle de fluxo, como o circuit breaker (interrupção após múltiplas falhas), o rollback automático em caso de erro, e o gerenciamento de timeout individual para serviços externos, resultando em uma lógica de validação robusta e flexível.