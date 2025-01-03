# ai_learning

## Структура

Все лабораторные работы находятся в соответствующих папках.

## Итоги сравнения нескольких методов обучения и прогнозирования для решения задачи классификации виновников с помощью алгоритмов машинного обучения.

| Алгоритм                   | Задача               | Метрика          | Бейзлайн | Улучшенный бейзлайн | Самостоятельная имплементация алгоритма | Улучшенная самостоятельная имплементация алгоритма |
|----------------------------|----------------------|------------------|----------|---------------------|-----------------------------------------|----------------------------------------------------|
| KNN                        | классификация        | Accuracy:        | 0.85625  | 0.90937             | 0.85                                    | 0.88125                                            |
|                            |                      | F1-score:        | 0.30303  | 0.67415             | 0.4                                     | 0.51282                                            |
|                            | регрессия            | R-squared (R^2): | 0.18592  | 0.44239             | 0.12810                                 | 0.33455                                            |
| Линейные модели            | классификация        | Accuracy:        | 0.85937  | 0.86562             | 0.8625                                  | 0.8625                                             |
|                            |                      | F1-score:        | 0.32835  | 0.37681             | 0.3125                                  | 0.3125                                             |
|                            | регрессия            | R-squared (R^2): | 0.40318  | 0.40316             | 0.40338                                 | 0.40338                                            |
| Решающее дерево            | классификация        | Accuracy:        | 0.87187  | 0.87812             | 0.88437                                 | 0.87812                                            |
|                            |                      | F1-score:        | 0.53932  | 0.55172             | 0.60215                                 | 0.58947                                            |
|                            | регрессия            | R-squared (R^2): | 0.07231  | 0.34412             | 0.37374                                 | 0.36566                                            |
|     Случайный лес          |     классификация    | Accuracy:        | 0.9      | 0.9125              | 0.86562                                 | 0.84687                                            |
|                            |                      | F1-score:        | 0.6      | 0.65                | 0.53763                                 | 0.46153                                            |
|                            |     регрессия        | R-squared (R^2): | 0.53904  | 0.53140             | 0.33535                                 | 0.22374                                            |
|     Градиентный бустинг    |     классификация    | Accuracy:        | 0.87187  | 0.87812             | 0.89687                                 | 0.89687                                            |
|                            |                      | F1-score:        | 0.48101  | 0.51851             | 0.62921                                 | 0.60240                                            |
|                            |     регрессия        | R-squared (R^2): | 0.44638  | 0.45180             | 0.47594                                 | 0.45288                                            |

Общий вывод по всем методам
Анализ показал, что результаты сильно зависят от типа задачи (классификация или регрессия), используемого алгоритма, а также степени улучшений и оптимизации.

- Для задач классификации лучшими показателями по метрике Accuracy обладают случайный лес и градиентный бустинг. Однако по метрике F1-score, которая более чувствительна к несбалансированным данным, решающее дерево и градиентный бустинг демонстрируют более стабильные результаты.
- Для задач регрессии наибольшая объясняющая способность данных (R-squared) достигается при использовании cлучайного леса, хотя улучшение по сравнению с бейзлайном относительно невелико.
Улучшение моделей (внедрение модификаций) часто давало положительный эффект, но его масштаб варьировался в зависимости от алгоритма. В некоторых случаях самостоятельная имплементация уступала улучшенным базовым реализациям.

Выводы по каждому методу
1. KNN (k-ближайших соседей)

Классификация: Улучшенный бейзлайн показал значительное повышение Accuracy (с 0.856 до 0.909), а F1-score увеличился почти вдвое. Самостоятельные реализации уступают, что может быть связано с менее оптимальной настройкой гиперпараметров.

Регрессия: Модель показала наименее высокие значения R-squared среди всех алгоритмов, даже после улучшений. Это говорит о слабой способности метода KNN к обобщению в задачах регрессии.

2. Линейные модели

Классификация: Результаты практически не изменились после улучшений. Это может указывать на ограниченность линейных моделей в решении данной задачи, вероятно из-за нелинейности данных.

Регрессия: R-squared стабильно около 0.4, что свидетельствует об умеренной способности линейных моделей объяснять дисперсию данных. Улучшения не привели к значимым изменениям.

3. Решающее дерево

Классификация: Демонстрирует хорошие результаты по Accuracy и F1-score. Улучшения дали прирост метрик, но незначительный.

Регрессия: Несмотря на улучшения, R-squared остается сравнительно низким, что указывает на склонность модели к переобучению и ограниченную обобщающую способность.

4. Случайный лес

Классификация: Высокие результаты по Accuracy (до 0.9125), но F1-score оказался ниже, что может быть связано с несбалансированностью данных. Самостоятельная реализация уступает улучшенным базовым подходам.

Регрессия: Хорошее начальное значение R-squared (0.539), однако оптимизация дала слабый прирост или даже ухудшение результатов. Это может указывать на недостаточную настройку параметров.

5. Градиентный бустинг

Классификация: Совмещает высокую Accuracy (0.878) и лучший F1-score (0.629 в улучшенной версии), что делает его предпочтительным выбором для задачи классификации.

Регрессия: R-squared выше, чем у других алгоритмов (до 0.475), что делает его наиболее подходящим для регрессионного анализа. Однако эффект улучшений минимален.

#### Итоговый выбор

Для классификации: Градиентный бустинг из-за баланса между Accuracy и F1-score.

Для регрессии: Случайный лес как наиболее точная модель по R-squared, хотя выигрыш от оптимизаций ограничен.