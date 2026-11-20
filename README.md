# Perfis de veículos: carros semelhantes e casos atípicos de consumo e desempenho

Projeto Final Individual — Mineração de Dados com apoio de LLM via API
João Vitor Rossi Ferreira — 6º Semestre DSM — Fatec São José dos Campos

**Pergunta:** quais carros apresentam perfis técnicos mais semelhantes entre si, quais se afastam do comportamento geral e o que caracteriza esses casos atípicos?

## Como executar

1. Abra `projeto_final_auto_mpg.ipynb` no VS Code (ou Jupyter) com Python 3.10 ou mais novo.
2. Clique em **Run All** (Executar Tudo).

A primeira célula instala sozinha as bibliotecas que estiverem faltando. Se preferir instalar antes: `pip install -r requirements.txt`.

Não precisa de chave de API nem de internet: o dataset está em `data/` e a resposta do Gemini já está salva em `resultados/resposta_llm.md` (o notebook reaproveita essa resposta, que é a que foi avaliada no trabalho). Para chamar a API de novo, defina a variável de ambiente `GEMINI_API_KEY` e mude `REEXECUTAR_LLM = True` na seção 9. A chave nunca fica no código.

## Estrutura

| Arquivo / pasta | Conteúdo |
|---|---|
| `projeto_final_auto_mpg.ipynb` | Notebook com todo o processo (preparação → distância → outliers → resumo → LLM → verificação → conclusão) |
| `data/auto_mpg.csv` | Dataset Auto MPG (UCI) convertido para CSV — https://archive.ics.uci.edu/dataset/9/auto+mpg |
| `resultados/*.csv` | Tabelas geradas (pares semelhantes, atípicos, comparações) |
| `resultados/figuras/` | Gráficos |
| `resultados/resumo_para_llm.json` | Único conteúdo enviado à LLM (resultados agregados) |
| `resultados/prompt_llm.txt` | Prompt completo enviado |
| `resultados/resposta_llm.md` | Resposta do Gemini (`gemini-3.8-flash`) |
