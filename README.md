$utf8NoBom = New-Object System.Text.UTF8Encoding($false)

$readme = @'
# 📚 Dicionário de Dados — TOTVS Protheus

Guia de consulta rápida e **100% offline** da estrutura de dados do ERP TOTVS Protheus, reunindo **10.816 tabelas**, **177.370 campos** e **25.461 índices** para apoio ao desenvolvimento ADVPL/TLPP, criação de queries SQL, integrações e análise de negócio.

## 🌐 Acessar Online

- 👉 **[Abrir Dicionário de Dados Interativo](https://misael2code.github.io/dicionario-dados-protheus/)**

---

## 🔍 O que você encontra aqui

- **Consulta por Tabela ou Descrição:** Encontre rapidamente qualquer tabela pelo código (`SA1`, `SB1`, `SC5`, `SE1`, etc.) ou pelo nome/descrição (`Clientes`, `Produtos`, `Pedidos de Venda`).
- **Busca Reversa por Campo:** Digite o nome de um campo (ex.: `A1_CGC`, `B1_COD`, `C5_NUM`) na busca principal para descobrir imediatamente a qual tabela ele pertence.
- **Ficha Técnica Completa da Tabela:**
  - **Cabeçalho:** Código, descrição oficial, modo de compartilhamento (`Exclusivo` ou `Compartilhado`) e chave única.
  - **Índices (`SIX`):** Ordem e composição das chaves de pesquisa e performance.
  - **Campos (`SX3`):** Ordem, nome técnico, tipo de dado (`Caractere`, `Numérico`, `Data`, `Lógico`, `Memo`), tamanho, casas decimais, título, descrição, contexto (`Real` ou `Virtual`), consulta padrão (`F3`) e obrigatoriedade.
- **Filtro Interno de Campos:** Dentro de qualquer tabela aberta, filtre colunas específicas por nome, título ou tipo de dado.
- **Links Diretos:** Compartilhe ou favorite uma tabela específica usando a URL com hash (ex.: `#SA1`, `#SB1`) e volte à listagem rapidamente pressionando `ESC`.

---

## 💻 Como Consultar Offline

1. Baixe ou clone este repositório no seu computador.
2. Abra o arquivo **`index.html`** diretamente no seu navegador (Google Chrome, Edge, Firefox, etc.).
3. Não exige instalação, banco de dados ativo ou conexão com a internet.
'@

[System.IO.File]::WriteAllText("$PWD\README.md", $readme, $utf8NoBom)
