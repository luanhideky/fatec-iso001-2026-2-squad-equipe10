# Aula 03 - Reflexão individual

## 1. Ambiente

Kernel observado: 6.18.33.2-microsoft-standard-WSL2
Memória disponível: 3.2Gi de 3.7Gi totais
Uma informação que me chamou atenção: o disco do projeto tem 955G disponíveis de 1007G totais, mostrando que há bastante espaço livre para armazenar dados no ambiente.

## 2. Processo

PID observado: 866
PPID observado: 343
Explique com suas palavras a diferença entre programa e processo: Um programa é como uma receita guardada no disco, um arquivo parado que não faz nada sozinho. Um processo é o que acontece quando essa receita é executada: uma instância viva, com um PID único, ocupando memória e sendo gerenciada pelo kernel enquanto está em execução. O mesmo programa (sleep) pode gerar vários processos diferentes ao mesmo tempo, cada um com seu próprio PID.

## 3. Proteção

Quem negou a leitura do arquivo e por quê? Foi o kernel do sistema operacional, não o programa cat nem o disco físico. Quando removi as permissões com chmod 000, o kernel passou a negar qualquer tentativa de abrir o arquivo, pois ele verifica a identidade do usuário e as permissões do arquivo antes de permitir qualquer acesso. O disco apenas armazena os bytes; ele não tem noção de "permissão" — quem aplica essa política de proteção é o kernel.

## 4. Projeto da squad

Componente escolhido: Worker Python, responsável por processar as leituras dos sensores (temperatura, vibração, pressão) recebidas via MQTT no cenário de IoT Industrial.
Esse componente rodaria como quê? Processo/serviço, de forma parecida com o "sleep" que observamos: teria um PID, um estado, e seria gerenciado pelo kernel enquanto estiver em execução.
Se ele falhar, qual impacto de negócio aparece? As leituras enviadas pelos sensores parariam de ser processadas e gravadas no banco de dados. O monitoramento do chão de fábrica em tempo real deixaria de funcionar, mesmo que os sensores continuassem enviando dados normalmente.
Qual controle deveria existir? Restart automático (systemd), registro de logs a cada reinício, health check periódico para detectar travamentos, e um alerta caso o processo reinicie repetidamente em um curto período.

