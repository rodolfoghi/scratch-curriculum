---
title: Paint Box
level: Scratch 1
language: uk-UA
stylesheet: scratch
embeds: "*.png"
materials: ["notes for club leaders/*.*"]
...


#Набір для малювання

__Передмова:__
Цей проект передбачає створення інструменту для малювання. Ви зможете змінювати колір ліній, очищувати екран, робити штампи та багато іншого.

##Крок 1: Водіть мишкою і малюйте.

Ми розпочнемо із ручки, яка малює, коли нею водять по сцені.

1 - Створіть новий проект у Скретч.  Видаліть спрайт кота, клікнувши правою кнопкою мишки і натиснувши Видалити.

2 - У полі __сцени__ оберіть __Нове тло__ та імпортуйте __зображення класної дошки__ з папки "У приміщенні".

3 - Створіть новий спрайт і назвіть його __Олівець__, використайте папку __resources\green-pencil (ресурси/зелений олівець)__.

4 - Перейдіть до вкладки __Образи__ та у __Редакторі малюнків__ розташуйте центр зображення на кінчику ручки/олівця.  Для цього оберіть кнопку "встановити центр образу" і розмістіть (обертаючи і перетягуючи) його так, щоб позначка центру зображення була на кінчику ручки/олівця.

5 - Зробіть так, щоб олівець слідував за мишкою по сцені, використовуйте блоки команд __"завжди"__ (вкладка Керувати) та __"переміститись у вказівник миші"__ (вкладка Рух).


```scratch
коли натиснуто зелений прапорець
завжди
	переміститись в вказівник миші
(кінець завжди)
```

__Тепер потрібно зробити так, щоб спрайт олівця повинен діяти як справжній олівець.__ 
У вкладці Олівець є багато блоків, пов'язаних з малюванням, але ми спершу використаємо блоки "підняти олівець" та "опустити олівець".

6 - Ми будемо використовувати кнопку мишки, щоб керувати олівцем – коли мишка рухається вниз, то й олівець рухається вниз, а коли вести мишкою вверх, то і олівець повинен рухатись вверх.  Це можна зробити за допомогою блоків "якщо то" та "мишку натиснуто?"

```scratch
коли натиснуто зелений прапорець
завжди
	переміститись в вказівник миші
	якщо мишку натиснуто?
	опустити олівець
	інакше
	підняти олівець
	(кінець якщо)
(кінець завжди)
```
##Протестуйте свій проект.
__Натисніть на зелений прапорець.__
Чи рухається олівець за мишкою?  Що відбувається, якщо утримувати кнопку мишки натиснутою і рухати мишкою? Не турбуйтесь з приводу кольору олівця поки що.


7 - З часом екран заповниться різною писаниною.  Для того, щоб його очистити, використайте відповідний блок під назвою "очистити":

```scratch
оли натиснуто зелений прапорець
очистити
завжди
	переміститись в вказівник миші
	якщо мишку натиснуто?
	опустити олівець
	інакше
	підняти олівець
	(кінець якщо)
(кінець завжди)
```

##Протестуйте свій проект.
__Натисніть на зелений прапорець.__

Чи зникає намальоване, коли натиснути зелений прапорець?

Збережіть свій проект.

##Крок 2: Очищення екрану

Замість того, щоб зупиняти і заново запускати проект, додайте кнопку очищення екрану.  Вона працюватиме за допомогою блоку "очистити".

1. Створіть новий спрайт з відповідним образом __(resources/cancel button)__.
2. Змініть ім'я спрайту на __Очистити__.
3. Розмістіть спрайт у лівому нижньому кутку сцени.
4. Створіть для нього наступний скрипт:

```scratch
коли натиснуто очистити
очистити
```

##Протестуйте свій проект.
__Натисніть на зелений прапорець.__

Чи очищає кнопка очищення сцену від усього написаного?

Збережіть свій проект

##Крок 3: Зміна кольору

Отже, ми можемо малювати лише блакитні лінії.  Давайте спробуємо якісь інші кольори.  Додамо кілька спрайтів внизу сцени.  Спрайти виглядатимуть як кольорові кнопки.  Якщо ми натиснемо на таку кнопку, колір лінії зміниться на колір кнопки.  Так ми знатимемо, який колір використовуємо; кнопка також змінить колір спрайту олівця.

