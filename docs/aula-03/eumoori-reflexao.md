# Aula 03 - Reflexão individual

## 1. Ambiente

Kernel observado: 6.8.0-1052-azure

Memória disponível: aproximadamente 5,6 GiB no momento da coleta.

Uma informação que me chamou atenção: o Sistema Operacional disponibiliza informações detalhadas sobre memória, processos, armazenamento e outros recursos, permitindo observar e diagnosticar o funcionamento do ambiente.

## 2. Processo

PID observado: 4185

PPID observado: 3037

Um programa é um conjunto de instruções armazenado, enquanto um processo é uma instância desse programa em execução. Cada processo possui informações próprias, como PID, estado e recursos utilizados, que podem ser observadas pelo Sistema Operacional.

## 3. Proteção

A leitura do arquivo foi negada pelo kernel do Linux porque as permissões do arquivo foram alteradas para `000`. Dessa forma, o usuário comum não possuía permissão de leitura. O teste resultou na mensagem `Permission denied`, demonstrando o controle de acesso realizado pelo Sistema Operacional.

## 4. Projeto da squad

Componente escolhido: Serviço de Coleta.

Esse componente rodaria como um processo/serviço contínuo no servidor Linux.

Se ele falhar, os dados enviados pelo Gateway IoT podem deixar de ser coletados, causando perda ou atraso das informações utilizadas no monitoramento industrial.

Como controle, o serviço deve possuir logs, monitoramento de funcionamento, healthcheck e mecanismo de reinicialização em caso de falha.
