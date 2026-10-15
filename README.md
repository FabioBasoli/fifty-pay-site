# Site institucional Fifty Pay

Site estático em HTML e CSS puros, sem etapa de build. Pronto para subir no Git e publicar na Vercel.

## Estrutura

```
fifty-pay-site/
├── index.html                    Página principal
├── politica-de-privacidade.html  Política de privacidade (LGPD)
├── assets/
│   ├── styles.css                Estilos das duas páginas (cores no topo, em :root)
│   ├── fonts/                    Plus Jakarta Sans e Roboto hospedadas no próprio site (licença OFL)
│   └── img/                      Logo em SVG (fundo escuro e fundo claro) e og-image.png
├── favicon.svg, favicon.ico, favicon-32.png, apple-touch-icon.png
├── robots.txt
└── vercel.json                   URLs limpas, cabeçalhos de segurança e cache
```

### Arquivos do logo (assets/img)

| Arquivo | Uso |
|---|---|
| `fifty-pay-logo-fundo-escuro.svg` | Logo completo (símbolo e nome) sobre fundo escuro |
| `fifty-pay-logo-fundo-claro.svg` | Logo completo sobre fundo claro |
| `fifty-pay-icone.svg` / `fifty-pay-icone-fundo-claro.svg` | Só o símbolo "50" |
| `fifty-pay-nome.svg` / `fifty-pay-nome-fundo-claro.svg` | Só o nome "FiftyPay" |

Os SVGs foram reconstruídos a partir das imagens PNG/JPG da marca:

- **Anel e seta:** redesenhados em geometria exata.
- **Números "50":** vetorizados a partir da imagem.
- **Nome "FiftyPay":** Montserrat Bold e Regular, convertidas em curvas.

Servem para web e materiais digitais. Para impressão em grande formato, peça ao designer o arquivo-mestre e substitua os arquivos mantendo os mesmos nomes.

## Publicar

1. Crie o repositório e envie os arquivos:
   ```bash
   cd fifty-pay-site
   git init
   git add .
   git commit -m "Site institucional Fifty Pay"
   git branch -M main
   git remote add origin <URL do repositório>
   git push -u origin main
   ```
2. Na Vercel, clique em **Add New → Project** e importe o repositório. Configure assim:
   - **Framework Preset:** Other
   - **Build Command:** vazio
   - **Output Directory:** vazio (a raiz do repositório)
3. Para usar o domínio próprio, abra **Settings → Domains** e siga as instruções de DNS.

Com `cleanUrls`, a política abre em `/politica-de-privacidade`.

## Depois de ligar o domínio

- Inclua `<link rel="canonical" href="https://SEU-DOMINIO/">` no `<head>` das duas páginas.
- Troque `og:image` para o endereço completo (`https://SEU-DOMINIO/assets/img/og-image.png`).
- Opcional: crie `sitemap.xml` e acrescente a linha `Sitemap:` ao `robots.txt`.

## Pendências antes de ir ao ar

- **Encarregado (DPO):** a LGPD (art. 41) exige que a identidade e o contato do encarregado sejam públicos. Inclua o nome na seção 11 da política.
- **Revisão jurídica:** a política de privacidade é uma versão inicial. Peça ao jurídico para validar as bases legais, os prazos de retenção e a lista de compartilhamento.
- **Marca:** o pedido no INPI (processo 942471938) ainda não foi concedido. Não use o símbolo ® até a concessão.
- **Maquininha:** a ficha técnica usa os dados do terminal informado (Wi-Fi/3G/4G, tela de 5", comprovante impresso ou SMS) e as certificações do plano de negócios. Confirme que o modelo entregue aos clientes corresponde a essas especificações antes de publicar.

## Acessibilidade

A auditoria WCAG 2.1 AA com axe-core cobriu as duas páginas, nos temas claro e escuro, e não encontrou violações. Também foram verificados:

- contraste de todas as combinações de cores;
- link "Pular para o conteúdo";
- foco visível;
- alvos de toque de 44 px;
- tela de 320 px sem rolagem lateral;
- zoom de 200%;
- preferência de movimento reduzido.

Antes de publicar, faça um teste manual com leitor de tela (NVDA ou VoiceOver).
