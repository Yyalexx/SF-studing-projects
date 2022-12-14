# Проект 4. Задача классификации

## Описание проекта
Вам предоставили данные о последней маркетинговой кампании, которую проводил банк: задачей было привлечь клиентов для открытия депозита. Вы должны проанализировать эти данные, выявить закономерность и найти решающие факторы, повлиявшие на то, что клиент вложил деньги именно в этот банк. Если вы сможете это сделать, то поднимете доходы банка и поможете понять целевую аудиторию, которую необходимо привлекать путём рекламы и различных предложений.

КАКОЙ КЕЙС РЕШАЕМ?  
Задача бинарной классификации по табличным данным.  
Бизнес-задача: определить характеристики, по которым можно выявить клиентов, более склонных к открытию депозита в банке, и за счёт этого повысить результативность маркетинговой кампании.  
Техническая задача специалиста Data Science: построить модель машинного обучения, которая на основе предложенных характеристик клиента будет предсказывать, воспользуется он предложением об открытии депозита или нет.

## Этапы работы над проектом

1 . Первичная обработка данных  
2 . Разведывательный анализ данных (EDA)  
3 . Отбор и преобразование признаков  
4 . Решение задачи классификации: логистическая регрессия и решающие деревья  
5 . Решение задачи классификации: ансамбли моделей и построение прогноза


**Краткая информация о данных**  

*bank_fin.zip*, данные о последней маркетинговой кампании банка  
Ссылка для скачивания данных:  
https://drive.google.com/drive/folders/1POG-Izw0V9yVDSaLYeFlwplmiSVaL0x5?usp=sharing


**Результаты**  
Реализована задача классификации, на основе соответствующих метрик проведено сравнение эффективности различных моделей. Выявлены признаки с наибольшим влиянием на исход маркетинговой кампании. Обозначены возможные способы дальнейшего улучшения модели машинного обучения.

**Выводы**  

Проведена предобработка признаков. Простыми способами (медиана, мода) заменены пропущенные значения. Методом Тьюки удалены выбросы баланса.  
Проведен разведывательный анализ данных в контексте влияния на целевой признак.  
Проведено кодирование признаков и масштабирование значений. Не проводилась трансформация признаков к нормальному распределению.  
На основе корреляции Пирсона проведен анализ мультиколлинеарности.   
С помощью ANOVA F-value (f_classif) дана оценка влияния признаков на целевой признак, для построения моделей отобраны 15 наиболее значимых признаков.  
Построены простые базовые модели - логистическая регрессия и решающее дерево.  
Построены ансамблевые модели - случайный лес, градиентный бустинг на решающих деревьх, стекинг из деревьев, регрессии и бустинга.  
Реализованы примеры подбора гиперпараметров - поиск по сетке, Tree-structured Parzen estimator (в Optuna).  
На каждом этапе моделирования оценивались метрики качества классификации. Ансамблевые решения закономерно показывают лучшие значения. Какая либо качественная разница между ансамблевыми моделями на данном датасете не прослеживается. Подбор гиперпараметров модели случайного леса незначительно улучшил результат. 