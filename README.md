# Project_discrete - Backtracking

# Tasks: судоку, кросворд, лабіринти, розфарбування, задача з королевами, магнітний пазл

--------------------------------------------------------------------------------------------------------------------

## 1) Алгоритм
Бектрекінг (backtracking) - це алгоритм, який використовується для розв'язання комбінаторних задач, таких як головоломки, задачі про перебору комбінацій, складання графів та інші. Його основна ідея полягає в тому, щоб систематично перебирати всі можливі варіанти розв'язку задачі, відстежуючи і виправляючи помилки по мірі їх виникнення.

Основна концепція полягає в тому, щоб спробувати кожен можливий варіант розв'язку задачі, рухаючись по дереву рішень. Якщо на якому-небудь етапі виявляється, що поточний варіант не може бути продовжений до правильного розв'язку, алгоритм повертається назад (backtracks) і спробує інший варіант.

### Основні кроки алгоритму бектрекінгу:

1. **Вибір варіанту**: Обирається наступний можливий варіант розв'язку задачі.

2. **Перевірка**: Перевіряється, чи є обраний варіант допустимим та чи приводить він до розв'язку задачі.

3. **Виконання**: Якщо вибраний варіант прийнятний, він виконується, і алгоритм рухається далі глибше в пошуках розв'язку.

4. **Повернення назад (backtrack)**: Якщо вибраний варіант не призводить до розв'язку, або виявляється, що він не може бути продовжений, алгоритм повертається назад до попереднього етапу вибору і обирає інший варіант.

Цикл вибору, перевірки, виконання та повернення назад продовжується до тих пір, поки не буде знайдено розв'язок або поки всі можливі комбінації не будуть перевірені.

Бектрекінг є потужним методом для розв'язання комбінаторних задач і використовується в багатьох областях, таких як штучний інтелект, оптимізація, криптографія та багато інших.

--------------------------------------------------------------------------------------------------------------------

# --- СУДОКУ ---



# --- M-COLORING ---

Задача: 
  Задача M-розфарбування (M-coloring) полягає в тому, щоб призначити кожному вузлу графа один із M кольорів таким чином, щоб жодні два сусідні вузли не мали однакового кольору. Якщо вдалося   так розфарбувати весь граф, то граф називається M-розфарбованим.


  на вхід дається -> (число вершин, число кольорів, ймовірність з'єднання)
  на вихід -> якщо можна розфарбувати, то малюнок як саме. якщо не вистачає кольорів - повідомлення, що не можна розфарбувати


### Загальна інформація:
  -Функція is_valid: Ця функція перевіряє, чи може поточний вузол бути розфарбований певним кольором, порівнюючи його з коліром сусідів. Якщо хоча б один з сусідів має той самий колір, що       і поточний вузол, функція повертає False, інакше - True.
  
  -Функція coloring: Ця рекурсивна функція вирішує задачу розфарбування графа. Вона спробує призначити кожному вузлу кольори, використовуючи метод бектрекінгу. Якщо вдалося розфарбувати всі     вузли, функція повертає True, в іншому випадку - False.
  
  -Функція run: Ця функція ініціалізує граф, додаючи до нього випадкові ребра з заданою ймовірністю. Потім вона викликає функцію coloring, щоб спробувати розфарбувати граф, та якщо це           вдається, вона візуалізує результат за допомогою бібліотеки networkx та matplotlib. Якщо ж функція coloring повертає False, виводиться повідомлення про те, що рішення не існує.
  
  -Змінні num_nodes, num_colors та probability: Вони визначають кількість вузлів у графі, кількість кольорів, якими можна розфарбувати граф, і ймовірність додавання кожного ребра між            вузлами в графі відповідно. Ці значення можна змінювати в залежності від вимог задачі.
  
  -Створення графу G: За допомогою бібліотеки NetworkX створюється граф з вузлами та випадково доданими ребрами на основі встановленої ймовірності.
  
  -Виклик функції coloring: Викликається рекурсивна функція coloring, яка намагається розфарбувати граф. Якщо це вдається, тобто функція повертає True, то відбувається візуалізація графа за     допомогою networkx.draw та matplotlib.pyplot.show. Якщо ж функція coloring повертає False, виводиться повідомлення про те, що рішення не існує.

  складність алгоритму : O(num_colors * (num_colors ^ num_nodes))

# --- ЛАБІРИНТИ ---

У нас є 2 типи лабіринтів: звичайні і з телепортами


### Особливості
  - Можливість читання макетів лабіринтів з текстових файлів.
  - Використання алгоритму пошуку в глибину для знаходження шляху рішення.
  - Візуалізація лабіринту та шляху рішення за допомогою Pygame.

### Використання
Помістіть свої файли з макетами лабіринтів у директорію test_cases_simple.

Запустіть скрипт maze_solver.py:
python maze_solver.py

Програма відобразить лабіринт та шлях рішення. Закрийте вікно, щоб вийти з програми.

Формат файлу з макетом лабіринту
Макет лабіринту повинен бути визначений у текстовому файлі, де кожен символ представляє певний елемент:

"." або (пробіл) для порожніх клітин.
"#" для стін.
"?" для точки старту.
"!" для кінцевої точки.
Приклад:

 -###########-\n-#?  #  #  #-
 -#   #  #  #-
 -### #     #-
 -#   # ### #-
 -# ###     #-
 -#       ###-
 -########!##-

### Ініціалізація:
Початкова позиція на мапі, де розташований символ початку шляху, визначається і позначається як кореневий вузол дерева.
Також знаходиться кінцева позиція, де знаходиться символ кінця шляху.
### Побудова дерева:
Починаючи з кореневого вузла, рекурсивно додаються дочірні вузли, які представляють допустимі сусідні позиції на мапі.
Для кожної позиції обчислюються її допустимі сусіди (верх, низ, ліворуч, праворуч), і якщо вони не знаходяться в межах мапи або представляють собою перешкоду, вони не розглядаються.
Якщо сусідня позиція ще не була відвідана, створюється новий вузол для цієї позиції і рекурсивно викликається побудова дерева для цієї нової позиції.
### Пошук шляху:
Після побудови дерева розпочинається рекурсивний пошук шляху від початкової позиції до кінцевої.
Кожен раз, коли рекурсивно викликається функція пошуку шляху, вона перевіряє, чи поточна позиція вузла є кінцевою. Якщо так, шлях знайдено, і повертається список з позиціями вузлів, які утворюють шлях.
Якщо поточна позиція не є кінцевою, функція рекурсивно викликається для кожного дочірнього вузла поточного вузла, доки не буде знайдено шлях або не будуть перевірені всі можливі напрямки.
### Повернення результату:
Якщо шлях знайдено, повертається список з позиціями вузлів, які утворюють шлях від початку до кінця.
Якщо шлях не знайдено (наприклад, якщо неможливо досягнути кінцеву позицію), повертається відповідне повідомлення.
### Часова та просторова складність:
Часова складність алгоритму залежить від кількості клітин на мапі та кількості можливих шляхів.
Просторова складність алгоритму залежить від розміру дерева, що будується. Це може бути важливо для великих мап з великою кількістю можливих шляхів.

# --- ЗАДАЧА З КОРОЛЕВАМИ ---
