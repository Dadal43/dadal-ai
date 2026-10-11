# DADAL AI — MVP 0.1

## O que já funciona
- Interface responsiva para celular e computador.
- Comandos por texto.
- Reconhecimento de voz em navegadores compatíveis com Web Speech API (requer permissão do microfone; geralmente precisa de HTTPS ou localhost).
- Respostas faladas em português, quando o navegador suporta síntese de voz.
- Comandos de demonstração para luz, ar-condicionado, TV e luz do quarto.
- Memória e preferências salvas no armazenamento local do navegador.
- Lista de rotinas guardada localmente.
- Base de PWA/service worker para cache após a primeira visita por servidor compatível.

## Limitações importantes
- Os controles de luz/TV/ar são SIMULAÇÕES e não acionam aparelhos físicos.
- E-mail ainda não está conectado. Não digite senhas neste protótipo.
- Dados locais não sincronizam entre dispositivos.
- Rotinas são apenas uma lista; não geram notificações quando o aplicativo está fechado.
- “Aprender” nesta versão significa guardar preferências que o usuário explicitamente manda guardar; não treina um modelo de IA.
- Reconhecimento de voz pode depender da internet e do navegador, mesmo que a interface carregue offline.

## Como testar no computador
1. Extraia o ZIP.
2. Abra `index.html` no Chrome ou Edge.
3. Teste comandos por texto. Para microfone, pode ser necessário servir os arquivos via HTTPS ou localhost.

## Como testar no Android
Para melhor compatibilidade com microfone e instalação como app, hospede os arquivos em um endereço HTTPS (por exemplo, um servidor web próprio) e abra no Chrome Android. Use o menu do navegador > “Adicionar à tela inicial”/“Instalar app”, se aparecer.

## Próximas etapas para transformar em produto real
1. Sincronização segura entre aparelhos com autenticação e backend (ex.: Firebase/Supabase).
2. Home Assistant para controlar dispositivos físicos por integrações oficiais e token de acesso guardado no servidor.
3. Integração OAuth com Gmail/Outlook, com permissões mínimas e opção de confirmar antes de enviar mensagens.
4. Modelo de linguagem conectado por um backend para conversa mais inteligente; nunca colocar chave de API no HTML público.
5. Rotinas agendadas via serviço de automação e notificações push.
6. Camada de segurança: confirmação para ações sensíveis, logs, revogação de permissões e botão de emergência.

## Arquitetura sugerida
- Cliente: PWA responsiva (esta pasta).
- Backend: API autenticada para memória sincronizada e comandos.
- Automação residencial: Home Assistant.
- E-mail: OAuth 2.0 do provedor.
- IA: provedor de modelo via backend, com limites e proteção de dados.

Esta entrega é um protótipo funcional local, não uma integração residencial completa.
