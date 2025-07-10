# resumo-do-lab-azure
Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab na DIO, enquanto feito bootcamp sobre Computação em Nuvem.

## Primeiros Avisos
Há algumas ferramentas na Azure com um aviso chamado Versão Prévia, quando houver esse aviso, não necessariamente a funcionalidade continuará no sistema da Azure.
Tudo o que for feito dentro da função será perdido, já que são apenas testes do sistema, não tendo garantia da continuidade.

## Primeiras Aulas (Base de Computação em Nuvem)
IaaS - Infraestrutura as a Service
Máquina para exercer função de servidor, mas que não precisa dele físico, sendo então utilizado como um serviço (pago, mensalmente/anualmente) para hospedar o serviço que queira vender. Não tem tanto o custo do servidor local. (As a Service, pagar pelo uso)

Em ambiente local (on-premise), máquina tem vários custos, desde o espaço físico, já que tem a quantidade de máquinas para poder processar as funções, além de custos de manutenção e até mesmo aquisição da máquina física. Aumenta o custo conforme a quantidade de máquinas. Refrigeração é necessária. Necessário, então o custo da infraestrutura.
Networking (cabeamento ou internet)

Híbrido, tem máquinas locais e máquinas em nuvem, para manter custos apenas das máquinas locais, alugando temporariamente (pequenos períodos, sazonais) máquinas em nuvem, encerrando o serviço pelo uso dessas máquinas. Então, é usado tanto físico quanto Cloud.

Plataformas - empresas que se focam em emprestar (vender) os serviços de máquinas cloud. (AWS, Azure, Oracle, GCP (Google))
As plataformas podem ter máquinas em lugares diferentes do mundo, rodando os serviços, em Data Centers. Otimizando e melhorando o uso e latência do serviço, conforme o local do serviço que irá utilizar.
A região pode, também, ser dividida em zonas dentro dela, para facilitar mais.

Nuvem Privada - DataCenter própria da empresa, sendo responsável por operar os serviços que fornecem. Não fornece acesso a usuários de fora da organização.

Nuvem Pública - Pertencente a serviços de nuvem ou provedor de Hosting. Fornece recursos e serviços a várias organizações/usuários.

CapEx/OpEx

CapEx - despesas de capital; gasto inicial em infraestrutura física, que pode se reduzir com o tempo
OpEx - despesas operacionais; gastos com produtos e serviços conforme necessidade, pagando conforme o uso

IaaS - infraestrutura como serviço, infraestrutura de TI, servidor, armazenamento, redes (necessita configuração própria para o negócio por parte do cliente);
PaaS - plataforma como serviço, fornecer ambiente para criação, teste e implementação de aplicativos de software, sem foco no gerenciamento da infraestrutura;
SaaS - software como serviço, usuário se conecta ao aplicativo através da internet;

Regions - compostas por um ou mais DataCenters próximos, fornecem flexibilidade e escala para reduzir a latência do cliente;

Serviços de Computação do Azure - recursos de computação como discos, processadores, memória, rede e sistemas operacionais;
Máquinas Virtuais; Serviços/Aplicativos; Contêineres; Serviços de Kubernetes do Azure (AKS); Área de Trabalho Virtual;

Instâncias de Contêiner - oferta de PaaS que executa um contêiner ou pod de contêineres
Aplicativos de Contêiner - oferta de PaaS, como instâncias de contêineres que pode balancear a carga e escalar
Serviço de Kubernetes - serviço de orquestração de contêineres com arquiteturas distribuídas e grandes volumes de contêineres

Functions - oferta de PaaS que dá suporte a operações de computação sem servidor. Baseado em eventos, é executado quando chamado, sem exigir infraestrutura de servidor enquanto inativos.

Armazenamento
LRS (armazenamento com redundância local) - DataCenter individual na região primária - criou a conta em uma região - Durabilidade de 11 noves
ZRS (armazenamento com redundância de zona) - três zonas, cópias diferentes, de disponibilidade na região primária - Durabilidade de 12 noves
GRS (armazenamento com redundância geográfica) - três cópias em uma zona e região principal e três na região secundária - Durabilidade de 16 noves
GZRS (armazenamento com redundância de zona geográfica) - três zonas de disponibilidade na região primária e um único DataCenter na região secundária - Durabilidade de 16 noves

Serviços de Armazenamento - Blob (quantidades massivas de dados); Disco (fornece discos para máquinas virtuais, aplicativos e outros serviços acessarem); Fila (serviço de armazenamento de mensagens que fornece armazenamento e recuperação para grandes quantidade de mensagens, cada uma com até 64KB); Arquivos (configura compartilhamento de arquivos de rede altamente disponível); Tabelas (fornece opção de chave/atributo para armazenamento de dados estruturados não-relacionais com design sem esquema)

