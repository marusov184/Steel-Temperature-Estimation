# Промышленность — задача проекта

Чтобы оптимизировать производственные расходы, металлургический комбинат ООО «Так закаляем сталь» решил уменьшить потребление электроэнергии на этапе обработки стали. Вам предстоит построить модель, которая предскажет температуру стали.


## Описание данных

Данные состоят из файлов, полученных из разных источников:

- `data_arc.csv` — данные об электродах;
- `data_bulk.csv` — данные о подаче сыпучих материалов (объём);
- `data_bulk_time.csv` *—* данные о подаче сыпучих материалов (время);
- `data_gas.csv` — данные о продувке сплава газом;
- `data_temp.csv` — результаты измерения температуры;
- `data_wire.csv` — данные о проволочных материалах (объём);
- `data_wire_time.csv` — данные о проволочных материалах (время).

Во всех файлах столбец `key` содержит номер партии. В файлах может быть несколько строк с одинаковым значением `key`: они соответствуют разным итерациям обработки.

## Вывод

После всех необходимых этапов предобработки данных, было рассмотрено три модели: дерево решений, градиентный бустинг и случайный лес. Наилучшей моделью является модель случайного леса со значением MAE на тестовой выборке 5.755. Также была оценена важность независимых переменных  Наиболее важными признаками являются изначальная температура и суммарная работа каждой отдельной парти, причем оба признака одинаково важны. К остальным значимым признакам можно отнести объем материала wire1, газа и Bulk15. Соответственно, бизнес в большей степени может управлять этими тремя показателями и тем самым влиять на конечную температуру и уменьшить потребление электроэнергии. 