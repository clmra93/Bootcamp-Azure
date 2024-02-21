# Bootcamp-Azure
Workspace Azure Machine Learning

Passo a passo para criar um Modelo de Machine Learning:

Criar um Workspace do Azure Machine Learning:

No portal do Azure, clique em "Criar um recurso" e pesquise por "Machine Learning".
Selecione "Machine Learning" na lista de resultados e clique em "Criar".
Preencha as informações necessárias, como nome, grupo de recursos e localização.
Clique em "Revisar + Criar" e depois em "Criar" para provisionar o workspace.

Criar ou Carregar um Dataset:

Dentro do seu workspace do Azure Machine Learning, navegue até a seção "Datasets" e clique em "Criar dataset".
Selecione a fonte dos dados, que pode ser um arquivo local, um conjunto de dados em um armazenamento de dados do Azure ou um banco de dados.
Siga as instruções para carregar os dados e defina as configurações adequadas.

Preparar os Dados:

Use ferramentas como o Azure Machine Learning Data Prep para limpar e processar os dados conforme necessário.
Realize tarefas como tratamento de valores ausentes, normalização de dados e engenharia de recursos.

Escolher e Treinar um Modelo:

Navegue até a seção "Experimentos" e crie um novo experimento.
Selecione o tipo de algoritmo de machine learning que deseja utilizar e configure os hiperparâmetros.
Utilize o conjunto de dados preparado para treinar o modelo.
Acompanhe o progresso do treinamento e experimente diferentes configurações conforme necessário.

Avaliar o Modelo:

Após o treinamento, avalie o desempenho do modelo utilizando métricas relevantes, como precisão, recall, F1-score, etc.
Utilize visualizações e ferramentas disponíveis no Azure Machine Learning para entender melhor o desempenho do modelo.

Registrar o Modelo:

Após avaliação satisfatória, registre o modelo treinado no Azure Machine Learning para rastreamento e reutilização.
Isso permitirá que você versione o modelo, facilitando sua implantação e gerenciamento.

Configurar Pontos de Extremidade:

Implantar o Modelo:

No Azure Machine Learning Studio, navegue até o modelo treinado registrado.
Selecione "Implantar como Serviço Web" e siga as instruções para configurar a implantação do serviço web.

Configurar Pontos de Extremidade:

Após a implantação, obtenha a URL do ponto de extremidade do serviço web.
Configure as permissões de autenticação e autorização conforme necessário.
Defina as configurações de entrada e saída para o serviço web, especificando o formato das requisições e respostas.

Arquivo .json de Pontos de Extremidade:

```
{
  "prediction_endpoint": "https://sua-url-do-ponto-de-extremidade/predict",
  "authentication_key": "sua-chave-de-autenticação",
  "request_format": "formato-da-requisição (ex: JSON)",
  "response_format": "formato-da-resposta (ex: JSON)"
}
```

Neste arquivo JSON, deve substituir "https://sua-url-do-ponto-de-extremidade/predict" pela URL real do ponto de extremidade do seu modelo e "sua-chave-de-autenticação" pela chave de autenticação fornecida pelo Azure. Ajuste outros parâmetros conforme necessidade.


Teste-Modelo-de-Previsão-Azure
Neste README tem a explicação sobre a criação de um modelo Machine Learning no Microsoft Azure.
O modelo aqui descreito é sobre o número de aluguéis de bicicletas em determinado dia, com base em características sazonais e meteorológicas, com dados retirados diretamente da documentação.

1 PASSO: Criando Conta no Portal do Azure
Primeiro criei minha conta no Portal do Microsoft Azure
Azure
Acessando o serviço do Azure Machine-learning
Já dentro do Microsoft Azure fiz uma busca por "Machine Learning", aparecendo o serviço "Azure Machine Learning".

Configurando Modelos e Conjunto de Dados
Objetivo do Modelo
Aprendizado de máquina automatizado para previsão de aluguel de bicicletas.
Fonte de Dados
Capital Bikeshare
Passos
Dentro do serviço "Azure Machine Learning" foi criado um novo Recurso, com os campos preenchidos de acordo com modelo pedido pelo curso.

Após a criação do Recurso e todas as etapas cumpridas foi clicado no link que nos leva para outra página, chamado de "Lauch Studio". Este link nos leva para o Studio do Azure Machine Learning, aonde serão realizados os passos para criação do Modelo de Teste.

Após a criação de um "Novo trabalho de ML automatizado e inseridas as informações pedidas.

Foi utilizado neste projeto o modelo "Regressão", tratando-se de um modelo supervisionado de aprendizado de máquina. Posteriormente foi realizada as configurações de tarefas e selecionado modelo de computação conforme documentação.

Análise e teste de modelo
Terminado o trabalho automatizado de aprendizado de máquina, foi avaliado o melhor modelo treinado.

O próximo passo é implantar e testar o modelo seguindo os passos da documentação. Para isso será necessário modificar os dados de alguma linha de código em Python.

Código resultado do Teste apresentado abaixo:

```
{
  "Results": [
    376.75859636249595
  ]
}
```

Resultado
376 bicicleta alugadas em 1 dia.

Conclusão
Baseado no modelo de Machine Learning criado dentro o Azure, obtivemos o resultado de 376 biciletas alugadas em dia, de acordo com caracteristicas meteorológicas e dia escolhido.

Referências
Cloud Computing Dictionary
Documentação
ML Learn AI Fundamentals
