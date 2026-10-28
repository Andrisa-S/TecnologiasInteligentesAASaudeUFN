# Atividade Avaliativa ER Clinic
  - [PDF Apresentação](https://github.com/alexandrezamberlan/tias/blob/main/Tecnologias%20Inteligentes%20Aplicadas%20a%CC%80%20Sau%CC%81de%20-%20ERClinic.pdf)
  - 10 pontos
  - [Atividade final](https://github.com/Andrisa-S/TecnologiasInteligentesAASaudeUFN/blob/main/Relat%C3%B3rio%20%E2%80%93%20Intelig%C3%AAncia%20Artificial%20na%20Sa%C3%BAde%20ER%20Clinic.pdf)

## Tarefas:
- [ ] Prestar atenção
- Gerar relatório:
  - [ ] Técnicas de IA utilizadas e quais situações/cenários
  - [ ] Avaliar a relação situação/cenário com técnica IA utilizada

# Relatório

  - **Título:** Inteligência Artificial na Saúde - Tecnologia para ampliar a eficiência sem perder o humano
  - *ER Clinic* - Healthtech Santamariense - 11 anos (2015)
  - Projeto *Treino Scout*: Torneios de integração, IA (inferência para identificação de categorias, sugestão de treino baseado no desempenho dos scouts) e Scout de atletas
  - Custo de aquisição do cliente
  -
  ### Inteligência Artificial na Saúde
  
  - A IA não precisa substituir pessoas para transformar profissões
      - Tarefas repetitivas -> IA
      - Tarefas analíticas -> IA + Profissional
      - Relação Humana -> Profissional

    - Pesquisa => Prevenção => Diagnóstico => Tratamento => Acompanhamento => Gestão => Atendimento
    - Áreas amplas: Pesquisa, imagem e documentação clínica
    - Prontuário deve ser guardado por 10 anos
    - IA **≠** Verdade
      - Se erra padrões, pode errar probabilidade e interpretar mal a resposta
      - Criar camadas de segurança, como criatividade 0
    - Regra de ouro:
      - IA: Analisa, organiza, sugere e acelera
      - Profissional: Interpreta, contextualiza, decide, assume responsabilidade
    - Parte clínica deve ter regulação:
      - CFM / Resolução nº 2.454/2026 **(Níveis de risco)**
      - LGPD: dados referentes à saúde são dados pessoais sensíveis
      
### Técnicas de IA utilizadas e situações/cenários
IA ao longo da jornada do paciente:
- Agendamento
  - Chatbot para Whatsapp: atendimento 24h e agendamento automático
    - - LLM e fluxo de agentes
    - Atualmente: recurso integrado com parceiro
    - Desejam: desenvolver o próprio recurso
    - **API para integração de terceiros:**
      - RAG (consulta nos endpoints da API)
      - Prompt Engineering
      - Processos N8N
  - Baseado em dados da plataforma, alerta para paciente com alto risco de não comparecimento
    - Base com dados estruturados:
      - Faltas anteriores
      - Dia e horário da consulta
      - Convênio
    - *IA vai muito além das LLMs**
    - Machine Learning supervisionado para estimar a probabilidade de um paciente não comparecer a uma consulta agendada.
  - **Técnica utilizada:**
    - Algoritmo: XGBoost, baseado em árvores de decisão combinadas (gradient boosting);
    - Tipo de problema: classificação binária, com estimativa probabilística; *target*: comparece ou não;
    - Treinamento supervisionado:  cada agendamento histórico é associado a um resultado conhecido: compareceu ou não compareceu
    - Inferência:  quando um agendamento é criado, o modelo analisa suas características e retorna uma probabilidade de falta, que o sistema apresenta em faixas de risco.
    - Importância das variáveis: selecionar *features* adequadas, elas permitem identificar padrões estatísticos que podem prever o comportamento futuro.
      - Exemplo da venda do sorvete e taxa de afogamento: correlação não implica casualidade.
    - Atualização e avaliação do modelo:
      - Considera métricas como *ROC AUC*, *Average Precision* e *Brier Score*
        
- Transcrição da consulta
  - Ouve a consulta, preenche automaticamente o prontuário: Evolução, história da doença atual, hipótese diagnóstica, medicações e plano de tratamento.
    - Atualmente: recurso integrado com parceiro
    - Desejam: desenvolver o próprio recurso
    - **Tecnologias-chave:**
      - Captura e transmissão de áudio em fragmentos
      - Reconhecimento automático de fala (ASR/STT)
      - LLM e *Prompt Engineering* para extração e organização das informações clínicas
    - Fluxo técnico:
      1) Captura de áudio
      2) Reconhecimento de fala *(Speech-to-Text)*
      3) Contextualização clínica
      4) LLM + Prompt Engineering
      5) Revisão profissional
    - Solução própria
      - Fluxo previsto: Áudio -> Transcrição -> Contextualização clínica -> LLM -> Dados estruturados -> Prontuário
      - Reconhecimento de fala
      - Base de conhecimento por especialidade: técnicas de *RAG* (Retrieval-Augmented Generation)
      - Prompt Engineering
      - **Desafio de arquitetura:** onde fazer a transcrição?
        1) Capturar o áudio e enviá-lo em fragmentos ao servidor
        2) Transcrever no frontend e enviar somente o texto

           Minha solução:
           - Capturar o áudio e transcrever de forma nativa e natural, como os áudios do whatsapp ou gravações do android;
           - Servidor armazena áudio e texto, retornando somente texto para cliente.
  - Resumo automático do prontuário
    - Testaram modelos de sumarização (Hugging Face)
    - Usaram modelos comerciais, usam modelos pagos via OpenRouter
    - **Tecnologias utilizadas:**
      - LLM via *OpenRouter*
      - **Prompt Engineering**
      - Python + Django
      - JSON + renderização HTML
      - Fluxo do processo:
        1) Coleta
        2) Organização
        3) Contextualização
        4) Síntese pela LLM
        5) Referências navegáveis
        6) Atualização incremental
      - Principal desafio técnico: Foi necessário desenvolver um algoritmo que conhecesse essas estruturas e soubesse extrair os dados relevantes de cada uma, consolidando tudo em um histórico textual coerente antes de enviá-lo à LLM.
      - Camadas de cuidado *guardrails*
        - Relevância clínica
        - Controle temporal
        - Redução de alucinações
        - Rastreabilidade
        - Renderização segura
        - Controle operacional
    
