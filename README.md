# Problem 1 

## Задача о математическом ожидании количества уникальных видов животных
На ферме содержатся шесть разных видов животных, и каждый раз, когда фермер заходит в сарай, он видит одно случайное животное. За день фермер заходит в сарай 6 раз. Каково математическое ожидание количества разных видов животных, которые фермер увидит за день?
Ответ округлить до сотых.
Формат ответа: значение матожидания, например: 4.12

**Требуется:**  
Найти математическое ожидание количества разных видов животных, которых фермер увидит за день. Ответ округлить до сотых.

## Решение

### Метод решения
Используем вероятностный подход с индикаторными переменными для каждого вида:

1. Вероятность, что конкретный вид **не** будет увиден за 1 заход: 5/6
2. Вероятность, что вид не будет увиден за 6 заходов: (5/6)^6 ≈ 0.3349
3. Вероятность, что вид будет увиден хотя бы раз: 1 - (5/6)^6 ≈ 0.6651
4. Матожидание для одного вида: 0.6651
5. Общее матожидание (6 видов): 6 × 0.6651 ≈ 3.9906

### Ответ
**Матожидание количества уникальных видов:**  
`3.99`

# Problem 2

## Кулинарное соревнование: матожидание победителей
В конкурсе участвуют 80 шеф-поваров с уникальными уровнями мастерства. В первом этапе судьи случайным образом распределяют их по парам (в любом состязании двух шефов выигрывает тот, у кого выше уровень мастерства). На втором этапе шефы снова случайно образуют пары для финального раунда (пары могут повториться). Победную награду получают те, кто выиграл в обоих этапах. 
Каково математическое ожидание числа победителей? 
Ответ округлите до десятых, например: 33,5

- **Участники:** 80 шеф-поваров с уникальными уровнями мастерства
- **Этапы:**
  1. Первый этап: случайное разбиение на 40 пар → победитель в каждой паре определяется уровнем мастерства
  2. Второй этап: новое случайное разбиение на 40 пар (возможны повторные пары)
- **Победители:** Шефы, выигравшие в обоих этапах

**Требуется:**  
Найти математическое ожидание количества победителей. Ответ округлить до десятых.

## Решение

### Метод решения
1. **Фиксируем одного шефа** с рангом k (1 ≤ k ≤ 80, где 1 - слабейший, 80 - сильнейший)
2. **Вероятность победы в одном этапе:**
   - Шеф побеждает, если попадает на более слабого соперника
   - P(победа) = (k-1)/79
3. **Для двух независимых этапов:**
   - P(две победы) = [(k-1)/79]²
4. **Матожидание для всех шефов:**
   - E = Σ от k=1 до 80 [(k-1)/79]²
   - Вычисляем сумму: Σ(k-1)² = Σ от m=0 до 79 m² = 79×80×159/6 = 167480
   - E = 167480 / 79² ≈ 167480 / 6241 ≈ 26.83

### Ответ
**Матожидание числа победителей:**  
`26.8`

# Problem 3

## Вероятность появления автомобиля на пустынном шоссе
На пустынном шоссе вероятность появления автомобиля за 30-минутный период составляет 0.95. Какова вероятность его появления за 10 минут? а за 27 минут?
Ответы дайте в процентах, округлив до десятых через точку с запятой.
Формат ответа: вероятность в процентах, например: 42.7;95.0

## Условие задачи
- **Исходные данные:**
  - P(появления за 30 мин) = 0.95
- **Требуется найти:**
  - P(появления за 10 мин) = ?
  - P(появления за 27 мин) = ?
- **Формат ответа:**
  - Вероятности в процентах, округленные до десятых
  - Разделитель - точка с запятой (например: `42.7;95.0`)

## Решение

### Метод решения
Используем экспоненциальное распределение для моделирования времени между событиями:

1. **Находим параметр λ (интенсивность):**
P(T ≤ 30) = 1 - e^(-λ*30) = 0.95
e^(-30λ) = 0.05
-30λ = ln(0.05) ≈ -2.9957
λ ≈ 0.09986 (событий в минуту)

2. **Формула для произвольного интервала t:**
P(T ≤ t) = 1 - e^(-λ*t)

3. **Расчеты:**
- **Для 10 минут:**
  ```
  P = 1 - e^(-0.09986*10) ≈ 1 - 0.3685 ≈ 0.6315 → 63.2%
  ```
- **Для 27 минут:**
  ```
  P = 1 - e^(-0.09986*27) ≈ 1 - 0.0676 ≈ 0.9324 → 93.2%
  ```

### Ответ
`63.2;93.2`
