# Компьютерная модель падения бутерброда
<p align="center">
  <img src="./cat.png" width="300px"/>
</p>
С каждым время от времени происходят неприятные ситуации. Однако если неудачных дней становится слишком много, человек начинает верить в различные теории заговора или, например, общепринятые законы. В частности наиболее известным философским принципом является закон Мёрфи, который гласит:
> Если что-нибудь может пойти не так, оно пойдёт не так.

Физический объект, компьютерная модель которого была разработана в рамках данного проекта, – бутерброд с маслом, падающий со стола на пол. Согласно распространенному мнению бутерброд всегда будет падать маслом вниз. При помощи физических законов и средств вычислительной математики было установлено, является ли данное утверждение истинным и при каких условиях бутерброд упадет на ребро.

## Цель моделирования
Определить конкретные параметры, при которых бутерброд может упасть на ребро.

## Описание модели
<p align="center">
  <img src="./model.png"/>
</p>

**Стол**
- горизонтальная поверхность, находящаяся на некотором уровне над полом
- обладает статическим и кинетическим трением

**Бутерброд**
- прямоугольное тело (пренебрегаем шириной и толщиной)
- абсолютно твердое (пренебрегаем распределением плотности и деформацией)
- центр масс выступает за край стола
- совершает вращательное движение
- при столкновении с полом происходит неупругий удар (бутерброд неотскакивает)

## Моделирование
Симуляция движения бутерброда осуществлялась при помощи вычисления физических формул, описывающих динамику рассматриваемого объекта с входными параметрами. В процессе моделирования необходимо было решить задачу Коши. Решение  было найдено с помощью метода Рунге-Кутты, который используется при вызове функции solve_ivp(). Для решения уравнений использовался метод fsolve библиотеки scipy, предназначенной для выполнения научных и инженерных расчётов. В основе данного метода лежит модификация гибридного метода Пауэлла.

<p align="center">
  <img src="./formulas.png"/>
</p>

## Обратная задача
<p align="center">
  <img src="./task.png" width="500px"/>
</p>
Для достижения цели нашей работы нам необходимо было решить обратную задачу, которая заключается в минимизации разницы искомого угла, под которым бутерброд упадет на ребро и значения целевой функции. Также для ускорения сходимости этой функции ее значение возводится в квадрат. Минимизация была осуществлена с помощью метода градиентного спуска.

## Оценка сходства
Для оценки качества модели было произведено сравнение полученных данных с экспериментальными данными из [статьи](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=26a061e77c4a30dbf59db13f557b4598f497e066). В результате был получен график зависимости угла, под которым падает бутерброд, от выступа. Значения выступов для заданных углов совпали с данными из таблицы в статье, что подтвердило качество разработанной модели.

<p align="center">
  <img src="./quality.png"/>
</p>

## Итоги
Для реализации проекта необходимо было освежить в памяти физические законы и математическую теорию, познакомиться с методами решения численных задач и научиться использовать Python библиотеки для инженерных вычислений и построения графиков. Было трудно, однако в ходе работы мы получили много положительных эмоций и смогли решить поставленную задачу.

## Авторы
Над проектом трудились студентки 3 курса ФИТ НГУ:
* Анна Воронова
* Алина Гусельникова
