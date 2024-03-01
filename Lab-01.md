Desafio de projeto:

Para esse desafio de projeto foi fornecido a documentação a ser seguida:

https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/02-content-safety.html

https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html

Esse Readme é para listar o passo a passo desde a criação da conta Azure, até a análise do ponto de extremidade.

Passo 1:

Criar a conta na Azure.

Ao entrar na Azure, selecione para criar a conta gratuita. Preenche todos os dados solicitados e conclui.

Passo 2:

Criar um recurso.

No canto superior esquerdo da tela, selecionamos criar um recurso. Lá buscamos por Machine Learning.

Selecione Azure Machine Learning.

Clique em Criar.

Em subscription/ assinatura, você deixa como está.

Em Resource Group, grupo de recursos, criar um novo e escolher o nome.

Em workspace, vá preenchendo conforme solicitado. Name, storage account, application, etc, mantendo o que está sendo criado no momento.

Após conferir tudo, clique em create/ criar.

Passo 3:

Após a implantação concluida, vá em go to resource/ ir para recursos.

No final da tela, clique em ir para o estúdio.

Na barra da esquerda, selecione ML Automatizado.

Clique em novo trabalho de ML Automatizado.

Preencha os dados conforme a documentação

Nome de trabalho, nome do experimento, descrição, etc, tudo conforme a descrição da documentação.

Avanço para próxima tela.

Tipo de tarefa, regressão.

Em selecionar dados, vá em criar.

O nome alugueldebicicletas

descrição dados históricos de aluguel de bicicletas

Tipo, Tabular. Verificar se colocou o tipo correto, senão não encontra as próximas etapas corretamente como descritas.

Na próxima tela, selecione de arquivos da web

Preencha a URL: https://aka.ms/bike-rentals

Os dados são todos retirados da documentação.

Avançar, conferir campo a campo:

Formato do arquivo: Delimitado

Delimitador: Vírgula

Codificação: UTF-8

Cabeçalhos: Somente o primeiro arquivo tem cabeçalhos

Ignorar linhas: nenhuma.

Após carregamento dos dados clique em Avançar.

Clique em avançar novamente.

Finalmente clique em criar

Passo 4:

Após carregamento, selecione aluguel de bicicletas e clique em avançar.

Agora é hora de preencher as configurações de tarefas.

Em coluna de destino, coloque rentals

Clique em exibir definições de configurações adicionais

Selecione NormalizedRootMeanSquaredError

Desmarcar as 3 caixinhas

Modelos permitidos: Random E light

Salvar

Em limites:

Maximo de avaliações: 3

Maximo de avaliações simultaneas: 3

Maximo de nós: 3

Limite de pontuaçãi da métrica: 0.085

Tempo limite de experimento: 15

Tempo limite de interação: 15

Habilitar o encerrmento antecipado

Tipo de validação: Validação de treinamento

Auto preenche para 10

Dados de teste: nenhum

Passo 5:

Em Computação:

Sem servidor

Tipo de máquina CPU

Tipo de máquina virtual: Dedicado

Tamanho: Standard_DS3_v2

Número de instâncias: 1

Clica em avançar

Enviar trabalho de treinamento

Aguardar concluir.

Passo 6:

Na guia Visão geral observe o melhor resumo no canto direito.

Selecione em nome do algoritmo, vá em métricas, selecione os gráficos residuais e predito_true.

Passo 7:

Na guia modelo, selecione Implantar, serviço web

Preencher conforme documentação:

Nome: prever-aluguéis

descrição: prever aluguel de bicicletas

tipo de computação: Instância de contêiner do azure

Habilitar autenticação: selecionado

Aguarde até que o status de implementação mude para succeedes. Em média 5 a 10 minutos.

Passo 8:

No menu esquerdo, selecione Endpoints, e abra o ponto final de tempo real de previsão de alugueis.

Visualiza a guia Teste.

No painel Dados de entrada para testar o endpoint, substitua o modelo JSON para:

```
{
   "Inputs": { 
     "data": [

{

"day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3

}

]

},

"GlobalParameters": 1.0

}
```



Clique em testar.

Revise o resultado do teste.

O resultado do teste gerou o seguinte JSON:


```
{
"Results": [
361.95238671338427
]
}
```

O resultado é que a previsão do número de aluguel em determinado dia é de 361 unidades.