1. Створіть новий спрайт, використавши образ __resources/red-pencil__
2. Розмістіть його внизу сцени поряд з __кнопкою Очистити__.
3. При натисканні спрайта Червоний, він повинен оповістити __червоний__.

```scratch
коли натиснуто червоний
оповістити червоний
```
__Ось і все, що робить цей спрайт. Основна ж робота призначена для олівця.__

Для спрайту олівця імпортуйте новий образ __resources/red-pencil__ Встановіть центр образу так, щоб позначка центру зображення була на кінчику ручки/олівця.ume.

4. Додайте новий скрипт для олівця.  Коли олівець отримує сповіщення __червоний__, він повинен змінити образ на образ червоного олівця і змінити колір на червоний (для цього використайте блок "задати колір олівця").

__Підказка:__ якщо клікнути на кольоровий квадратик у блоці "задати колір олівця", то можна __скористатись інструментом "піпетка"__ і клікнути на спрайт Червоний, щоб переконатись, що це  той самий колір.

```scratch
when I receive red
switch to costume
red-pencil
set pen color to (red)
```

##Протестуйте свій проект.
__Натисніть на зелений прапорець.__

Намалюйте лінію.  Потім оберіть червоний колір і продовжте лінію.  Чи змінив спрайт олівця образ? Чи малює він тепер червоним? Чи малює він кінчиком червоного олівця?

Збережіть свій проект.

5. Повторіть описані вище операції для блакитного, жовтого, зеленого спрайтів вибору кольорів.

##Протестуйте свій проект.
__Натисніть на зелений прапорець.__

Чи працюють усі кнопки вибору кольорів? Чи всі вони правильно змінюють образ  спрайта олівця?  Чи всі вони змінюють колір олівця на вірний?  Чи всі образи малюють кінчиком олівця?

Збережіть свій проект.

##Крок 4: Створення зони малювання.

YВи напевно помітили, що можете малювати на усій сцені, навіть по краях.  Але це небажано.  Малювати треба посередині сцени.  Це можна забезпечити обмеживши можливість олівця виходити за межі зони малювання – світло сірої частини сцени.

Пам'ятайте, що у Скретч задати точку можна координатами х та у.  Наша зона малювання знаходиться в межа 230 та -230 по осі х, 170 і -170 по осі у.  Можна використати ці значення та блок "якщо" для того, щоб переконатись, що курсор мишки знаходить в зоні малювання, перш ніж ми перемістимо туди олівець.

Для цього введіть ще один блок __якщо__ у скрипт, перевіряючи координати точки, у кій міститься курсор мишки:

mouse y is greater than -120 and mouse y is less than 170 and mouse x is greater than -230 and mouse x is less than 230

__Зауважте__, що для цього потрібно кілька разів використати блок з оператором __і__, перший для двох умов щодо координати по осі х, другий для двох умов по координаті для осі у та третій для об'єднання двох попередніх умов.

```scratch
очистити
завжди якщо мишка y більше -120 і мишка у менше 170 і мишка x більше -230 і мишка x isменше 230
перемаститись до вказівник миші
```
Оскільки не можна малювати поза зоною малювання, можна ховати інструмент Олівець, коли його не використовують.  Для цього замініть блок __якщо__ на блок __якщо інакше__.  Залишіть ту ж умову __якщо__ і додайте блок __показати__, якщо вона істинна, інакше __сховати__.

```scratch
коли натснуто зелений прапорець
підняти олівець
очистити
завжди
	якщо мишка y більше -120 і мишка у менше 170 і мишка x більше -230 і мишка x isменше 230
		перемаститись до вказівник миші
		показати
		якщо мишку натиснуто?
			опустити олівець
		інакше
			підняти олівець
		(кінець якщо)
	інакше
		сховати
	(кінець якщо)
(кінець завжди)
```

##Протестуйте свій проект.
__Натисніть на зелений прапорець.__

Чи можете ви малювати у зоні малювання?Чи можна малювати поза нею? Що відбувається з олівцем, коли вийти за межі зони малювання, а потім повернутись у неї?

Збережіть свій проект.

##Крок 5: Резинка/стирання.

