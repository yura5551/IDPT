# Запуск и сборка контейнера
## Сборка
	sudo docker build -t lr1-img:2.0 .
## Запуск 
	sudo docker run lr1-img:2.0



# Проверка правил и фактов

## Генерация правил
Изначально правила генерируются для 4-х случаев 
	1)simple; 
	2)random;
	3)ring;
	4)stairway.
Затем отдельно проверяются факты
Функция проверки фактов evidence_check:

Cоздается список result в котором хранятся результаты правил по проверенным фактам
Для каждого типа правил создается список в составе списка s_list, далее в эти списки заносятся соответвующие правила.
## Проверка фактов ## 
	Правила "AND": 
		 1) Если элемент находится в фактах, то увеличиваем значение итератора на 1;
		 2) После итерации сравнением итератор с длинной правила;
		 3) Если значения равны то результат сохраняется в список result.
	Правила "OR":  
		 1) Проверка до первого вхождения; 
		 2) Аналогично с "AND";
		 3) При нахождении первого вхождения break. 
	Правила "NOT": 
		 1) Аналогично с "AND".
	
## Результат
	В список result добавляется результат выполнения правила, в противном случае 0.

## Время
Полученное время для соответсвующего алгоритма вне контейнера: 29c.
В контейнере: 63с.
## Характеристики аппартаных ресурсов
![Характеристики аппартаных ресурсов](https://github.com/Ichail/IDPT/blob/main/MyPC.png)

