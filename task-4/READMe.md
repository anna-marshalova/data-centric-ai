# Модуль 4. Генерация данных

## Исзодный датасет и постановка задачи
Есть датасет для соревнования [LLM - Detect AI Generated Text](https://www.kaggle.com/competitions/llm-detect-ai-generated-text), 
содержащий эссе, написанные людьми. 
Задача - дополнить его сгенерированными текстами. 
В последствии на этих данных можно будет обучать модели для детекции сгенерированных текстов.

## Процесс генерации

Для генерации текстов использовалась большая языковая модель Claude от Anthropic.
Для обеспечения разнообразия сгенерированных текстов:
- В качестве первого слова использовались первые слова из оригинальных эсcе;
- Варьировались значения температуры.

См. шаблон промпта для модели в файле `template.txt`.  
Так было сгенерировано 755 текстов.

## EDA
Для сравнения человеческих и синтетических текстов был проведен EDA, 
похожий на тот, что проводился в первом задании.

### Вот какие выводы удалось получить:

- Сгенерированные тексты в среднем почти в 2 раза короче.
- Модель реже использует личные местоимения, особенно местоимение "we".
- Слова в сгенерированных текстах действительно в среднем длиннее.
- Предложения в сгенерированных текстах, наоборот, в среднем короче, 
а самих предложений меньше. В первом EDA такого не было.
- Дисперсия длин абзацев в сгенерированных текстах меньше.
- Случайные повторения одного и того же слова подряд встречаются почти исключительно только у людей.

Процесс генерации и EDA см. в ноутбуке  `dataset-generation.ipynb`.