__Малювання ліній - це чудово, але трапляються помилки, які хочеться виправити.__ Це можна зробити за допомогою олівця, який замалює все у колір фону.

Додайте новий спрайт-кнопку на сцену, щоб з'явилась кнопка Резинка. Скористайтесь образом __resources/eraser__ для неї, зменшіть її таким чином, щоб розмістити внизу сцени.  Вона повинна працювати так само, як і кнопки вибору кольорів і давати оповіщення "Резинка".  

Спрайт олівця повинен відповідати на це оповіщення зміною кольору на колір фону (для того, щоб обрати колір скористайтесь __піпеткою__ і виберіть колір фону).  Також необхідний новий образ для демонстрації інструменту Резинка: використайте __resources/eraser__. __Не забудьте встановити для нього центр, як у попередніх кроках.__

##Протестуйте свій проект.
__Натисніть на зелений прапорець.__

Чи стирає резинка лінії? Чи діє вона у всій площині сцени до її країв ? Чи можна переключатись між інструментами олівець та резинка?

Збережіть свій проект.

##Крок 6: Штампи.

Наступний крок це додавання інструменту Штампи для нанесення маленьких картинок на малюнок. 

Перелік дій:

1 - Додайте новий спрайт, використавши будь-який образ чи зображення.  Зменште його розмір і розмістіть спрайт внизу сцени поряд з іншими інструментами.  при кліканні на цей спрайт він повинен давати оповістити __штамп__(блок "оповістити").

2 - Додайте новий образ для спрайту олівця, той же, який вибрано для спрайу __штамп__.

3 - Виберіть спрайт олівця і створіть нову змінну під назвою __Вид олівця__ лише для цього спрайта.  Вона потрібна для того, щоб розрізняти дії малювання та створення штампів.

4 - Додайте новий скрипт, що відповідав би на сповіщення "штамп".  Він повинен містити блок __змінити образ на штамп__ та присвоїти змінній __Вид олівця__ значення __хибно__.

5 - Змініть інші скрипти, які відповідають на сповіщення про інструменти колір олівця (червоний, зелений блакитний) та резинка таким чином, щоб вони присвоювали змінній __Вид олівця__ значення  __істинно__.

6 - І нарешті перевірте цю змінну у момент, __коли курсор мишки рухається вниз__, щоб з'ясувати, яка дія виконується – малювання чи штампування.  Якщо "Вид олівця"  = істинно, то повинен виконуватись блок __підняти олівець__, а якщо ні, то функція штампування.


##Протестуйте свій проект.

__Натисніть на зелений прапорець.__


Чи коректно працює інструмент штампування? 

Що відбувається при поверненні до одного зі звичайних інструментів малювання?

Збережіть свій проект.


__Молодець! Створення основного проекту завершено.  Спробуйте виконати додаткові завдання.__


##Додаткове завдання 1: Олівець-райдуга.

Додамо особливий олівець, що малює всіма кольорами райдуги.  Такі олівці насправді є, тому було б добре і за допомогою комп'ютера створити такий же олівець.  Ключ до створення такого олівця – використання блоку зміни кольору.

По-перше, додайте спрайт вибору олівця-райдуги та відповідний образ для спрайту олівця:

1. Створіть новий спрайт вибору інструменту і розмістіть його внизу сцени поруч зі спрайтами вибору кольорів.  Використайте образ resources/rainbow-selector  і задайте при кліканні на нього сповіщення "райдуга".
2. Додайте образ resources/rainbow-selector для спрайта олівця.

Необхідно створити скрипт, який змінюватиме колір олівця кілька разів за секунду для створення ефекту райдуги (зміна кольорів 5 разів кожні 0.5 секунди цілком підходить, але слід спробувати різні варіанти).  Скретч картка Таймер показує, як зробити так, щоб щось часто змінювалось.  Використайте блок "змінити колір олівця на 5" замість блоку в Таймері "змінити таймер на -1" всередині циклу.

