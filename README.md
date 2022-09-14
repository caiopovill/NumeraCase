# NumecaCase

# 📘Abstrato
Como parte do processo seletivo, fiz uma análise dos datasets fornecidos para encontrar as melhores estratégias de vendas.

A princípio, recebi 3 conjuntos de dados! Como veremos mais abaixo, utilizei a função merge para unir os datasets a partir dos id's em comum.

Como não temos uma tentativa de prever um dado, não utilizarei modelos de machine learning, focarei apenas na análise exploratória de dados.

# 🔰Sobre este projeto
O principal deste projeto é apresentar os diferentes grupos e suas aderências aos canais de venda.

# 📖Informações do conjunto de dados

Os 3 datasets e suas colunas explicadas

![image](https://user-images.githubusercontent.com/105823082/189561449-c9023b4d-b604-48e4-9d8d-c68ebbd4eabc.png)

Depois de feito os joins entre os datasets, temos um dataset final!

Esses são os números de clientes femininos, masculinos e outros

![image](https://user-images.githubusercontent.com/105823082/189564431-6e222f2f-b3b5-4ccf-8931-6f3e1cb75bfe.png)

Gráfico de frequência de idade dos clientes

![image](https://user-images.githubusercontent.com/105823082/189565051-90f806e8-e6b3-440b-943c-c700925bc0c9.png)

Levando em conta esses 2 gráficos, excluí os dados de 'outros' e os clientes com 118, estou considerando que esses dados são erros por possuírem muitos valores nulos.

Boxplot com as colunas numéricas do dataset final

![image](https://user-images.githubusercontent.com/105823082/189566813-8afc1594-e0da-4187-87cd-8f695c5a924e.png)

![image](https://user-images.githubusercontent.com/105823082/189567114-3313c6f1-364d-4bde-bc2b-e086034ef6ef.png)

Com os boxplots a função describe podemos identificar as concentrações em cada feature. 50% da amostra de renda_anual está entre 45 mil e 80 mil, outro exemplo é a idade que 50 % da amostra está em torno de 41 e 66 anos

Separei os dados em classes para análisa-los separadamente. Os membros entre membros novos e antigos. Membros antigos se cadastraram antes de 2016 e membros novos de 2016 em diante. A renda anual em 3 grupos, A - 90000 mil ~ 120000 mil, B - 60000 mil ~ 90000 mil, C - 30000 ~ 60000. A idade em 3 classificações para mais tarde identificar quais canais de venda foram mais aceitos por cada faixa etária. Os dados foram divididos em --- novo : até 40 anos --- meia idade : 40 até 64 anos --- idoso : maior que 64 anos

Vamos entrar nos dados que interferem diretamente nas estratégias de negócio, existem 4 possíveis resultados das estratégias de venda. Irei focar apenas nos resultados que estão ligados aos canais de vendas, estou considerando que quando um tipo de de evento é transacao, significa que o cliente comprou sem ter sido exposto a qualquer tipo de propaganda.

![image](https://user-images.githubusercontent.com/105823082/189567660-f675f20e-0faf-482a-b017-155e7011d88c.png)

Existem 3 tipos de ofertas diferentes, primeiro vamos dividir cada tipo de oferta em 1 dataset, depois dividiremos esse dataset em cada canal de venda, para analisarmos qual tipo de canal funcionou melhor para cada tipo de oferta e seus respectivos públicos.

![image](https://user-images.githubusercontent.com/105823082/190246244-7361306d-9c16-42f1-9633-186002a69ae5.png)


Agora que já temos os resultados que analisaremos, vou dividir o dataset final nos 4 canais de vendas, para analisarmos os resultados de cada canal.

![image](https://user-images.githubusercontent.com/105823082/189568338-261ab3b0-6a71-4bbd-ac01-038d24ab3aab.png)


# Separando os dados apenas em ofertas informativas

## Por gênero

Classificação entre oferta recebida ou visualizada para cada tipo de canal de venda e os diferentes gêneros

![image](https://user-images.githubusercontent.com/105823082/190247950-1c050379-4410-46c7-997d-b93fe6d4e5c4.png)

A diferença entre gênero quanto a visualização de ofertas informativas são insignificantes, mas o canal web_email se mostrou muito mais eficiente para levar a informação até o consumidor.

## Renda anual

Classificação entre oferta recebida ou visualizada para cada tipo de canal de venda e os diferentes níveis de renda anual
Separando a renda anual em 3 grupos, A - 90000 mil ~ 120000 mil, B - 60000 mil ~ 90000 mil, C - 30000 ~ 60000 

![image](https://user-images.githubusercontent.com/105823082/190248248-76d60f0e-dc00-48f6-b263-14ebf0dda14f.png)

O único dado que chama um pouco atenção com a separação por renda anual é a classe C que visualiza menos ofertas pelo canal social_email, mas novamente o canal web_email se mostrou mais eficiente para levar a informação até o consumidor.

## Por idade

Classificação entre oferta recebida ou visualizada para cada tipo de canal de venda e as diferentes faixas etárias

![image](https://user-images.githubusercontent.com/105823082/190248970-0e823cd0-30bf-49a6-b724-4a708ab67fe8.png)

Um dado que chama a atenção é que pelo canal social_email os jovens visualizaram apenas 28% das ofertas, mas com o canal web_email eles foram os que mais visualizaram com 49%.

# Separando os dados apenas em ofertas que possuem desconto

## Por gênero

Classificação entre oferta recebida, visualizada ou concluída para cada tipo de canal de venda e os diferentes gêneros

![image](https://user-images.githubusercontent.com/105823082/190249238-5b94c2cc-9570-4bc5-acfd-99d7d2a398fe.png)

Os resultados entre feminino e masculino nas ofertas de desconto foram muito semelhantes, nos 3 canais o publico feminino teve mais maior % de ofertas concluídas

## Por idade

Classificação entre oferta recebida, visualizada ou concluída para cada tipo de canal de venda e as diferentes faixas etárias

![image](https://user-images.githubusercontent.com/105823082/190249464-20e69256-54fa-4ad4-8480-9a5a7defa274.png)

O público mais jovem foi o que teve menos ofertas concluídas entre as 3 idades.

## Renda anual

Classificação entre oferta recebida ou visualizada para cada tipo de canal de venda e os diferentes níveis de renda anual
Separando a renda anual em 3 grupos, A - 90000 mil ~ 120000 mil, B - 60000 mil ~ 90000 mil, C - 30000 ~ 60000 

![image](https://user-images.githubusercontent.com/105823082/190250246-58abb3ba-14c7-4498-83cd-16597f22e458.png)

Os resultados entre as diferentes rendas nas ofertas de desconto foram muito semelhantes, nos 3 canais a classe A foi a que mais concluiu ofertas.

# Separando os dados apenas em ofertas que possuem a oferta Compre 1 Leve 2

## Por gênero

Classificação entre oferta recebida, visualizada ou concluída para cada tipo de canal de venda e os diferentes gêneros

![image](https://user-images.githubusercontent.com/105823082/190250831-e164f6ed-72e5-45b1-8348-2a410f4c0dbc.png)

Nos 4 possíveis canais de venda, as mulherem tiveram mais ofertas concluídas do que os homens, o canal web_email teve a maior discrepância entre os gêneros, 7% de diferença.

## Por idade

Classificação entre oferta recebida, visualizada ou concluída para cada tipo de canal de venda e as diferentes faixas etárias

![image](https://user-images.githubusercontent.com/105823082/190250991-533f4a4a-47af-4bc5-819d-57b5eae40a0e.png)

A classe meia_idade e idoso apresentaram os niveis muito semelhantes entre os 3 canais, porém o público mais novo apresentou um grande aumento de % em ofertas concluídas no canal web_email_mobile

## Renda anual

Classificação entre oferta recebida ou visualizada para cada tipo de canal de venda e os diferentes níveis de renda anual
Separando a renda anual em 3 grupos, A - 90000 mil ~ 120000 mil, B - 60000 mil ~ 90000 mil, C - 30000 ~ 60000 

![image](https://user-images.githubusercontent.com/105823082/190251635-a9e9151c-192a-447b-bce4-568e09492a4e.png)

A classe B não apresentou diferença entre os tipos de canais. a classe C teve uma maior aderência no canal web_email_mobile_social, enquanto a classe A tem a maior aderência no canal email_mobile_social.
