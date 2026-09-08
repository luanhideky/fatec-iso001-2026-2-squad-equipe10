# Cenário de Negócio

## Tema

**Monitoramento IoT Industrial**

## Contexto

Ambientes industriais possuem máquinas, equipamentos e processos que precisam operar de forma contínua e confiável. Para acompanhar essas operações, sensores IoT podem ser utilizados para coletar dados dos equipamentos e enviá-los para uma solução central de monitoramento.

O projeto da Equipe 10 propõe uma solução de Monitoramento IoT Industrial capaz de receber continuamente informações provenientes de sensores, armazenar os dados coletados e disponibilizá-los para acompanhamento da equipe responsável pela operação.

Quando forem identificadas condições anormais, a solução deverá permitir a geração de alertas para auxiliar na identificação de possíveis falhas ou problemas operacionais.

## Problema de negócio

A falta de monitoramento contínuo pode dificultar a identificação de comportamentos anormais em equipamentos e processos industriais.

Sem uma solução centralizada, uma falha pode ser percebida somente depois de causar indisponibilidade, interrupção de processos ou impacto na operação.

A solução proposta busca centralizar a coleta e o acompanhamento dos dados provenientes de sensores IoT, permitindo maior visibilidade sobre o funcionamento do ambiente industrial.

## Atores

### Operador

Responsável por acompanhar as informações coletadas pelos sensores e visualizar possíveis alertas relacionados aos equipamentos monitorados.

### Gestor

Responsável por acompanhar o estado geral da operação e utilizar as informações do sistema para apoiar decisões relacionadas ao ambiente industrial.

### Administrador do Sistema

Responsável pela configuração, manutenção, permissões, disponibilidade e funcionamento da solução de monitoramento.

### Equipe de Suporte

Responsável por investigar problemas técnicos, analisar logs e auxiliar na recuperação da solução em situações de falha.

### Sensores IoT

Dispositivos responsáveis pela coleta contínua de informações dos equipamentos e processos monitorados.

## Dados envolvidos

A solução poderá trabalhar com os seguintes tipos de dados:

- Identificação dos sensores
- Identificação dos equipamentos monitorados
- Medições coletadas pelos sensores
- Data e horário das medições
- Eventos
- Alertas
- Logs do sistema
- Métricas de funcionamento da solução

## Impacto

A indisponibilidade ou funcionamento inadequado da solução pode causar:

- Falta de visibilidade sobre os equipamentos monitorados
- Atraso na identificação de condições anormais
- Perda de dados coletados pelos sensores
- Falha na geração de alertas
- Dificuldade na análise de problemas
- Impacto na continuidade da operação

## Premissas

Para o desenvolvimento inicial do projeto, serão consideradas as seguintes premissas:

- Os sensores IoT possuem capacidade de enviar dados pela rede.
- Os dados coletados serão enviados para uma solução central de monitoramento.
- As medições deverão ser armazenadas para consulta posterior.
- A solução deverá registrar logs de funcionamento.
- O acesso às informações deverá possuir controle de permissões.
- A solução deverá considerar mecanismos de recuperação em caso de falha.
- A arquitetura poderá evoluir durante as próximas Sprints conforme os conteúdos estudados na disciplina.

## Relação com Sistemas Operacionais

O cenário possui relação direta com conceitos de Sistemas Operacionais, principalmente:

- Entrada e Saída (E/S), devido à comunicação com sensores e dispositivos
- Processos e serviços responsáveis pela coleta e processamento dos dados
- Rede para comunicação entre sensores, serviços e aplicação
- Armazenamento dos dados coletados
- Filesystem para arquivos e logs
- Permissões e controle de acesso
- Disponibilidade e recuperação de serviços
- Logs e observabilidade
