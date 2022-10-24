Виртуальная стажировка Сбер.

Вводные данные задачи:

В файле data.csv (находится в архиве "Вспомогательный данные") представлены подневные данные объема расчетных счетов физических лиц. В отличие от депозита, клиент может снять всю сумму с расчетного счета в любой момент времени без каких-либо «штрафов». Такой продукт называют Undefined Maturity Product – UMP). Однако маловероятно, что все клиенты разом закроют свои счета в Банке. Всегда кто-то снимает деньги, а кто-то пополняет счет – есть некоторый стабильный уровень, ниже которого не опустится суммарный обьем расчетных счетов.

Например, если бы мы знали будущее объема расчетных счетов, как на рисунке 1, то стабильная часть на 1 месяц (1м) была бы на уровне, обозначенным красным цветом. Это тот уровень, который не пробивается на протяжении 1 месяца. Аналогично 2м – зеленый, 3м – синий, 4м – розовый.

<img width="1331" alt="Рисунок 1" src="https://user-images.githubusercontent.com/101212758/197534237-8f1c76f4-f071-4c09-9ee4-57e9df98dc7d.png">

Описание задачи:

Для временного ряда в файле data.csv необходимо построить модель, которая оценивает обьем стабильной части средств на дату. 

Например:
model_forecast (2019-02-01, ‘1М’, История_до_2019-02-01) = стабильная часть на 1М

Возможные горизонты: 1М, 2М, 3М, 4М, 5М, 6М, 7М, 8М, 9М, 10М, 11М, 12М

Критерии качества модели:
Нужно одновременно минимизировать величины:
максимальный объем пробития стабильный части на валидационной выборке 
фактическая стабильная часть – модельная стабильная часть 

Можно применять любые подходы. Как вариант: построить квантильную регрессию для прогнозирования ряда.
