# Operação e Observabilidade

Este documento descreve uma proposta inicial de como a solução de Monitoramento IoT Industrial poderá ser operada, monitorada, protegida e recuperada em situações de falha.

As definições poderão evoluir durante as próximas Sprints conforme o desenvolvimento da arquitetura.

## Execução da Solução

Os principais componentes da solução deverão funcionar como serviços independentes.

Inicialmente são considerados:

- Serviço de coleta de dados
- Serviço de processamento
- API
- Serviço de alertas
- Aplicação de monitoramento
- Banco de dados
- Serviços de logs e monitoramento

Os serviços responsáveis pela coleta e processamento dos dados deverão permanecer em execução para permitir o recebimento contínuo das informações provenientes dos sensores IoT.

## Monitoramento

Os principais componentes da solução deverão ser monitorados para identificar falhas e indisponibilidades.

O monitoramento poderá acompanhar informações como:

- Estado dos serviços
- Disponibilidade da aplicação
- Comunicação com o Gateway IoT
- Comunicação com o banco de dados
- Consumo de memória
- Uso de CPU
- Uso de armazenamento
- Quantidade de erros
- Falhas de comunicação
- Funcionamento do serviço de alertas

## Logs

Os principais serviços deverão registrar logs de funcionamento.

Os logs poderão registrar:

- Inicialização e encerramento de serviços
- Erros de processamento
- Falhas de comunicação
- Falhas de acesso ao banco de dados
- Eventos relacionados aos sensores
- Geração de alertas
- Tentativas de acesso
- Erros da aplicação

Os logs deverão possuir uma política de armazenamento e retenção para evitar consumo excessivo de espaço em disco.

## Métricas e Alertas

A solução deverá permitir o acompanhamento de métricas relacionadas ao seu funcionamento.

Exemplos de métricas:

- Uso de CPU
- Uso de memória
- Espaço disponível em disco
- Quantidade de dados recebidos
- Quantidade de sensores ativos
- Quantidade de erros
- Tempo de resposta dos serviços
- Disponibilidade dos componentes

Alertas operacionais poderão ser gerados quando forem identificadas situações como:

- Serviço indisponível
- Falha de comunicação
- Uso elevado de recursos
- Falta de espaço de armazenamento
- Falha no banco de dados

## Segurança e Permissões

O acesso aos recursos da solução deverá seguir o princípio de menor privilégio.

Usuários e serviços deverão possuir somente as permissões necessárias para realizar suas atividades.

Inicialmente serão considerados diferentes níveis de acesso:

- Operador
- Gestor
- Administrador
- Equipe de suporte

O acesso aos arquivos, logs, banco de dados e serviços deverá ser controlado de acordo com as responsabilidades de cada usuário.

## Backup

Os dados considerados importantes deverão possuir estratégia de backup.

O backup poderá incluir:

- Banco de dados
- Configurações importantes
- Arquivos necessários para recuperação da solução

A política de backup deverá considerar periodicidade, armazenamento e verificação da integridade dos dados.

## Recuperação de Falhas

A solução deverá possuir procedimentos para recuperação em situações de falha.

Exemplos:

- Reinício de serviços
- Restauração de backup
- Recuperação do banco de dados
- Investigação por meio de logs
- Verificação da comunicação de rede
- Verificação do Gateway IoT

## Disponibilidade

Os serviços responsáveis pela coleta, processamento e armazenamento dos dados são importantes para a continuidade da solução.

Medidas de disponibilidade poderão incluir:

- Monitoramento do estado dos serviços
- Reinício automático em caso de falha
- Backup dos dados
- Monitoramento de recursos
- Identificação rápida de indisponibilidades

## Reinício de Serviços

Serviços críticos poderão ser configurados para reiniciar automaticamente quando houver encerramento inesperado.

O reinício deverá ser acompanhado por registros em logs para permitir a identificação da causa da falha.

## Plano de Contingência

Em caso de indisponibilidade da solução, a equipe responsável deverá:

1. Identificar qual componente apresentou falha.
2. Verificar logs e métricas disponíveis.
3. Verificar comunicação de rede.
4. Verificar o estado dos serviços.
5. Reiniciar o serviço quando necessário.
6. Verificar o banco de dados e o armazenamento.
7. Restaurar dados a partir de backup quando necessário.
8. Confirmar o retorno da operação.

## Relação com Sistemas Operacionais

A operação da solução possui relação com os seguintes conceitos:

- Processos e serviços
- Gerenciamento de CPU e memória
- Filesystem
- Permissões de usuários e grupos
- Entrada e Saída
- Armazenamento
- Rede
- Logs
- Backup e recuperação
- Disponibilidade
- Observabilidade
