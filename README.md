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
