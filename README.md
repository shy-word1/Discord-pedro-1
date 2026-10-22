# NOX — chat da tropa

Uma interface de conversa dark, responsiva e inspirada em apps de comunidade, feita em HTML/CSS/JavaScript.

## O que já funciona

- Layout responsivo para celular e computador
- Canais iniciais: geral, memes, games, skate e música
- Criar canais personalizados
- Apelido salvo no dispositivo
- Mensagens, links e reações rápidas
- Histórico local neste navegador
- Integração opcional com Supabase Realtime para mensagens ao vivo entre pessoas conectadas ao mesmo canal

## Importante sobre o chat ao vivo

Sem configurar um serviço de backend, o site funciona em modo local: as mensagens ficam salvas apenas no navegador/dispositivo usado. Para conversar de verdade entre celulares diferentes, conecta o Supabase:

1. Cria um projeto no [Supabase](https://supabase.com/dashboard).
2. No painel do projeto, copia a **Project URL** e a **publishable key** (ou a chave pública legacy `anon`).
3. Abre o NOX, entra em **Configurar** e cola os dois valores. Não uses a chave `service_role` nem uma chave secreta no navegador.
4. Confirma que o Realtime está habilitado no projeto e testa com dois navegadores/dispositivos abertos no mesmo canal.

O NOX usa canais públicos de Broadcast: quem tiver acesso ao site e souber o nome do canal pode entrar na conversa. Não uses para dados privados, senhas, endereços ou informações sensíveis. As mensagens transmitidas ao vivo não são armazenadas num banco compartilhado; o histórico salvo no momento fica local em cada navegador. Para uma versão de produção, o próximo passo é adicionar autenticação, banco de dados com políticas RLS e controles de moderação.

## Publicar na Vercel

Importa o repositório `shy-word1/Discord-pedro-1` na Vercel. Como é uma página estática sem build step, seleciona **Other** (ou deixa a detecção automática) e usa a raiz do repositório como diretório. Depois de conectado, cada commit na branch principal pode gerar um novo deploy.

## Arquivo

- `index.html` — interface, estilos e lógica do app em um arquivo só.
