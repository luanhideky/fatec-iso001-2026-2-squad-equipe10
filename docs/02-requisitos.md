# Requisitos do Sistema

## Visão Geral

Os requisitos abaixo representam uma proposta inicial para a solução de Monitoramento IoT Industrial da Equipe 10.

Eles poderão ser ajustados durante as próximas Sprints conforme a evolução da arquitetura e das decisões técnicas do projeto.

## Requisitos Funcionais

### RF01 - Receber dados dos sensores

A solução deverá receber continuamente os dados enviados pelos sensores IoT conectados ao ambiente industrial.

### RF02 - Identificar sensores e equipamentos

A solução deverá permitir identificar qual sensor realizou cada medição e a qual equipamento ele está relacionado.

### RF03 - Armazenar medições

A solução deverá armazenar as medições recebidas para permitir consultas posteriores.

### RF04 - Consultar dados coletados

O operador deverá conseguir consultar as informações coletadas pelos sensores.

### RF05 - Exibir informações de monitoramento

A solução deverá disponibilizar uma visão das informações coletadas para acompanhamento do ambiente industrial.

### RF06 - Gerar alertas

A solução deverá gerar alertas quando forem identificadas condições definidas como anormais.

### RF07 - Consultar histórico

A solução deverá permitir a consulta do histórico de medições e eventos registrados.

### RF08 - Registrar eventos e falhas

A solução deverá registrar eventos importantes e falhas ocorridas durante sua operação.

### RF09 - Controlar acesso

A solução deverá permitir diferentes níveis de acesso de acordo com o tipo de usuário.

## Requisitos Não Funcionais

### RNF01 - Disponibilidade

Os serviços responsáveis pela coleta e monitoramento deverão possuir mecanismos que permitam sua recuperação em caso de falha.

### RNF02 - Segurança

O acesso à solução deverá ser controlado por autenticação e permissões adequadas aos diferentes tipos de usuário.

### RNF03 - Integridade dos dados

As medições armazenadas deverão ser protegidas contra alterações ou perdas não autorizadas.

### RNF04 - Desempenho

A solução deverá processar as informações recebidas dos sensores sem causar atrasos excessivos na visualização dos dados e geração de alertas.

### RNF05 - Armazenamento

A solução deverá possuir capacidade de armazenar as medições, eventos e logs necessários para sua operação.

### RNF06 - Backup

Os dados considerados importantes deverão possuir estratégia de backup para reduzir o risco de perda de informações.

### RNF07 - Recuperação

A solução deverá possuir procedimentos de recuperação de dados e serviços em situações de falha.

### RNF08 - Logs

Os principais serviços deverão registrar logs de funcionamento, erros e eventos relevantes.

### RNF09 - Observabilidade

A solução deverá permitir o acompanhamento de métricas e informações relacionadas ao funcionamento dos seus principais componentes.

### RNF10 - Escalabilidade

A arquitetura deverá permitir evolução futura da quantidade de sensores e do volume de dados coletados.

## Relação com Sistemas Operacionais

Os requisitos possuem relação com os seguintes conceitos da disciplina:

- Processos e serviços
- Entrada e Saída (E/S)
- Comunicação em rede
- Gerenciamento de memória
- Filesystem
- Armazenamento
- Permissões
- Logs
- Backup e recuperação
- Disponibilidade
- Observabilidade
