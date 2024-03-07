# Задача
Стояла задача разработать алгоритм, который для всех товаров из validation.csv предложит несколько вариантов наиболее похожих товаров из base, а затем
оценить качество алгоритма по метрике accuracy@5.

# Данные
base.csv - анонимизированный набор товаров. Каждый товар представлен как уникальный id (0-base, 1-base, 2-base) и вектор признаков размерностью 72.
train.csv - обучающий датасет. Каждая строчка - один товар, для которого известен уникальный id (0-query, 1-query, …) , вектор признаков И id товара из base.csv, который максимально похож на него (по мнению экспертов).
validation.csv - датасет с товарами (уникальный id и вектор признаков), для которых надо найти наиболее близкие товары из base.csv
validation_answer.csv - правильные ответы к предыдущему файлу.

# Вывод
Был использован индекс Faiss с инвертированным индексом и векторными фильтрами (IVF).
Предварительно признаки были масштабированы, удалены пропуски.
Accuracy@5 на обучающей и валидационной выборках - 21%. Полученные результаты показывают, что модель предсказывает наиболее похожих соседей для примерно каждого пятого товара из обучающей и валидационной выборок.
