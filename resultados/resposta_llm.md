## 1. Principais padrões

* **Predomínio e separação por cilindros:** A base de 398 registros concentra-se em carros de 4 cilindros (204) e 8 cilindros (103). A quantidade de cilindros dita fortemente a proximidade técnica: a chance de o vizinho mais próximo ter o mesmo número de cilindros é de 98,5%.
* **Diferenças marcantes por origem:** Os modelos dos EUA têm maior peso médio (1525 kg), maior potência média (118,48 hp) e menor rendimento (8,54 km/l), concentrando 41,37% de motores de 8 cilindros. Em contrapartida, os veículos do Japão e da Europa são mais leves (1008 kg e 1099 kg) e mais econômicos (12,95 km/l e 11,86 km/l), sem nenhum modelo de 8 cilindros.
* **Evolução do consumo ao longo dos anos:** O rendimento médio aumentou de forma consistente no período analisado, saindo de 7,52 km/l em 1970 para 13,48 km/l em 1982 (com pico de 14,33 km/l em 1980).
* **Convergência entre montadoras:** Em 74,9% dos casos, o modelo mais parecido pertence à mesma região de origem, mas apenas em 17,8% pertence à mesma marca, indicando que fabricantes diferentes desenvolviam veículos com fichas técnicas quase idênticas.

---

## 2. Carros mais semelhantes

Os pares com menor distância Euclidiana reúnem modelos do mesmo ano (fato presente em 56,0% dos vizinhos mais próximos) e com a mesma contagem de cilindros. O par mais próximo de toda a base é formado por **chevrolet chevette (78)** (EUA) e **honda accord lx (78)** (Japão), com distância de apenas 0,08. Ambos possuem 4 cilindros, exatamente 68 hp de potência, pesos quase idênticos (977 kg vs. 968 kg), acelerações muito próximas (16,5 s vs. 16,6 s) e consumos semelhantes (12,75 km/l vs. 12,54 km/l). 

Outros exemplos incluem **volkswagen jetta (81)** e **honda prelude (81)** (distância 0,12), além de **mazda glc 4 (81)** e **ford escort 4w (81)** (distância 0,15). Isso indica que, ao projetar veículos para atender a uma mesma categoria e período, montadoras de origens distintas convergiram para especificações praticamente espelhadas (como hipótese, para disputar o mesmo perfil de consumidor no mercado).

---

## 3. Casos atípicos

Adotando o critério de consenso (apontados por ao menos 2 métodos), foram detectados **16 carros atípicos**, segmentados em dois grupos principais:

* **Atípicos potentes (13 carros):** Formado quase exclusivamente por modelos norte-americanos do início da década de 1970 com motores V8 (como buick electra 225 custom 1973, chevrolet impala 1970 e pontiac grand prix 1973). Em comparação com os veículos típicos, eles apresentam média de potência de 207,0 hp (contra 100,99 hp dos típicos), peso médio de 1892,21 kg (contra 1330,31 kg), aceleração média rápida de 11,04 s (contra 15,65 s) e consumo muito mais elevado, registrando 5,89 km/l (contra 10,09 km/l dos típicos). O bmw 2002 (70) também se destaca nesse grupo devido à sua elevada relação potência/peso (111,51 hp/tonelada para um veículo de 4 cilindros).
* **Atípicos fracos/lentos (3 carros):** Formado por vw dasher diesel (80), vw pickup (82) e peugeot 504 (79). Caracterizam-se por acelerações muito lentas (média de 24,37 s de 0 a 60 mph), potência reduzida (média de 57,0 hp) e relação hp/tonelada de apenas 49,4, embora atinjam um rendimento favorável de 16,24 km/l.
* **Observação de qualidade dos dados:** O modelo **buick estate wagon (sw) (70)** foi apontado pelos 3 métodos como atípico, exibindo uma relação atípica de 160,74 hp/tonelada devido a 225 hp e peso registrado de 1400 kg (3086 lb). O resumo aponta que outras peruas de 8 cilindros do mesmo período (1971-1972) pesam entre 3892 e 5140 lb, o que indica que esse peso provavelmente foi registrado com erro na base de dados original.

---

## 4. Concordância entre os métodos de outliers

A concordância entre os três métodos aplicados (IQR, Z-score e Isolation Forest) variou conforme o rigor de cada algoritmo:
* **Z-score (> 3):** Foi o mais conservador, identificando apenas 7 carros ao todo (5 em potência, 2 em aceleração e 2 em hp/tonelada).
* **IQR e Isolation Forest (contamination = 0,05):** Ambos identificaram 20 carros cada.
* **Concordância geral:** A grande maioria dos dados (373 carros) não foi considerada atípica por nenhum método. Dos modelos sinalizados, 9 foram acusados por apenas 1 método, 10 por 2 métodos e 6 carros foram rotulados simultaneamente pelos 3 métodos.

---

## 5. Resumo executivo

A análise de 398 veículos mostrou que número de cilindros e ano de fabricação governam a semelhança técnica, gerando modelos quase idênticos entre marcas de diferentes continentes. Foram identificados 16 veículos atípicos, divididos entre modelos V8 norte-americanos do início dos anos 1970 (altíssimo peso e potência) e modelos europeus de aceleração extremamente lenta. Detectou-se também provável erro de registro no peso da perua Buick Estate Wagon (1970).

---

## 6. Perguntas adicionais

1. **Qual o impacto do provável erro de peso da Buick Estate Wagon (1970)?** Caso o peso seja corrigido para a faixa das outras peruas (entre 3892 e 5140 lb), o modelo ainda seria apontado como atípico pelos métodos multivariados?
2. **Existe correlação entre o tipo de combustível e a lentidão dos atípicos europeus?** Como a base registra versões diesel (ex.: VW Dasher), seria útil verificar se a baixa aceleração é comum a todos os veículos a diesel da base (informação não detalhada para os demais carros no resumo).
3. **Quais foram as 9 variáveis/modelos apontados por apenas 1 método de outlier?** Investigar por que houve discordância entre Isolation Forest e IQR nesses 9 casos específicos ajudaria a calibrar melhor a detecção de anomalias.