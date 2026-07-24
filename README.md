# Gerador de Assinaturas Multsoft

Aplicativo local para gerar assinaturas no mesmo padrão visual do modelo fornecido.

## Como usar

1. Abra `index.html` no navegador.
2. Preencha nome, cargo, telefone, e-mail e endereço.
3. As logos padrão já estão configuradas como `Multsoft` e `MB Tratos`.
4. Se a marca final for diferente, envie a imagem em `Marca alternativa`.
5. Ajuste `X`, `Y` e `Largura` para encaixar a imagem alternativa no lado direito.
6. Use `Baixar PNG` para salvar a assinatura como imagem.
7. Use `Copiar HTML` para colar a assinatura em um editor de e-mail.

## Padrões de e-mail aplicados

- **Cores para fundo branco:** o texto usa verde `#2f7d1f`, contatos em cinza `#333`, tagline em teal `#0a7c93` e separadores claros — todos legíveis (WCAG AA) sobre o fundo branco padrão dos clientes de e-mail.
- **HTML em 600px:** a assinatura é gerada em tabela com CSS inline, largura máxima de 600px (padrão de e-mail, sem scroll no celular), com telefone, e-mail e site clicáveis.
- **PNG nítido (retina):** exportado com fundo transparente em `1200x300px` (2x) para exibição a `600x150px` — nítido em telas de alta densidade e no webmail.

## Imagens no e-mail (importante)

- Gmail e Outlook **não exibem** imagens em base64 (`data:`) nem caminhos relativos. Hospede numa URL pública HTTPS os cinco arquivos abaixo e informe essa URL no campo **URL base das logos**. O HTML passa a referenciar as imagens de lá, com `width`, `height` e `alt`:
  - `multsoft-wordmark.png`, `mb-tratos-wordmark.png` (logos)
  - `icon-phone.png`, `icon-mail.png`, `icon-location.png` (ícones de contato, estilo linha)
- Sem a URL base, o HTML cai no base64 embutido (`assets/logos.js`) apenas como fallback de preview — não confiável em e-mails reais.
- Para uma marca alternativa, prefira PNG transparente ou SVG já recortado no tamanho da área direita.

## Observações

- As imagens de origem ficam em `assets/multsoft-wordmark.png`, `assets/mb-tratos-wordmark.png` e `assets/logos.js`.
- A base está pronta para evoluir com importação de CSV e geração em lote.
