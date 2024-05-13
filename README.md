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

1) Функції
Функція is_valid: Ця функція перевіряє, чи може бути поточний вузол розфарбований певним кольором. Вона перевіряє кольори сусідів поточного вузла і перевіряє, чи співпадає хоча б один з них з поточним кольором. Якщо так, функція повертає False, інакше - True.

Функція coloring: Ця рекурсивна функція вирішує задачу розфарбовування графа. Вона спробує призначити кожному вузлу кольори, використовуючи backtracking. Якщо вдалося розфарбувати всі вузли, функція повертає True, в іншому випадку - False.

Функція run: Ця функція ініціалізує граф, додаючи до нього випадкові ребра з заданою ймовірністю. Потім вона викликає функцію coloring, щоб спробувати розфарбувати граф, та якщо вдається, вона візуалізує результат за допомогою бібліотеки networkx та matplotlib.


# --- ЛАБІРИНТИ ---
