# Deploy · Showcase Lucas Porto (Porto OS)

Showcase de apresentação encriptado (StaticCrypt) para publicar no GitHub Pages com domínio próprio.

## O que tem nesta pasta
- `index.html` — o showcase completo (app + 2 landing pages + gerador + orçamento, tudo embutido) protegido por senha.
- `CNAME` — domínio `lucas.guilds.com.br`.

## Endereço e senha
- URL: **https://lucas.guilds.com.br**
- Senha: **lucas-portoos-2026**
- "Lembrar neste dispositivo por 7 dias" ativado (o Lucas digita a senha uma vez).

## Status da publicação
Se o Gustavo autorizou o device flow nesta sessão, o repositório, o GitHub Pages e o HTTPS já foram criados automaticamente. Só falta o passo de DNS abaixo.

## Passo manual do Gustavo: DNS no Wix
1. Wix → Domínios → guilds.com.br → Registros DNS.
2. Adicionar/editar CNAME: host = `lucas`, valor = `Gustavogm9.github.io`.
3. Salvar. Propaga em alguns minutos. O certificado HTTPS sai sozinho depois disso.

> IMPORTANTE: só mande o link pro Lucas depois que `https://lucas.guilds.com.br` abrir com cadeado. StaticCrypt só funciona em HTTPS; em http:// a senha certa falha como se estivesse errada.

## Mensagem de WhatsApp pro Lucas
> Lucas! Montei tudo o que conversamos num lugar só pra você navegar. Abre aqui no celular: https://lucas.guilds.com.br (senha: lucas-portoos-2026). Tem o app, as duas páginas e o orçamento. Dá uma olhada com calma e me fala o que achou 👊

## Trocar a senha depois
No sandbox, dentro da pasta com staticrypt instalado:
```
npx staticrypt lucas-porto_showcase.html -p "NOVA-SENHA" --remember 7 --short \
  --template-title "Lucas Porto · Acesso restrito" --template-button "Entrar" \
  --template-placeholder "Senha" --template-color-primary "#0F766E" \
  --template-color-secondary "#081210" -d out
```
Depois copiar `out/lucas-porto_showcase.html` para `index.html` e dar push de novo.

## Nota de segurança
A proteção é client-side (AES-256 no navegador). Serve para manter o showcase fora de buscadores e de acesso casual, adequado para uma proposta comercial. Não é cofre de dados sensíveis (não há dados reais de cliente aqui, só conteúdo de demonstração).
