# 📋 Dicionário de Dados – TOTVS Protheus

Consulta offline e instantânea de todo o Dicionário de Dados do TOTVS Protheus (SX2, SX3 e SIX), direto no navegador.

> **100% offline** — sem CDNs, fontes externas ou chamadas de rede. Funciona abrindo `index.html` localmente ou via GitHub Pages.

---

## 📊 Estatísticas

| Dado | Quantidade |
|------|-----------|
| Tabelas (SX2) | **10.816** |
| Campos (SX3) | **177.370** |
| Índices (SIX) | **25.461** |
| Shards de dados | **22 arquivos** |

---

## 🚀 Como Usar

### Localmente
Basta abrir o arquivo `index.html` no navegador (Chrome, Firefox, Edge, etc.):
```
index.html
```

### Via GitHub Pages
1. Faça push deste repositório para o GitHub
2. Vá em **Settings → Pages** e selecione a branch `main`, pasta `/ (root)`
3. Acesse em: `https://<seu-usuario>.github.io/dicionario_dados_protheus/`

---

## 🔍 Funcionalidades

- **Busca instantânea** por código da tabela (`SA1`, `SB1`), descrição (`Clientes`, `Produtos`) ou nome de campo (`A1_CGC`)
- **Paginação** com 100 tabelas por página e contador dinâmico
- **Carregamento sob demanda** (shards por letra inicial) para performance máxima
- **Detalhes completos**: cabeçalho da tabela, índices (SIX) e campos (SX3) com badges coloridos por tipo
- **Filtro de campos** dentro da tabela
- **Navegação por URL hash** (`#SA1`) e suporte a ESC / botão Voltar
- **Responsivo** (desktop + mobile)

---

## 📁 Estrutura do Projeto

```
dicionario_dados_protheus/
├── index.html              ← SPA principal
├── dados/
│   ├── tabelas_indice.js   ← Índice com resumo de todas as tabelas
│   ├── detalhes_A.js       ← Campos e índices das tabelas com prefixo A
│   ├── detalhes_B.js
│   ├── ...
│   └── detalhes_OUTROS.js
├── bruto/                  ← CSVs originais (ignorados pelo .gitignore)
│   ├── SX2990.rpt
│   ├── SX3990.rpt
│   └── SIX990.rpt
├── converter.ps1           ← Script de conversão (PowerShell)
├── converter.py            ← Script de conversão (Python)
├── .gitignore
└── README.md
```

---

## 🔄 Atualização dos Dados

Para atualizar o dicionário com novos dados exportados do SQL Server:

1. Exporte os dados atualizados para a pasta `bruto/` (formato CSV com `;` como separador, encoding UTF-8)
2. Execute o script de conversão:
   ```powershell
   powershell -ExecutionPolicy Bypass -File converter.ps1
   ```
3. Abra `index.html` para verificar

---

## 📝 Licença

Dados proprietários TOTVS. Uso interno.
