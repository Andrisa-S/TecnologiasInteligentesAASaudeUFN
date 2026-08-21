# Notas de Aula

## Semana 1 - 31/07/26
  ### Introdução
  - Apresentação do Plano de Ensino
    - Temas e conteúdos trabalhados
    - Nova forma de avaliação
      - 20% da nota é a participação efetiva
      - 20% da nota será as anotações em sala de aula
      - 60% desafios e trabalhos
        
  - **Predição X Previsão**
    - Predição - Predizer (dizer antecipadamente): Estimativa de resposta. Ato de afirmar com convicção aquilo que poderá acontecer num momento futuro;
    - Previsão - Prever (ver antecipadamente): Baseada na análise de dados históricos com o objetivo de estimar a evolução futura de uma determinada variável.
      
  - **Sistema de Recomendação X Sistema de Apoio a Decisão (SAD)**
    - SR: *Recomendação* a partir do histórico individual, com base no padrão *pessoal*;
    - SAD: *Sugestão* a partir do histórico geral, com base nos padrões *coletivos*.
  - Criação do Mapa Mental da Disciplina (arquivo mapaMentalTIAS.png)
    - IA na saúde:
      - Recomendação;
      - Predição e previsão;
      - Diagnóstico;
      - Monitoramento e sensoreamento.
    - Áreas:
      - Medicina e Odonto;
      - Enfermagem;
      - Farmácia;
      - Fisioterapia.
    - Domínios:
      - Engenharia e Projeto de Software;
      - Banco de Dados;
      - Sistemas Distribuídos;
        - Sistemas Operacionais;
        - Redes de Computadores;
        - Processamento de alto desempenho.
      - Processamento da Língua Natural;
      - Representação e Raciocínio de Conhecimento;
        - Ontologia;
        - Prolog.
      - Mineração de dados;
      - Redes Neurais;
        - Reconhecimento de padrões;
        - Aprendizado de máquina
          - Treinamento;
          - Amostra.
        - Automação;
        - Comunicação;
        - Negociação.
      - Sistemas Multiagentes.

----------------------
## Semana 2 - 07/08/26
  ### Revisão
  - **Técnicas de IA**
    - Redes Neurais - Reconhecimento de padrões
      - Base de conhecimento de amostras para treinamento
      - Raciocínio automatizado
      - Aprendizado de máquina

  - Processamento da Língua Natural

  - Sistemas Multiagentes
   
  - **Áreas da saúde:** 👩‍⚕️
    - Medicina, Odontologia ou Psicologia
      - Diagnóstico ou recomendação
    - Enfermagem
      - Monitoramento/Sensoriamento e atuação
    - Farmácia, Biomedicina ou Química
      - Predição ou Previsão -> recomendação

  - **Termos ou conceitos:**
    - Sistema de Apoio à Decisão (SAD) X Sistema de recomendação
    - Diagnóstico 🩺
		  - reconhecer padrões -> volume de dados -> algoritmos de aprendizado de máquina
	  - Monitoramento ou Sensoriamento Atuação
		  - automação
	  - Predição e Previsão
	  	- reconhecer padrões -> volume de dados -> algoritmos de mineração
	  - Recomendação
		  - Predição e Previsão
    - KDD: Descoberta de Conhecimento em BigData
      - Mineração de Dados (*Data Minning*)
        - Reconhecimento de Padrões (*Pattern Recognition*)
          - Redes Neurais Artificiais e Matemática
            - Algoritmos de Predição
            - Algoritmos de Previsão
    - Estatística X Mineração:
      - *Estatística:* Amostra (n) -> entender TUDO
      - *Mineração:* Tudo (**all**) -> entender UM indivíduo

----------------------
## Semana 3 - 14/08/26
- Apresentação e discussão da pesquisa
- Entender na prática a diferença de Predição e Previsão
	- Códigos python no Google Colab
		- pandas 🐼
   			- dataframes: são armazenados pós ETL
        	- métodos ou recursos de leitura de dados (SGBD ou csv ou json)
		- numpy
    		- Tratamento de estruturas de dados e conversões
		- scikitlearn:
			- Modelos pré-treinados (teoria de RNA: amostras repetidas e ajustes de peso):
				- Predição (classifica ou categoriza ou rotula ou etiqueta)
				- Previsão (a partir de série temporal estima o próximo item da série)
    - Treinamento de modelo
  		- **Regra do negócio:** atributos a serem avaliados
      	- Base de dados (fonte de amostras) para o treinamento
      	  - **ETL** (Extração, Transformação e Carga): organização de dados pré-treinamento
      	    - BD
      	      - plugins de conexão do pandas com SGBD
      		- csv
      	    - padronizar a estrutura de dados a ser minerada (KDD)
      	      - [] (lista)
      	      - {} (dicionário)
      	      - {key:dados}
      	- Definir se predição ou previsão
			
----------------------
## Semana 4 - 21/08/26
- Revisão **Predição e Previsão**
	- *Predição* - genérico - sem tempo futuro:
	    - CLASSIFICAR/CATEGORIZAR/ETIQUETAR/ROTULAR.
	- *Previsão* - específico - com tempo futuro:
   		- **Linha/Série temporal**;
   		- ESTIMAR/PREVER > TEMPO
	- Necessário uma *base* de dados **robusta** (volumes de dados consistente)

 - PROBLEMA (contexto)
	 1. Definir: Predição ou Previsão
	 2. Escolher base de dados
	 3. Aplicar ETL
	 4. Definir modelo -> BenchMark
----------------------
## Semana 5 - 28/08/26
