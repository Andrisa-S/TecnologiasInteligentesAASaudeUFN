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

- **Modelos de Predição:**
  	1. Decision Tree Classifier
  		```python
  	 		from sklearn.tree import DecisionTreeClassifier
			modelo = DecisionTreeClassifier()
  	 	```
  		- Baseado em regras do tipo "if... else..."
  		- Interpretação fácil
  		- ❗ Pode sofrer com overfitting
  
  	2. Random Forest Classifier
  		```python
  	 		from sklearn.ensemble import RandomForestClassifier
			modelo = RandomForestClassifier()
  	 	```
  		- Conjunto de várias árvores de decisão
  		- Mais robusto que Decision Tree
  		- Usa média das previsões das árvores
  		- Boa performance geral
  
  	3. K-Nearest Neighbors (KNN)
  	   ```python
	  	   	from sklearn.neighbors import KNeighborsClassifier
			modelo = KNeighborsClassifier(n_neighbors=5)
  	   ```
  	   - Classifica com base nos vizinhos mais próximos
  	   - Simples e eficaz para dados pequenos
  	   - ❗Lento para grandes volumes de dados

	4. Support Vector Machine (SVM)
		```python
  			from sklearn.svm import SVC
			modelo = SVC()
  		```
  		- Tenta encontrar o melhor "limite" entre classes
  		- Eficiente em espaços de alta dimensão
  		- ❗Pode ser lento e difícil de ajustar

	5. Naive Bayes
		```python
  			from sklearn.naive_bayes import GaussianNB
			modelo = GaussianNB()
  		```
  		- Baseado em probabilidade (Teorema de Bayes)
  		- Rápido e eficiente
  		- Supõe independência entre variáveis (nem sempre é o caso)

  	6. Gradient Boosting Classifier
  	   ```python
  			from sklearn.ensemble import GradientBoostingClassifier
			modelo = GradientBoostingClassifier()
  	   ```
		- Método de boosting (modelo aprende com os erros anteriores)
  		- Alta acurácia
  		- ❗Mais lento para treinar, mas muito eficaz

	7. XGBoost / LightGBM / CatBoost (Modelos externos)
		- Requerem instalação extra:
			```python
   				pip install xgboost lightgbm catboost
   			```
   		- Exemplo com XGBoost:
  			```python
     			from xgboost import XGBClassifier
				modelo = XGBClassifier()
     		```
     	- Muito usados em competições de machine learning (Kaggle)
        - Altíssima performance e controle
        - Mais complexos, mas muito poderosos

	- *Como trocar?*	
   		Basta mudar a linha do modelo:
	   ```python
		# De:
		modelo = LogisticRegression()
		
		# Para, por exemplo:
		modelo = RandomForestClassifier()
		```
		
		E manter o restante igual:
		
		```python
		modelo.fit(X_train, y_train)
		y_pred = modelo.predict(X_test)
		```
  	- *Comparações* -
  	  Você pode comparar vários modelos com:
		* `accuracy_score`
		* `classification_report`
		* `confusion_matrix`
		* `cross_val_score`

----------------------
## Semana 5 - 28/08/26