Також необхідно контролювати виконання цього циклу, щоб він змінював колір олівця лише при виборі інструменту Олівець-райдуга, інакше усі інструменти матимуть ефект райдуги!  Це можна зробити за схемою переходів спрайту олівця між функціями малювання та штампування.  Потрібно створити змінну під назвою "Перехід до райдуги" зі значенням істинно, коли обирається олівець-райдуги та значенням хибно у всіх інших випадках.  Кожного разу, коли олівець відповідає на оповіщення інструменту вибору, повинно присвоюватись відповідне значення змінній"Перехід до райдуги".

Скористайтесь тим, що ви уже знаєте з кроку Штампи для контролю за ефектом райдуги. Скрипти. які відповідають на оповіщення про вибір інструменту малювання повинні присвоїти значення двом змінним: "Вид олівця" та "Перехід до райдуги".

##Протестуйте свій проект.
__Натисніть на зелений прапорець.__

Чи коректно працює  інструмент райдуги? 

Що відбувається при переході на звичайні інструменти малювання?

Збережіть свій проект.

##Додаткове завдання 2: Клавіші швидкого викликуcuts

Замість вибору спрайтів інструментів малювання чи штампування внизу сцени шляхом клікання на них можна скористатись клавіатурою.  Слід використати блок "коли натиснуто клавішу []". Для кожного інструменту вибору необхідно пописати у скрипті окремий блок "коли натиснуто клавішу []", що має таку ж дію, що й клікання на відповідний спрайт. Додайте ці скрипти для сцени.

Можна використати такі  "клавіші швидкого виклику":
* Clear all – a (очистити)
* Er Eraser – e (резинка)
* Red pencil –r (червоний олівець)
* Blue pencil – b (блакитний олівець)
* Yellow pencil – y (жовий олівець)
* Green pencil – g (зелений олівець)
* Rainbow pencil – w (олівець-райдуга)
* Stamp – s (штамп)


##Протестуйте свій проект.
__Натисніть на зелений прапорець.__

Чи можна обрати усі інструменти за допомогою  відповідних клавіш?Чи всі інструменти коректно працюють при виборі їх клавішами? Чи правильно обираються інструменти при кліканні на їх спрайти на сцені?

Збережіть свій проект.

##Додаткове завдання 3: Збільшення та зменшення олівця.
Інша функція, яка часто зустрічається у програмах,що дозволяють малювати, - це зміна розміру олівця.  Давайте створимо її.  Складність може виникнути через те, що іноді зміна розміру потребує зміни розмірів олівця, а іноді зміни розмірів образу спрайту олівця.  Це залежить від того, яка функція (малювання чи штампування) використовується.

Створіть 2 нових спрайти вибору інструментів під назвами "Більший" і "Менший". У них повинні бути образи resources/bigger-selector та resources/smaller-selector і вони повинні надсилати сповіщення "більший", "менший".

Спрайт олівця повинен реагувати на ці сповіщення зміною або розміру олівця на 1 або образу олівця на 10, залежно від того, який вид олівця застосовується (використайте блоки "якщо ... інакше" таким же чином, як вони використані у скрипті, за яким спрайт обирає між штампуванням та "опустити олівець").  Не забудьте прописати клавіші швидкого вибору для інструментів "Більший" та "Менший".  Можна використати клавіші стрілок вгору та вниз.

Збережіть свій проект.

Ви помітили, що зміна розміру штампу також змінює розмір олівця на екрані, якщо знову обрати цей інструмент. Щоб цього не відбувалось необхідно встановити розмір 100% кожного разу, коли відбувається перехід до функції власне олівця. Так щоб інструмент мав належний розмір.

Ще краще, щоб інструмент штампування пам'ятав, який розмір він мав до вибору олівця і повертався до цього розміру при повторному виборі штампування.  Найпростіше це зробити за допомогою змінної "Розмір штампу", яка оновлюється до поточного розміру щоразу, коли розмір інструменту штампування змінюється.  При виборі інструменту штампування, його розмір може обиратись із пам'яті цієї змінної.

##Протестуйте свій проект.
__Натисніть на зелений прапорець.__

Чи впливає розмір на роботу олівців? 

Що відбувається при переході до інструменту штампування, зміні розміру, а потім поверненні до інструменти власне олівця?

Збережіть свій проект.

__Молодець! Проект завершено, тепер можна насолоджуватись грюe!__

Не забудьте поділитись грою з друзями та рідними, клікнувши __Поділитись цим проектом__ у рядку меню. 