- Exames
  - A partir da foto ou PDF do exame, destaca automaticamente resultados fora de padrões de referência
  - Organiza as informações e gera um parecer final para apoiar a análise clínica
  - Armazena o histórico do paciente, permite acompanhar a evolução dos resultados por meio de gráficos
  - **Tecnologias utilizadas:**
    - LLM multimodal via *OpenRouter*: recebe os arquivos e interpreta o conteúdo, extraindo informações
    - Processamento de arquivos: PDFs e imagens codificadas em Base64
    - Utilizado anteriormente - OCR: código implementa PyMuPDF para extração de texto de PDFs e Tesseract OCR para PDFs digitalizados e imagens
    - *Python + Django + Celery:* gerenciam o processamento assíncrono
    - Identifica referência da clínica
    - Fluxo do processo:
      1) Entrada
      2) Preparação
      3) Interpretação pela IA
      4) Análise individual
      5) Parecer geral
      6) Persistência
    - O sistema de IA interpreta documentos com instruções explícitas *(prompt engineering)* com a capacidade do modelo interpretar documentos e imagens. A resposta é um JSON estruturado, que converte em registros individuais.
    - Camadas de cuidado *(guardrails)*:
      - Preservação dos dados
      - Contextualização
      - Controle da resposta
      - Confiabilidade operacional
      - Segurança clínica
   
- Copiloto clínico - **Córtex**
  - A partir da base privada de conhecimento da clínica, localiza protocolos e conteúdos relevantes
  - Organiza informações e sugere condutas, exames e tratamentos com referêcnias
  - Informação do paciente -> conhecimento da clínica -> busca organização, sugestão -> referências: decisão do profissional
  - **Técnica principal:** RAG *(Retrieval-Augmented Generation)*
    - Pipeline de conhecimento:
      1) Extração
      2) Chunking
      3) Embeddings: selecionar trechos em vetores numéricos que representam características semânticas do conteúdo, reduz o uso de tokens
      4) Base vetorial
      5) Recuperação: busca semântica
      6) Reranking: reclassificação dos resultados para selecionar os mais pertinentes
      7) Geração: *Prompt Engineering*
  - **Tecnologias utilizadas:**
    - LLM configurável por copiloto; utiliza GPR-5 como exemplo, mas também trabalham com Gemini Flash
    - Embeddings: OpenAI ```text-embedding-3-small```, codificação do texto para vetores
    - Banco vetorial: Pinecone, com busca de similaridade semântica
    - Reranking: Cohere Rerank, refina a seleção dos trechos recuperados
    - Backend: API REST em Django, com processamento assíncrono via Celery e Redis. Integra o serviço com a plataforma ERClinic via API.
  - Guardrails e rastreabilidade
    - Base privada
    - Respostas fundamentadas
    - Controle de conteúdo
    - Saída estruturada
    - Rastreabilidade
  - Principal desafio: Recuperar os trechos certos, fornecer contexto suficiente, evitar informações sem sustentação documentar e avaliar se a resposta realmente corresponde às fontes consultadas.

### Avaliação