## Benefícios da Nuvem
* Alta Disponibilidade - recursos disponíveis o máximo de tempo possível, mas que pode sofrer interrupções. Geralmente, há um ressarcimento, crédito para o produto, caso haja interrupções.
* Escalabilidade - capacidade de ajustar recursos para atender à demanda, seja crescendo ou diminuindo.
* Elasticidade
* Confiabilidade - sistema que se recupera de falhas e que continue funcionando. Pondo o sistema e demais regiões, quando ocorrer algum evento com o seu sistema, consiga recuperar o funcionamento.
* Previsibilidade - avanço no sistema com a confiança de segurança.
* Segurança - prevenção de ataques.
* Governança - estabelecer modelos de regras.
* Gerenciabilidade - facilitar a utilização e gerenciamento de recursos dos usuários com base em sua necessidade.

## SLAs (Service Level Agreement)
Acordo de Nível de Serviço é um contrato entre um prestador de serviços e um cliente, que define detalhes do serviço a ser fornecido. Esses detalhes incluem o nível de desempenho esperado, as metodologias de medições de desempenho e o que acontecerá se os níveis de desempenho não forem atingidos. Geralmente, há um ressarcimento por parte do fornecedor do serviço.
Uma dica a ser visto é a quantidade de 9's que o contrato terá para entender o menor tempo de indisponibilidade do serviço.
A redundância de armazenamento pode ajudar a ter menos tempo de indisponibilidade do serviço também, já que é criado cópias.

# Microsoft Learn
A computação em nuvem é a entrega de serviços de computação pela Internet. Os serviços de computação incluem infraestrutura de TI comum, como máquinas virtuais, armazenamento, bancos de dados e rede. Também pode se expandir para IoT (Internet das Coisas), ML (machine learning) e IA (inteligência artificial).

## Cenários (modelo de responsabilidade compartilhada)
Cenários comuns para IaaS:

* Migração lift-and-shift: configurando recursos para nuvem semelhante ao datacenter local, apenas migrando de execução local para infraestrutura IaaS.
* Teste e desenvolvimento: configurações para ambientes de desenvolvimento e teste que precisa replicar rapidamente. Você pode inicializar ou desativar os diferentes ambientes rapidamente com uma estrutura de IaaS, mantendo o controle completo.

Cenários para PaaS:

* Estrutura de desenvolvimento: usar como base para desenvolver ou personalizar aplicativos baseados em nuvem. São incluídos recursos de nuvem, como escalabilidade, alta disponibilidade e a funcionalidade de multilocatário, reduzindo a quantidade de codificação que os desenvolvedores precisam realizar.
* Análise ou business intelligence: permitem que as organizações analisem e minerem dados, encontrando insights e padrões e prevendo resultados para aprimorar a previsão, as decisões de design de produto, o retornos sobre investimentos e outras decisões de negócios.

# IAs
## IAs Generativas
Sistemas capazes de criar, aprimorar e adaptar conteúdos de forma autônoma que se assemelha a qualidade humana.

## Prompts
- Instrução
- Exemplos (Few-shot Learning) -> exemplo de estrutura de resposta para instrução pedida à IA. Modelo de retorno para IA seguir.
- Contexto/Configuração -> cenário, contexto em que a IA pode atuar. "Imagine que..."
- Restrições/Limitações -> limitar a resposta, escopo, em termos de extensão ou o que será retornado. "Responda em até ... palavras sobre..."
- Conteúdo principal -> dado relevante, necessário, para o processamento da instrução dada. Pode ser um dado, tabelas, parágrafos, etc., que deve ser analisado/traduzido.
- Indicações -> são especificações para guiar as respostas para saídas específicas.
- Formato de Saída -> define como o modelo deve estruturar as respostas em termos de formato/estilo. "Retorne em tópicos..."; "Retorne como parágrafo..."
- Conteúdo de Suporte -> dar contexto e informações para que o modelo adapte sua resposta para diferentes cenários.

## Técnicas de Engenharia de Prompt
- Instrução Clara -> Técnica que organiza a instrução para serem objetivas e detalhadas, evitando ambiguidades e confusões.
- Repetir instruções no final -> Deixando claro o que a IA deve retornar. Podendo garantir uma resposta completa.
- Guardrails -> Técnica para limitar as respostas para coisas mais relevantes e práticas. Evitando informações inúteis.
- Preparando Saída -> Indicar como o usuário deseja como que entregue a resposta. Indicando também um exemplo para que ele siga.
- Solicitação de Cadeia de Pensamento -> Instrução para a IA responder passo a passo a explicação antes de chegar a sua conclusão.
- Especificar Estrutura de Saída -> Definir do formato exato da saída/resposta.
- Dividir a Tarefa -> Quebre problemas grandes para etapas menores para fácil resolução por parte do modelo.
- Adicionar Sintaxe Clara
