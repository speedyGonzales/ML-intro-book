# ML-intro-book
## Matplotlib

Библиотека на Python за създаване на графики и диаграми. 

### Как да я извикаме:
```python
from matplotlib import pyplot as plt
Как да я извикаме:
```
### Плотиране на линейна графика:
Как да я извикаме:
```python
x_values = [0, 1, 2, 3, 4]#списък със стойностите на x координатите на точките
y_values = [0, 1, 4, 9, 16]#списък със стойностите на y координатите на точките
plt.plot(x_values, y_values)# plt - синонима, който сме дали на Matplotlib модула
plt.show()# ще покаже графиката
```
### Сравняване на две линейни графики: 
```python
from matplotlib import pyplot as plt

time = [0, 1, 2, 3, 4]
revenue = [200, 400, 650, 800, 850]
costs = [150, 500, 550, 550, 560]

plt.plot(time, revenue)
plt.plot(time, costs)
plt.show()
```
### Параметри на Plot функцията: 

- linestyle - '--',':', ''  # Стил на плотираната линия
- marker - 'o'(кръгче), 's'(квадратче), '*'(звездичка) # Стил на маркера за стойност
- color -'green','purple', '#AAAAAA', #82edc9 # Цвят на плотираната линия

### Координатни линии и етикети:
```python
plt.xlabel('Етикет по абцисата')
plt.ylabel('Етикет по ординатата')
plt.title('Заглавие на плотираната графика')
```
- x1- начално число на абцисната ос
- x2- крайно число на абцисната ос
- y1- начално число на ординатната ос
- y2- крайно число на ординатната ос
```python
plt.axis([x1,x2,y1 ,y2]) 
```
Множествено плотиране:
plt.subplot() иска три аргумента:

* брой редове
* брой колони
* индекс на текущия плот

### Отстояния при плотиране: 
```python
plt.subplots_adjust()
```
- left - отляво
- right - отдясно
- bottom - отдолу
- top - отгоре
- wspace - по хоризонтала от двете страни
- hspace - по вертикала от двете страни
```python
from matplotlib import pyplot as plt

x = range(7)
straight_line = [0, 1, 2, 3, 4, 5, 6]
parabola = [0, 1, 4, 9, 16, 25, 36]
cubic = [0, 1, 8, 27, 64, 125, 216]

# Subplot 1
plt.subplot(2, 1, 1)
plt.plot(x, straight_line)

# Subplot 2
plt.subplot(2, 2, 3)
plt.plot(x, parabola)

# Subplot 3
plt.subplot(2, 2, 4)
plt.plot(x, cubic)

plt.subplots_adjust(wspace=0.35, bottom=0.2)

plt.show()
```
### Легенда:

plt.legend() приема два аргумента:
* списък с легенда за всяка от плотираните линии
* позиция на легендата (loc) :

- 0 	избери най-доброто
- 1 	горе дясно
- 2 	горе ляво
- 3 	долно ляво
- 4 	долно дясно
- 5 	дясно
- 6 	централно ляво
- 7 	централно дясно
- 8 	долно централно
- 9 	горно централно
- 10 	централно
```python
from matplotlib import pyplot as plt

months = range(12)
hyrule = [63, 65, 68, 70, 72, 72, 73, 74, 71, 70, 68, 64]
kakariko = [52, 52, 53, 68, 73, 74, 74, 76, 71, 62, 58, 54]
gerudo = [98, 99, 99, 100, 99, 100, 98, 101, 101, 97, 98, 99]

plt.plot(months, hyrule)
plt.plot(months, kakariko)
plt.plot(months, gerudo)


legend_labels=["Hyrule", "Kakariko",  "Gerudo Valley"]
plt.legend(legend_labels, loc=8)
plt.show()
```
### Деления и етикети на деления: 
```python
ax = plt.subplot()# променлива с която ще имаме достъп до деленията и техните етикети

ax.set_xticks([<списък от деления по абцисата>])
ax.set_xticklabels([<списък от етикети за деленията по абцисата>])
ax.set_yticks([<списък от деления по ординатата>] )
ax.set_yticklabels([<списък от етикети за деленията по ординатата>])

from matplotlib import pyplot as plt

month_names = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep","Oct", "Nov", "Dec"]

months = range(12)
conversion = [0.05, 0.08, 0.18, 0.28, 0.4, 0.66, 0.74, 0.78, 0.8, 0.81, 0.85, 0.85]

plt.xlabel("Months")
plt.ylabel("Conversion")

plt.plot(months, conversion)

# Your work here
ax = plt.subplot()
ax.set_xticks(months )
ax.set_xticklabels(month_names)
ax.set_yticks([0.10, 0.25, 0.5, 0.75] )
ax.set_yticklabels(['10%', '25%', '50%','75%'])
plt.show()
```
### Фигури
```python
plt.close('all') # изчиства всички предишни плотирания

plt.figure(figsize=(4, 10)) # ще създадем чертеж 4 на 10
plt.plot(x, parabola) # ще плотираме/създадем чертежа
plt.savefig('tall_and_narrow.png') # ще запазим плотирания чертеж в картинка с име tall_and_narrow.png
```


































