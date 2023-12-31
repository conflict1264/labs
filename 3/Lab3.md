## Комп'ютерні системи імітаційного моделювання

## СПм-22-5, **Зубенко Сергій Петрович**

### Лабораторна робота №**3**. Використання засобів обчислювального интелекту для оптимізації імітаційних моделей

<br>

### Варіант 8, модель у середовищі NetLogo:

[Segregation Simple Extension 1.](http://www.netlogoweb.org/launch#http://www.netlogoweb.org/assets/modelslib/IABM%20Textbook/chapter%203/Segregation%20Extensions/Segregation%20Simple%20Extension%201.nlogo)

<br>

### Налаштування середовища BehaviorSearch:

**Обрана модель**:

<pre>
Segregation Simple Extension 1
</pre>

**Параметри моделі** (вкладка Model):

<pre>
["number" [500 10 2500]]
["%-similar-wanted" [0 1 100]]
["number-of-ethnicities" [2 1 5]]
</pre>

Використовувана **міра**:  
Для фітнес-функції було обрано **відсоток одинакових черепах**, вираз для її розрахунку взято з налаштувань монітору аналізованої імітаційної моделі в середовищі NetLogo  
![Редагування параметрів графіку вихідної моделі](percent-similar.png)  
та вказано у параметрі "**Measure**":
<pre>
percent-similar
</pre>

Середній відсоток черепах повиннен враховуватися **в максимальній** за весь період симуляції тривалістю, 100 тактів , починаючи з 0 такту симуляції.  
Параметр зупинки за умовою ("**Stop if**") у разі не використовувався.  
Загальний вигляд вкладки налаштувань параметрів моделі:  
![Вкладка налаштувань параметрів моделі](parameters.png)

**Налаштування цільової функції** (вкладка Search Objective):  
Метою підбору параметрів імітаційної моделі, що втілює взаємодію черепах різних видів в середовищі ставу, є **максимізація** відсотка одинакових черепах – це вказано через параметр "**Goal**" зі значенням **Maximize Fitness**. При цьому цікавить не просто значення нещасливих черепах, а її максимальне значення протягом всієї симуляції (тривалість якої (100 тактів) вказувалася на минулій вкладці). Для цього у параметрі "**Collected measure**", що визначає спосіб обліку значень обраного показника, вказано **MAX_ACROSS_STEPS**.
Щоб уникнути викривлення результатів через випадкові значення, що використовуються в логіці самої імітаційної моделі, **кожна симуляція повторюється по 15 разів**, результуюче значення розраховується як **середнє арифметичне**.
Загальний вигляд вкладки налаштувань цільової функції:
![Вкладка налаштувань цільової функції](objective.png)

**Налаштування алгоритму пошуку** (вкладка Search Algorithm):
Загальний вид вкладки налаштувань алгоритму пошуку:
![Вкладка налаштувань пошуку](search.png)

<br>

### Результати використання BehaviorSearch:

Діалогове вікно запуску пошуку *(можна залишити за замовчуванням, але стежте, куди пишеться результат)*:

![Вікно запуску пошуку](dialog.png)

Результат пошуку параметрів імітаційної моделі, використовуючи **генетичний алгоритм**:  
![Результати пошуку за допомогою ГА](ga.png)

Результат пошуку параметрів імітаційної моделі, використовуючи **випадковий пошук**:  
![Результати випадкового пошуку](rs.png)

Робота моделі у середовищі NetLogo з парметрами:
![Результати роботи моделі](rezult.png)
