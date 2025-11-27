 — Simulação de Ataques de Brute Force com Medusa (FTP, Web e SMB)
1. Objetivo do Trabalho
Este documento descreve, de forma acadêmica e ética, como funciona a simulação de ataques de força bruta utilizando o Medusa, ferramenta comum em ambientes de testes de segurança.

O objetivo deste trabalho é compreender:
Como ataques de força bruta são executados em serviços como FTP, HTTP (Web) e SMB.
Como avaliá-los de forma segura.
Como aplicar medidas defensivas para reduzir riscos e fortalecer o ambiente.
Este conteúdo é estritamente educacional. Testes devem ser feitos somente em ambientes controlados e autorizados.

2. Ferramenta Utilizada: Medusa
Medusa é um login brute-forcer rápido, modular e multithread, utilizado para auditorias e treinamento em segurança digital.
Características principais:
Alta velocidade devido ao suporte multithread.
Módulos individuais para diversos serviços.

Suporte a:
FTP
HTTP (Basic Auth e POST)
SMB
SSH, Telnet, VNC, entre outros.
Possibilidade de uso com listas de usuários e senhas.

3. Ambiente Utilizado para a simulação, o ambiente pode ser composto por:

Componente	Descrição
Sistema operacional de ataque	Kali Linux
Sistema alvo	Windows Server ou Linux
Tipo de rede	Host-only, NAT ou ambiente virtual controlado
Serviços configurados	FTP, servidor Web e SMB
As contas e serviços vulneráveis devem ser propositalmente configurados apenas para fins acadêmicos.

4. Conceito de Brute Force
O brute force é uma técnica onde são testadas diversas combinações de credenciais até que a combinação correta seja encontrada.

O processo envolve:
Definir um possível usuário.
Enviar diversas tentativas de senha.
Aguardar o retorno do serviço.
Registrar credenciais válidas quando encontradas.
Em ambientes reais, esse tipo de ataque costuma ser identificado rapidamente. A simulação em laboratório é controlada para evitar impactos.

5. Simulação em Serviços
A seguir está o processo de simulação para os serviços alvo. Não são fornecidos comandos ofensivos, apenas explicações conceituais adequadas a trabalhos acadêmicos.

5.1 Simulação em FTP

Processo da simulação:
Configuração de um servidor FTP vulnerável (ex.: vsftpd).
Criação de uma conta com senha fraca.
Medusa envia tentativas de login utilizando listas de usuários e senhas.
O servidor FTP retorna mensagens indicando sucesso ou falha.
A simulação encerra quando uma credencial válida é encontrada.

Riscos comuns:
Senhas fracas.
Falta de política de bloqueio por tentativas.
Exposição do serviço sem criptografia.

Medidas de defesa:
Exigir senhas fortes.
Usar chaves SSH no lugar de senhas simples.
Implementar fail2ban.
Preferir FTPS ou SFTP.

5.2 Simulação em HTTP (Web)

Aqui a simulação ocorre em sistemas Web com:
HTTP Basic Auth
Formulários de login tipo POST

Processo:
Identificação do método de autenticação.
Análise dos campos responsáveis por usuário e senha.
Envio das tentativas de login.
O servidor Web responde com códigos como 200, 401 ou 403.
Identificação do comportamento que indica sucesso.

Vulnerabilidades simuladas:
Falta de limitação de tentativas.
Ausência de CAPTCHA.
Mensagens diferentes para acerto/erro, facilitando fingerprinting.

Medidas de defesa:
Rate limiting.
Autenticação multifator.
Captcha.
Bloqueio automático de IP.

5.3 Simulação em SMB
O SMB permite compartilhamento de arquivos em ambientes Windows.
Processo da simulação:
Configuração de um compartilhamento SMB com credenciais fracas.
Envio de múltiplas tentativas de autenticação via Medusa.
Análise das respostas do serviço (sucesso ou falha).
Registro das credenciais válidas encontradas.

Riscos simulados:
Senhas fracas em contas locais.
Falta de políticas de bloqueio no Active Directory.
Exposição indevida de portas SMB.

Medidas de defesa:
Políticas rígidas de senha no AD.
Bloqueio automático após tentativas.
Desativar SMBv1.

6. Estrutura Recomendada para o Relatório Final
Introduçã
Contextualização e objetivos.
Metodologia
Ferramentas, ambiente e justificativa.
Simulação nos três serviços
Explicação do processo e riscos de cada um.
Discussão técnica
Impactos de senhas fracas.
Análise de logs.
Métodos modernos de mitigação.
Medidas de segurança
Hardening.

Políticas de autenticação.
Monitoramento e prevenção.
Conclusão
Importância de ambientes controlados.
Relevância prática na segurança ofensiva e defensiva.

7. Considerações Éticas e Legais
Testes devem ser realizados somente:
Em laboratórios próprios.
Em ambientes autorizados.
Com permissão formal.
Jamais realizar brute force em serviços de terceiros, ambientes corporativos ou redes públicas.

O uso indevido se enquadra em leis brasileiras como:
Marco Civil da Internet.

Lei 12.737/2012 (Carolina Dieckmann).
