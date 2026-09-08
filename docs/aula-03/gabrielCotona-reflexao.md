# Aula 03 - Reflexão individual

## 1. Ambiente
Kernel observado: Linux 6.8 (Ubuntu 24.04.4 LTS - Noble Numbat)
Memória disponível: 5.4Gi
Uma informação que me chamou atenção: Achei interessante ver que mesmo em um ambiente limpo (Codespace recém-criado) já existem vários processos rodando em segundo plano, cuidando de tarefas do sistema sem que eu tenha feito nada. 

## 2. Processo
PID observado: 30845
PPID observado: 26912
Explique com suas palavras a diferença entre programa e processo: Um programa é apenas um arquivo guardado no disco, com instruções paradas, esperando para ser executado. Um processo é o que acontece quando esse programa é colocado em execução: o sistema operacional carrega o código na memória, atribui um PID único e passa a gerenciar seu estado (rodando, dormindo, etc). Ou seja, o programa é a receita; o processo é a receita sendo preparada naquele momento.

## 3. Proteção
Quem negou a leitura do arquivo e por quê? O kernel do Linux negou o acesso. Quando executei o comando chmod 000, removi todas as permissões de leitura, escrita e execução do arquivo segredo.txt. Ao tentar ler o arquivo com cat, o kernel verificou as permissões antes de liberar o acesso e, como nenhuma permissão estava concedida, retornou o erro "Permission denied". Isso mostra que o sistema operacional é o intermediário entre a aplicação e os dados, controlando quem pode acessar o quê.

## 4. Projeto da squad
Esse componente rodaria como quê? A API do projeto rodaria como um processo (ou serviço) contínuo no servidor, ficando em execução o tempo todo para responder às requisições dos usuários.
Se ele falhar, qual impacto de negócio aparece? Se o processo da API cair, os usuários não conseguem mais acessar o sistema, perdendo funcionalidades como login, consultas e cadastros — gerando indisponibilidade e possível perda de confiança dos clientes.
Qual controle deveria existir?  Deveria existir um healthcheck automático que verifica periodicamente se o processo está ativo, com restart automático em caso de falha, além de logs para registrar o motivo da queda e permitir diagnóstico rápido.
