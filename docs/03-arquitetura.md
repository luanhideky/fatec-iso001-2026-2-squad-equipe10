# Arquitetura da Solução

## Visão Geral

A arquitetura proposta para o projeto de Monitoramento IoT Industrial da Equipe 10 foi pensada para permitir a coleta contínua de dados provenientes de sensores instalados em equipamentos ou processos industriais.

Os dados coletados serão enviados por meio da rede para um Gateway IoT, responsável por encaminhar as informações para os serviços da solução.

A partir desse ponto, os dados poderão ser processados, armazenados e disponibilizados para consulta em uma aplicação de monitoramento.

Quando forem identificadas condições anormais, a solução poderá gerar alertas para auxiliar a equipe responsável pela operação.

A arquitetura apresentada nesta etapa é inicial e poderá evoluir durante as próximas Sprints.

## Fluxo Geral da Solução

Sensores IoT  
↓  
Gateway IoT  
↓  
Serviço de Coleta / API  
↓  
Processamento dos Dados  
↓  
Banco de Dados  
↓  
Aplicação de Monitoramento / Dashboard

O serviço de processamento também poderá encaminhar informações para o serviço de alertas quando uma condição anormal for identificada.

## Componentes

### Sensores IoT

Responsáveis pela coleta de informações dos equipamentos ou processos industriais.

Os sensores representam os principais dispositivos de Entrada e Saída (E/S) da solução.

### Gateway IoT

Responsável por receber os dados enviados pelos sensores e encaminhá-los para os serviços de processamento da solução.

O Gateway também funciona como ponto intermediário entre os dispositivos IoT e a rede utilizada pela aplicação.

### Rede de Comunicação

Responsável pela comunicação entre sensores, Gateway IoT e os serviços da solução.

Falhas ou indisponibilidades na rede podem interromper temporariamente o envio dos dados.

### Serviço de Coleta de Dados

Responsável por receber as informações encaminhadas pelo Gateway IoT.

Esse serviço deverá permanecer em execução para garantir a continuidade da coleta dos dados.

### Serviço de Processamento

Responsável por analisar e tratar as informações recebidas antes do armazenamento ou geração de alertas.

### API

Responsável por permitir a comunicação entre os diferentes componentes da solução e a aplicação de monitoramento.

### Banco de Dados

Responsável pelo armazenamento das medições, informações dos sensores, eventos e alertas registrados.

### Aplicação de Monitoramento

Responsável por disponibilizar as informações para operadores, gestores e outros usuários autorizados.

### Dashboard

Responsável pela apresentação das principais informações coletadas pelos sensores e pelo estado dos equipamentos monitorados.

### Serviço de Alertas

Responsável por gerar alertas quando forem identificadas condições consideradas anormais.

### Logs e Monitoramento

Responsáveis pelo registro e acompanhamento do funcionamento dos principais serviços da solução.

## Processos e Serviços

A solução poderá possuir diferentes processos ou serviços executados simultaneamente, entre eles:

- Serviço de coleta de dados
- Serviço de processamento
- API
- Serviço de alertas
- Banco de dados
- Aplicação de monitoramento
- Serviços de logs e monitoramento

Esses componentes deverão ser acompanhados para identificar falhas, consumo excessivo de recursos ou interrupções.

## Armazenamento

O banco de dados será responsável por armazenar informações como:

- Sensores cadastrados
- Equipamentos monitorados
- Medições
- Eventos
- Alertas
- Histórico das informações

Os logs da aplicação também deverão possuir uma estratégia adequada de armazenamento.

## Comunicação entre Componentes

A comunicação principal ocorrerá entre:

- Sensores e Gateway IoT
- Gateway IoT e serviço de coleta
- Serviço de coleta e serviço de processamento
- Serviços e banco de dados
- API e aplicação de monitoramento
- Serviço de processamento e serviço de alertas

## Riscos Operacionais

Os principais riscos identificados inicialmente são:

- Falha de comunicação com os sensores
- Indisponibilidade da rede
- Parada do serviço de coleta
- Sobrecarga no processamento dos dados
- Falha no banco de dados
- Perda de informações
- Falha na geração de alertas
- Falta de espaço de armazenamento
- Acesso não autorizado
- Falta de logs suficientes para investigação de problemas

