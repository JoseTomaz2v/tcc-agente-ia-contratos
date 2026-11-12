# TCC — Aplicação do Lean Office e da Inteligência Artificial na Gestão de Contratos

Repositório de apoio ao Trabalho de Conclusão de Curso de Engenharia de Produção do Centro Universitário IBMR. Reúne o protótipo, os contratos da amostra e os arquivos usados na avaliação.

## Sobre o projeto

O trabalho mapeia um processo típico de gestão de contratos (AS-IS), classifica seus desperdícios com base no Lean Office e propõe um processo futuro (TO-BE) em que um protótipo com IA apoia a etapa de leitura e registro de informações contratuais. A conferência e a decisão continuam com o gestor do contrato.

A pesquisa segue o Design Science Research (Peffers et al., 2007). Dos módulos previstos no TO-BE, apenas o de **extração** foi implementado; regras, painel e alertas são proposta conceitual.

## Estrutura

```
tcc-agente-ia-contratos/
├── README.md
├── src/
│   └── prototipo_gestao_contratos.ipynb    # notebook do protótipo
├── contratos/                              # os 8 contratos da amostra (PDF)
└── gabarito/
    ├── gabarito.json                       # referência dos 12 campos por contrato
    ├── log_processamento.json              # tempo, tokens e status de cada chamada
    ├── relatorio_comparacao.json           # comparação automática campo a campo
    ├── revisao_campos_descritivos.csv      # veredito da revisão humana (72 campos)
    ├── resumo_extracao_texto.json          # páginas e caracteres extraídos por PDF
    └── resumo_paginas_imagem.json          # páginas renderizadas dos PDFs digitalizados
```

## Amostra

Oito contratos administrativos reais, publicados no Portal Nacional de Contratações Públicas (PNCP) sob a Lei nº 14.133/2021. Dois são digitalizações sem camada de texto pesquisável (contratos 3 e 6): nesses casos as páginas são renderizadas como imagem e lidas pelo próprio modelo de linguagem. O protótipo não usa biblioteca de OCR.

O arquivo `3_PRF-GM_21-2024.pdf` conserva o nome original, mas o contratante é o TCESP; a PRF é apenas o órgão gerenciador da ata à qual o TCESP aderiu.

## Resultados da avaliação

| Indicador | Resultado |
|---|---|
| Campos estruturados coincidentes com o gabarito | 24/24 |
| Campos descritivos concordantes após revisão humana | 69/72 |
| Contratos processados sem falha de execução | 8/8 |
| Tempo total das chamadas à API | ≈ 78 s |
| Custo estimado | ≈ US$ 0,20 |

Os três erros de conteúdo estão descritos em `gabarito/revisao_campos_descritivos.csv`. O gabarito foi elaborado com apoio de ferramenta de IA generativa, conferido nos documentos originais e corrigido durante a avaliação; as correções estão registradas no campo `observacoes` do próprio arquivo.

## Como executar

1. Python 3.14 e as bibliotecas: `pip install pdfplumber pypdfium2 Pillow requests`
2. Criar um arquivo `.env` na raiz com a linha `ANTHROPIC_API_KEY=sua_chave` (a chave não está no repositório).
3. Abrir `src/prototipo_gestao_contratos.ipynb` no Jupyter ou no VS Code e executar as células em ordem: extração de texto, renderização dos PDFs digitalizados, envio à API e comparação com o gabarito.

Modelo utilizado: `claude-haiku-4-5-20251001`, temperatura 0. A reprodução exata depende da disponibilidade dessa versão do modelo.

## Contexto acadêmico

Trabalho de Conclusão de Curso — Engenharia de Produção — Centro Universitário IBMR (Rio de Janeiro), 2026.

**Autores:** Breno, Ernan, José, Maike e Thais.

**Orientador:** Prof. Francisco José Rodrigues da Silva Junior.
