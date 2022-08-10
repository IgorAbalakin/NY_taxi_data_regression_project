# PROJECT-5. Задача регрессии 

### Оглавление 
[1. Описание проекта](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Описание-проекта) 

[2. Первичная обработка данных](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Первичная-обработка-данных) 

[3. Разведывательный анализ данных](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Разведывательный-анализ-данных) 

[4. Отбор и преобразование признаков](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Отбор-и-преобразование-признаков) 

[5. Решение задачи регрессии: линейная регрессия и деревья решений](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Решение-задачи-регрессии-линейная-регрессия-и-деревья-решений) 

[6. Решение задачи регрессии: ансамблевые методы и построение прогноза](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Решение-задачи-регрессии-ансамблевые-методы-и-построение-прогноза) 
 
____
### Описание проекта 

Известно, что стоимость такси в США рассчитывается на основе фиксированной ставки и тарифной стоимости, величина которой зависит от времени и расстояния. Тарифы варьируются в зависимости от города.

В свою очередь, время поездки зависит от множества факторов, таких как направление поездки, время суток, погодные условия и так далее.

Таким образом, если разработать алгоритм, способный определять длительность поездки, можно будет прогнозировать её стоимость самым тривиальным образом, например, просто умножая стоимость на заданный тариф. 

Сервисы такси хранят огромные объёмы информации о поездках, включая такие данные, как конечная и начальная точки маршрута, дата поездки и её продолжительность. Эти данные можно использовать для того, чтобы прогнозировать длительность поездки в автоматическом режиме с привлечением искусственного интеллекта.

*Бизнес-задача:* определить характеристики и с их помощью спрогнозировать длительность поездки на такси.

*Техническая задача*: построить модель машинного обучения, которая на основе предложенных характеристик клиента будет предсказывать числовой признак — время поездки такси, то есть решить задачу регрессии.
 
:arrow_up: [к оглавлению](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Оглавление)

 ____
### Первичная обработка данных

Данные о клиенте и таксопарке:

        id — уникальный идентификатор поездки;
        vendor_id — уникальный идентификатор поставщика услуг (таксопарка), связанного с записью поездки.

Временные характеристики:

        pickup_datetime — дата и время, когда был включён счётчик поездки;
        dropoff_datetime — дата и время, когда счётчик был отключён.

Географическая информация:

        pickup_longitude — долгота, на которой был включён счётчик;
        pickup_latitude — широта, на которой был включён счётчик;
        dropoff_longitude — долгота, на которой счётчик был отключён;
        dropoff_latitude — широта, на которой счётчик был отключён.

Прочие признаки:

        passenger_count — количество пассажиров в транспортном средстве (введённое водителем значение);
        store_and_fwd_flag — флаг, который указывает, сохранилась ли запись о поездке в памяти транспортного средства перед отправкой поставщику (Y — хранить и пересылать, N — не хранить и не пересылать поездку).

Целевой признак:

        trip_duration — продолжительность поездки в секундах.


:arrow_up: [к оглавлению](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Оглавление)

____
### Разведывательный анализ данных

В данной части проекта необходимо выполнить:

        - исследование данные;
        - поиск закономерностей, позволяющих сформулировать предварительные гипотезы относительно того, какие факторы являются решающими для оформления депозита;
        - построение визуализаций, иллюстрирующих исследование.



:arrow_up: [к оглавлению](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Оглавление)

 ____
### Отбор и преобразование признаков

Перед построением модели необходимо выполнить следующие шаги:

        1. Многие алгоритмы машинного обучения не могут обрабатывать категориальные признаки в их обычном виде. Поэтому нам необходимо их закодировать.
        2. МНеобходимо масштабировать и трансформировать некоторые признаки для того, чтобы улучшить сходимость моделей, в основе которых лежат численные методы.
        3. Отобрать признаки, которые для использования для обучения модели.


:arrow_up: [к оглавлению](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Оглавление)
 
____
### Решение задачи регрессии: линейная регрессия и деревья решений

В данной части проекта необходимо выполнить:

        1. Построить модель линейной регрессии на обучающей выборке.
        2. Сгенерировать полиномиальные признаки второй степени с помощью PolynomialFeatures из библиотеки sklearn. Построить модель полиномиальной регрессии второй степени на обучающей выборке.
        - построение визуализаций, иллюстрирующих исследование.
        3. Построить модель полиномиальной регрессиивторой степени с L2-регуляризацией (регуляризацией по Тихонову) на обучающей выборке ( Коэффициент регуляризации установить равным 1, остальные параметры оставить по умолчанию.
        4. Построить модель дерева решений (DecisionTreeRegressor) на обучающей выборке.

:arrow_up: [к оглавлению](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Оглавление)
 
____
### Решение задачи регрессии: ансамблевые методы и построение прогноза

1. Построить модель случайного леса на обучающей выборке. В качестве гиперпараметров укажем следующие:

        n_estimators = 200;
        max_depth = 12;
        criterion = 'squared_error';
        min_samples_split = 20;
        random_state = 42.

2. Построить модель градиентного бустинга над деревьями решений (GradientBoostingRegressor) на обучающей выборке. В качестве гиперпараметров укажем следующие:

        learning_rate = 0.5;
        n_estimators = 100;
        max_depth = 6;
        min_samples_split = 30;
        random_state = 42.

3. Для лучшей из построенных моделей рассчитать медианную абсолютную ошибку (MeAE, в sklearn — функция median_absolute_error) предсказания длительности поездки такси на валидационной выборке.

:arrow_up: [к оглавлению](https://github.com/IgorAbalakin/NY_taxi_data_regression_project/blob/main/README.md#Оглавление)
  ____