## Relação com Sistemas Operacionais

A arquitetura possui relação direta com diversos conceitos de Sistemas Operacionais:

### Processos e Serviços

Os componentes da solução dependem da execução contínua de processos e serviços.

### Entrada e Saída (E/S)

Os sensores IoT realizam a entrada de dados que serão processados pela solução.

### Rede

A comunicação entre sensores, Gateway e servidores depende da infraestrutura de rede.

### Memória

Os serviços utilizarão memória para processar as informações recebidas.

### Armazenamento e Filesystem

O sistema operacional será responsável pelo acesso ao armazenamento utilizado por arquivos, logs e outros dados da solução.

### Permissões

Usuários e serviços deverão possuir permissões adequadas para acessar os recursos necessários.

### Logs e Observabilidade

Logs e métricas serão utilizados para acompanhar o comportamento dos serviços e auxiliar na identificação de falhas.

### Disponibilidade

Os principais serviços deverão possuir mecanismos de reinício e recuperação para reduzir períodos de indisponibilidade.

### Virtualização e Containers

A utilização de máquinas virtuais ou containers poderá ser considerada nas etapas futuras para isolar e organizar os serviços da solução.

## Mapeamento da Arquitetura para o Sistema Operacional

A solução de Monitoramento IoT Industrial depende de recursos do Sistema Operacional para executar seus serviços, gerenciar memória, realizar operações de entrada e saída, controlar acesso a arquivos e manter a comunicação entre os componentes.

| Componente | Processo/Serviço | Recurso do SO | Risco |
|---|---|---|---|
| Gateway IoT | Serviço de comunicação | Rede e E/S | Perda ou atraso na comunicação com sensores |
| Serviço de coleta | Processo de coleta | Processos, memória e rede | Interrupção da coleta de dados |
| Serviço de processamento | Processo de processamento | CPU e memória | Sobrecarga e aumento do tempo de processamento |
| API | Serviço da API | Processos, memória e rede | Indisponibilidade de comunicação entre componentes |
| Banco de dados | Serviço de banco de dados | Memória, disco e filesystem | Perda de dados ou falta de espaço |
| Serviço de alertas | Processo de alertas | Processos e rede | Alertas não enviados |
| Logs e monitoramento | Serviço de observabilidade | Disco, filesystem e E/S | Crescimento excessivo dos logs e falta de espaço |

### Ambiente observado

O laboratório foi executado utilizando Ubuntu 26.04 LTS sobre WSL2, com kernel `6.18.33.2-microsoft-standard-WSL2`.

O ambiente apresentou aproximadamente 7,7 GiB de memória RAM disponível para o WSL, com cerca de 7,2 GiB disponíveis no momento da coleta. O filesystem principal do ambiente Linux apresentou aproximadamente 1007 GB de capacidade, com cerca de 955 GB disponíveis.

Entre os processos observados estavam `systemd`, `systemd-journald`, `rsyslogd`, `systemd-resolved` e serviços relacionados ao WSL.

Para o cenário de IoT Industrial, a rede é considerada um dos recursos mais críticos, pois a comunicação entre sensores, Gateway IoT e os serviços da solução depende da disponibilidade da comunicação. Falhas de rede podem causar atraso ou interrupção na coleta e processamento das medições.

### Processos e serviços

Os componentes da solução devem ser executados como processos ou serviços separados sempre que possível. Essa separação facilita o isolamento de falhas, monitoramento, reinicialização de serviços e identificação de consumo excessivo de recursos.

Durante o laboratório foi criado um processo controlado utilizando o comando `sleep`. Foram observados seu PID, PPID, estado, prioridade e informações disponíveis no diretório `/proc`. Após o encerramento do processo, ele deixou de aparecer na listagem de processos.

### Permissões e segurança

O Sistema Operacional deve aplicar o princípio do menor privilégio aos arquivos e serviços da solução.

Durante o laboratório, um arquivo de teste teve suas permissões removidas utilizando `chmod 000`. A tentativa de leitura por um usuário sem permissão foi negada pelo Sistema Operacional com a mensagem `Permission denied`.

Na solução IoT Industrial, arquivos de configuração, credenciais, logs e dados persistidos devem possuir permissões adequadas para reduzir o risco de acesso não autorizado.
