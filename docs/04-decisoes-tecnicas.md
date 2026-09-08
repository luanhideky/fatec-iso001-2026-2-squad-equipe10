# Decisões Técnicas

Este documento registra as decisões técnicas iniciais propostas para a solução de Monitoramento IoT Industrial da Equipe 10.

As decisões poderão ser revisadas durante as próximas Sprints conforme a evolução dos requisitos e dos conteúdos estudados na disciplina.

---

## ADR-001 - Utilização de Gateway IoT

### Contexto

Os sensores instalados no ambiente industrial precisam enviar continuamente suas informações para a solução de monitoramento.

Conectar todos os sensores diretamente aos serviços principais da aplicação pode aumentar a complexidade da comunicação e dificultar o gerenciamento dos dispositivos.

### Decisão

Utilizar um Gateway IoT como ponto intermediário entre os sensores e os serviços da solução.

### Justificativa

O Gateway centraliza a comunicação dos dispositivos e permite separar a camada de sensores dos serviços responsáveis pelo processamento e armazenamento dos dados.

### Consequências

**Vantagens:**

- Centralização da comunicação com os sensores
- Melhor organização da arquitetura
- Redução do acoplamento entre sensores e aplicação
- Possibilidade de tratamento inicial dos dados

**Desvantagens:**

- O Gateway se torna um componente importante para a disponibilidade da solução
- Uma falha nesse componente pode interromper temporariamente o envio dos dados

### Trade-off

A utilização do Gateway adiciona um componente extra à arquitetura, porém simplifica a comunicação e o gerenciamento dos sensores.

### Conexão com Sistemas Operacionais

- Entrada e Saída (E/S)
- Rede
- Processos
- Disponibilidade

---

## ADR-002 - Separação dos Serviços da Solução

### Contexto

A solução precisa realizar diferentes atividades, como receber dados, processar informações, disponibilizar consultas e gerar alertas.

Executar todas essas responsabilidades em um único processo pode dificultar o monitoramento e a recuperação em situações de falha.

### Decisão

Separar as principais responsabilidades em serviços distintos.

Inicialmente serão considerados:

- Serviço de coleta
- Serviço de processamento
- API
- Serviço de alertas
- Aplicação de monitoramento

### Justificativa

A separação permite acompanhar cada serviço individualmente e facilita a identificação de problemas.

### Consequências

**Vantagens:**

- Melhor organização da solução
- Possibilidade de reiniciar apenas o serviço que apresentar falha
- Maior facilidade de monitoramento
- Possibilidade de evolução independente dos componentes

**Desvantagens:**

- Aumenta a quantidade de processos e serviços que precisam ser administrados
- Exige comunicação entre os componentes

### Trade-off

A arquitetura se torna um pouco mais complexa, porém melhora o isolamento e a capacidade de recuperação dos serviços.

### Conexão com Sistemas Operacionais

- Processos e serviços
- Escalonamento
- Memória
- Rede
- Logs
- Disponibilidade

---

## ADR-003 - Persistência das Medições em Banco de Dados

### Contexto

As informações recebidas dos sensores precisam ser armazenadas para permitir consultas posteriores e análise do histórico da operação.

### Decisão

Utilizar um banco de dados para armazenar as medições, eventos, informações dos sensores e alertas.

### Justificativa

A persistência permite manter um histórico das informações coletadas e evita que os dados existam apenas durante o processamento.

### Consequências

**Vantagens:**

- Consulta ao histórico de medições
- Centralização das informações
- Possibilidade de análise posterior
- Persistência dos dados

**Desvantagens:**

- O banco de dados passa a ser um componente crítico
- Será necessário controlar espaço de armazenamento
- Exige estratégia de backup e recuperação

### Trade-off

O armazenamento permanente consome recursos de disco e exige manutenção, porém é necessário para preservar o histórico da solução.

### Conexão com Sistemas Operacionais

- Armazenamento
- Entrada e Saída de disco
- Filesystem
- Backup
- Disponibilidade

---

## ADR-004 - Registro de Logs dos Serviços

### Contexto

Falhas em serviços, comunicação ou processamento precisam ser identificadas e investigadas pela equipe responsável pela operação.

### Decisão

Os principais serviços da solução deverão registrar logs de funcionamento, erros e eventos relevantes.

### Justificativa

Os logs permitem acompanhar o comportamento da solução e auxiliam na identificação da causa de problemas.

### Consequências

**Vantagens:**

- Facilita a investigação de falhas
- Permite acompanhar eventos da solução
- Auxilia no monitoramento e suporte

**Desvantagens:**

- Logs ocupam espaço de armazenamento
- Será necessário definir política de retenção e limpeza

### Trade-off

O armazenamento de logs aumenta o consumo de disco, porém fornece informações importantes para operação e diagnóstico.

### Conexão com Sistemas Operacionais

- Filesystem
- Entrada e Saída
- Armazenamento
- Permissões
- Logs
- Observabilidade
