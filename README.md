# Scanner de Canhotos

App web para fotografar CT-e, NF-e e canhotos de entrega e salvar em PDF com o número do documento no nome.

- Lê a chave de acesso pelo código de barras e confere o dígito verificador.
- Frente e verso (ressalva) no mesmo PDF.
- Tudo é processado no celular: nenhuma foto ou PDF é enviado para servidor.

Publicado pelo GitHub Pages. Este repositório contém só o código do app, nenhum documento.

## Leitura do número da NF

- Nota fiscal sozinha (devolução): número lido pelo código de barras da DANFE.
- CT-e: o app lê a chave do CT-e e a linha "NF-E:" nas chaves do CT-e com OCR (Tesseract, rodando no próprio celular, pasta `ocr/`).
- Se encontrar o canhoto da NF na foto (ex.: "N. 469.952"), salva como `NF_469952.pdf`; sem canhoto, `CTe_469952.pdf`.

## Clientes e pastas

O arquivo `clientes.json` lista os clientes que aparecem no app. Para cada cliente, coloque em `cnpj` a raiz do CNPJ (8 primeiros dígitos) para o app reconhecer o cliente sozinho quando ler a chave da NF, por exemplo:

    { "nome": "Farmarin", "cnpj": ["12345678"] }

O PDF sai como `NF_469952__Farmarin__2026-07.pdf` e o organizador no servidor move para `Canhotos/Farmarin/2026/07 - Julho/NF/NF_469952.pdf`.
