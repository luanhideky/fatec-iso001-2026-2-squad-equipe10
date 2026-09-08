# ISO001 - Projeto da Disciplina

## Squad

**Equipe 10**

### Integrantes e papéis

- **PM:** Luan Hideki
- **Tech Lead:** Diego
- **Team Members:**
  - Kaue
  - Fabricio
  - Gustavo
  - Gabriel

## Tema escolhido

### Monitoramento IoT Industrial

O projeto aborda um cenário de Monitoramento IoT Industrial, no qual sensores realizam a coleta contínua de dados de equipamentos e processos em um ambiente industrial.

A proposta é permitir o acompanhamento dessas informações e a geração de alertas quando forem identificadas condições anormais de operação.

## Problema de negócio

Em ambientes industriais, equipamentos e processos precisam ser acompanhados continuamente. A ausência de monitoramento adequado pode dificultar a identificação de falhas, indisponibilidades ou comportamentos anormais.

A solução proposta deverá coletar e armazenar informações provenientes de sensores IoT, permitindo o acompanhamento dos dados e a geração de alertas para auxiliar a operação.

## Componentes previstos

Como arquitetura inicial, estão previstos os seguintes componentes:

- Sensores IoT
- Gateway IoT
- Rede de comunicação
- Serviço de coleta de dados
- Banco de dados
- Aplicação de monitoramento
- Dashboard
- Serviço de alertas
- Logs e monitoramento da infraestrutura

> A arquitetura poderá ser alterada durante as próximas Sprints conforme a evolução dos requisitos e das decisões técnicas da squad.

## Conceitos de Sistemas Operacionais envolvidos

O projeto será relacionado principalmente aos seguintes conceitos:

- Processos e serviços
- Entrada e Saída (E/S)
- Comunicação em rede
- Armazenamento
- Gerenciamento de memória
- Filesystem
- Permissões
- Logs
- Disponibilidade
- Observabilidade
- Virtualização e containers

## Documentação

- [Cenário de Negócio](docs/01-cenario-negocio.md)
- [Requisitos](docs/02-requisitos.md)
- [Arquitetura](docs/03-arquitetura.md)
- [Decisões Técnicas](docs/04-decisoes-tecnicas.md)
- [Operação e Observabilidade](docs/05-operacao-observabilidade.md)

## Diagramas

- [Diagrama de Contexto](diagrams/contexto.mmd)
- [Diagrama de Containers](diagrams/containers.mmd)
- [Diagrama de Deployment](diagrams/deployment.mmd)

## Backlog

- [Sprint 01](backlog/sprint-01.md)
- [Sprint 02](backlog/sprint-02.md)

## Evidências

- [Evidências do Projeto](evidencias/README.md)
