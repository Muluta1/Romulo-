# FinanPro - Como Publicar Para Clientes

Este app é estático. Você pode publicar sem banco de dados e sem servidor próprio.

Abra `index.html` para testar no computador. Depois de publicado em HTTPS, ele também funciona como PWA instalável no celular.

## Opção Mais Fácil: Netlify Drop

1. Acesse `https://app.netlify.com/drop`.
2. Arraste o arquivo `FinanPro_publicar.zip` ou a pasta deste projeto.
3. O Netlify cria um link público.
4. Envie o link para os clientes.

## Opção Vercel

1. Crie uma conta na Vercel.
2. Envie esta pasta como projeto.
3. A Vercel detecta os arquivos estáticos e publica.

## Opção GitHub Pages

1. Crie um repositório no GitHub.
2. Envie os arquivos desta pasta.
3. Ative GitHub Pages apontando para a branch principal.

## Como Configurar o WhatsApp

1. Abra o arquivo `checkout-config.js`.
2. Em `whatsappNumber`, coloque seu número com DDI e DDD, por exemplo `5585999999999`.
3. Publique o site depois de salvar.

## Como Configurar Pix Mercado Pago

Não coloque senha, token, chave secreta ou dados bancários no site.

1. Abra `checkout-config.js`.
2. Confirme a chave em `pix.key`.
3. Ajuste `receiverName` e `city` se desejar.
4. Ajuste os valores em `prices`, se quiser vender por outro preço.
5. Publique o site depois de salvar.

Chave Pix configurada:

`a4606461-4d94-4c4d-8acb-48da7056a171`

Os botões do site abrem um pagamento Pix copia-e-cola para essa chave. Como o projeto é estático, ele não confirma pagamento automaticamente. Para confirmação automática, precisa backend com Mercado Pago API e webhook.

## Como Os Dados Funcionam

Cada cliente usa o próprio navegador. Os dados ficam salvos localmente no aparelho da pessoa, usando `localStorage`.

Isso é bom para começar rápido, porque não exige login nem servidor. Para uma versão mais avançada com conta, backup em nuvem e pagamento automático, será necessário backend.

Use `Exportar` para baixar um backup JSON e `Importar` para restaurar esse backup em outro navegador.

## Login e IA

O app tem login/cadastro local para separar os dados por e-mail no mesmo navegador. Esse login não valida pagamento automaticamente, porque o projeto é estático e não tem servidor.

A IA financeira funciona localmente, sem API externa: ela lê os dados cadastrados no app e responde sobre saldo, gastos, dívidas, metas, reserva, orçamento e alertas.

## Arquivos Importantes

- `index.html`: app principal.
- `checkout-config.js`: chave Pix Mercado Pago, preços e número do WhatsApp.
- `manifest.webmanifest`: instalação como app no celular.
- `service-worker.js`: cache/offline quando publicado em HTTPS.
- `privacidade.html`: política simples de privacidade.
- `termos.html`: termos de uso simples.
- `netlify.toml`: configuração para Netlify.
- `vercel.json`: configuração para Vercel.
- `assets/`: ícones e favicon.
