# FL_info
Reune diversos links de sites/cursos/artigos/ferramentas/produtos sobre aprendizado federado relevantes para o projeto fl_project.

### DATASETS
* [VED -  Vehicular Energy Dataset](https://github.com/gsoh/VED). O VED captura trajetórias de GPS de veículos, juntamente com seus dados de séries temporais de combustível, energia, velocidade e consumo de energia auxiliar, e os dados foram coletados por meio de registradores OBD-II de bordo, de novembro de 2017 a novembro de 2018. A frota é composta por um total de 383 carros particulares (264 veículos a gasolina, 92 HEVs e 27 PHEVs/EVs) em Ann Arbor, Michigan, EUA.

  * Artigo: [Vehicle Energy Dataset (VED), A Large-scale Dataset for Vehicle Energy Consumption Research](https://doi.org/10.1109/TITS.2020.3035596)

* [Extended Vehicle Energy Dataset (eVED)](https://github.com/zhangsl2013/eVED). Versão estendida do VED, que é um conjunto de dados em larga escala para análise do consumo de energia de veículos. Comparado com sua versão original, o conjunto de dados VED estendido (eVED) é aprimorado com coordenadas GPS precisas de viagem do veículo, servindo como uma base confiável para associar os registros de viagem VED com informações externas, por exemplo, limite de velocidade da estrada e cruzamentos, de serviços de mapas acessíveis para acumular atributos que são relevantes e essenciais na análise do consumo de energia do veículo

### FRAMEWORKS/REPOS
* [Awesome Federated Machine Learning Public](https://github.com/innovation-cat/Awesome-Federated-Machine-Learning). Tudo sobre FL em videos, tutoriais, artigos, conferencias, códigos.
  
* [Awesome Healthcare Federated Learning](https://github.com/monk1337/Aweome-Heathcare-Federated-Learning?tab=readme-ov-file). Destaca alguns links de tutoriais, artigos e frameworks relevantes na área de FL, em especial para a area da saúde, mas que também se direciona para novas aplicações.
  
* [FATE-Uma estrutura de aprendizagem federada de nível industrial](https://github.com/FederatedAI/FATE). O FATE (Federated AI Technology Enabler) é o primeiro framework de código aberto para aprendizagem federada de nível industrial do mundo, que permite que empresas e instituições colaborem em dados, protegendo a segurança e a privacidade dos dados. Ele implementa protocolos de computação seguros baseados em criptografia homomórfica e computação multipartidária (MPC).
  
* [Flower - Uma estrutura de aprendizagem federada amigável](https://github.com/adap/flower). Flower ( flwr) é uma estrutura para a construção de sistemas de IA federados.
  
* [PySift](https://github.com/OpenMined/PySyft). Executar ciência de dados em dados que permanecem no servidor de outra pessoa.
  
* [Tensorflow Federado](https://github.com/google-parfait/tensorflow-federated). O TensorFlow Federated (TFF) é um framework de código aberto para aprendizado de máquina e outras computações em dados descentralizados. O TFF foi desenvolvido para facilitar a pesquisa e a experimentação abertas com Aprendizado Federado (FL) , uma abordagem de aprendizado de máquina em que um modelo global compartilhado é treinado por vários clientes participantes que mantêm seus dados de treinamento localmente. Por exemplo, o FL tem sido usado para treinar modelos de previsão para teclados móveis sem a necessidade de enviar dados confidenciais de digitação para servidores.
  
* [FEDn](https://www.scaleoutsystems.com/framework). O FEDn é uma plataforma de aprendizado federado pronta para produção que permite que organizações treinem modelos de ML de forma colaborativa, mantendo dados confidenciais seguros e locais. Seja explorando o aprendizado federado ou escalando implantações de produção, o FEDn integra-se perfeitamente aos seus fluxos de trabalho de ML existentes, com opções de implantação flexíveis e controles de segurança rigorosos.

### TUTORIAIS
* [Aprendizagem federada com o Google](https://federated.withgoogle.com/). Bastante importante para entender FL e ver o ínicio de tudo. É principal tutorial da área.
 

### História
O campo do Aprendizado Federado foi formalmente estabelecido e popularizado pelo artigo seminal "[Communication-Efficient Learning of Deep Networks from Decentralized Data](https://arxiv.org/abs/1602.05629)".  Publicado em 2017 por H. Brendan McMahan e uma equipe de pesquisadores, o trabalho delineou as bases conceituais e algorítmicas que definiriam a pesquisa e o desenvolvimento subsequentes. O artigo propôs o FL como uma abordagem para treinar modelos em redes de dispositivos móveis, deixando os dados de treinamento distribuídos e aprendendo um modelo compartilhado pela agregação iterativa de atualizações computadas localmente.

Em resposta às limitações do FedAvg em ambientes non-IID, foi proposto o Federated Proximal (FedProx). O artigo [Federated Optimization for Heterogeneous Networks](https://anitksahu.github.io/FedProx.pdf) de [Li et al., 2018](https://anitksahu.github.io/FedProx.pdf), introduziu o FedProx como uma generalização e uma re-parametrização do FedAvg, especificamente projetada para lidar com a heterogeneidade estatística e de sistema. O mecanismo central do FedProx é a adição de um termo de regularização proximal à função de perda de cada cliente. Esse termo, que geralmente utiliza a norma $L_2$, restringe o quão longe as atualizações do modelo local podem se desviar do modelo global atual. Matematicamente, a função objetivo local de um cliente $k$ é modificada para incluir a regularização, minimizando:

$$ \min_w \; f_k(w) + \frac{\mu}{2} \lVert w - w_t \rVert^2 $$

onde $f_k(w)$ é a função de perda local, $w_t$ é o modelo global da rodada $t$, e $\mu$ é o parâmetro de regularização. Esse termo de penalidade garante que as atualizações locais permaneçam "próximas" do modelo global, controlando o "client drift" e melhorando a robustez e a estabilidade da convergência em redes com dados heterogêneos. Em um estudo comparativo, o FedProx demonstrou uma precisão superior de 86.5% e convergiu em 85 rodadas, superando o FedAvg e oferecendo um equilíbrio eficaz entre desempenho e estabilidade.
