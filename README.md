TCC — Aplicação do Lean Office e da Inteligência Artificial na Gestão de Contratos

Repositório de apoio ao Trabalho de Conclusão de Curso (Engenharia de Produção) que propõe e avalia um protótipo de automação, baseado em inteligência artificial, para a etapa de leitura e registro de informações em contratos — hoje realizada manualmente.

Sobre o projeto

O trabalho aplica os princípios do Lean Office para mapear o processo atual (AS-IS) de gestão de contratos e identificar os desperdícios associados à extração manual de informações. A partir desse diagnóstico, é proposto um processo futuro (TO-BE) em que um protótipo baseado em IA substitui as atividades manuais responsáveis por esses desperdícios.

A pesquisa segue a metodologia Design Science Research (DSR), de Peffers et al. (2007), estruturada em seis etapas: identificação do problema e motivação, definição dos objetivos da solução, projeto e desenvolvimento do artefato, demonstração, avaliação e comunicação.

O protótipo foi avaliado em uma amostra de 8 contratos públicos reais, comparando o processo manual (AS-IS) e o processo automatizado (TO-BE) a partir de três indicadores:

Tempo de processamento — tempo necessário para extrair os campos definidos de cada contrato;
Falhas de execução — ocorrência de erros técnicos durante o processamento automatizado;
Taxa de acerto da extração — percentual de campos extraídos corretamente, validado contra um gabarito de referência.
Estrutura do repositório
tcc-agente-ia-contratos/
├── README.md              # este arquivo
├── src/                    # código-fonte do protótipo
├── contratos/               # amostra dos 8 contratos públicos utilizados
├── gabarito/                 # gabarito de referência usado na validação da taxa de acerto
└── resultados/                # saídas/registros da validação do protótipo
Amostra de contratos

Os 8 contratos utilizados na amostra são públicos, obtidos em portais de órgãos governamentais (ex.: TCE-SP, TCE-PR, CEBRASPE, PM-RJ), e estão disponibilizados integralmente na pasta contratos/ para fins de reprodutibilidade. Dois deles (aquisição de veículo — TCE-SP; locação de frota — PM-RJ/CS Brasil) são documentos digitalizados (escaneados), exigindo etapa de OCR no processamento.

Como executar

Preencher com os passos reais de instalação/execução do protótipo (dependências, comando de entrada, variáveis de ambiente necessárias, etc.).

bash
pip install -r requirements.txt
python src/main.py
Tecnologias utilizadas
Python
Extração de texto/PDF: pdfplumber, pypdfium2, Pillow
Requisições HTTP: requests
Modelo de linguagem (LLM) via API para extração das informações contratuais
Contexto acadêmico

Trabalho de Conclusão de Curso — Engenharia de Produção — Centro Universitário IBMR (Rio de Janeiro).

Autores: Breno, José, Thais , Maike , Ernan.

Orientador: Prof. Francisco.
