# Gerador de Assinaturas Multsoft

Aplicativo para gerar assinaturas no mesmo padrão visual do modelo fornecido. Publicado em **https://dhonleno.github.io/assinaturas/**.

## Como usar

1. Acesse o gerador pelo link publicado (não abra o arquivo local, para as imagens do e-mail funcionarem).
2. Preencha nome, cargo, telefone, e-mail, endereço e **slogan**.
3. Em **Aparência dos textos**, escolha a **fonte** e ligue **negrito/itálico** por elemento (Nome, Cargo, Contatos, Slogan).
4. As logos padrão já estão configuradas como `Multsoft` e `MB Tratos`.
5. Se a marca final for diferente, envie a imagem em `Marca alternativa` e ajuste `X`, `Y` e `Largura`.
6. Use `Copiar HTML` para colar a assinatura no editor de e-mail, ou `Baixar PNG` para a imagem.

## Personalização de textos

- **Slogan editável:** cada quebra de linha vira uma linha no bloco central.
- **Fonte:** apenas fontes seguras para e-mail (Arial, Verdana, Tahoma, Trebuchet, Georgia, Times, Courier, Segoe UI) — Gmail e Outlook ignoram fontes personalizadas.
- **Negrito/Itálico:** aplicáveis individualmente a Nome, Cargo, Contatos e Slogan.
- **Fundo decorativo:** padrão geométrico sutil (linhas de fluxo em degradê verde→teal) atrás do slogan e das logos, com fade para não atrapalhar os contatos. Pode ser ligado/desligado. No e-mail é aplicado via `background` na tabela (Gmail/Apple Mail exibem; Outlook desktop degrada para sem fundo, mantendo a legibilidade).

## Padrões de e-mail aplicados

- **Cores para fundo branco:** o texto usa verde `#2f7d1f`, contatos em cinza `#333`, tagline em teal `#0a7c93` e separadores claros — todos legíveis (WCAG AA) sobre o fundo branco padrão dos clientes de e-mail.
- **HTML em 600px:** a assinatura é gerada em tabela com CSS inline, largura máxima de 600px (padrão de e-mail, sem scroll no celular), com telefone, e-mail e site clicáveis.
- **PNG nítido (retina):** exportado com fundo transparente em `1200x300px` (2x) para exibição a `600x150px` — nítido em telas de alta densidade e no webmail.

## Imagens no e-mail (importante)

- Gmail e Outlook **não exibem** imagens em base64 (`data:`) nem caminhos relativos. Hospede numa URL pública HTTPS os arquivos abaixo e informe essa URL no campo **URL base das logos**. O HTML passa a referenciar as imagens de lá, com `width`, `height` e `alt`:
  - `multsoft-wordmark.png`, `mb-tratos-wordmark.png` (logos)
  - `icon-phone.png`, `icon-mail.png`, `icon-location.png` (ícones de contato, estilo linha)
  - `signature-bg.png` (padrão geométrico de fundo, transparente)
- Sem a URL base, o HTML cai no base64 embutido (`assets/logos.js`) apenas como fallback de preview — não confiável em e-mails reais.
- Para uma marca alternativa, prefira PNG transparente ou SVG já recortado no tamanho da área direita.

## Observações

- As imagens de origem ficam em `assets/multsoft-wordmark.png`, `assets/mb-tratos-wordmark.png` e `assets/logos.js`.
- A base está pronta para evoluir com importação de CSV e geração em lote.
