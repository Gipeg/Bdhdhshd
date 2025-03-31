# Bdhdhshd

import random

# 5.1 Генерация случайного числа и проверка на простоту
print("Задание 5.1")
num = random.randint(1, 1000)
is_prime = True
for i in range(2, int(num ** 0.5) + 1):
    if num % i == 0:
        is_prime = False
        break
print(f"Случайное число: {num}")
if is_prime and num > 1:
    print("Число простое")
else:
    print("Число не простое")

# 5.2 Угадай число
print("Задание 5.2")
secret_number = random.randint(1, 10)
while True:
    guess = int(input("Попробуйте угадать число от 1 до 10: "))
    if guess < secret_number:
        print("Загаданное число больше.")
    elif guess > secret_number:
        print("Загаданное число меньше.")
    else:
        print("Молодец, ты угадал!")
        break

# 5.3 Перевод температуры из Цельсия в Фаренгейт
print("Задание 5.3")
for celsius in range(100, -1, -10):
    fahrenheit = celsius * 1.8 + 32
    print(f"{celsius}°C = {fahrenheit:.1f}°F")

# 5.4 Проверка суммы покупки и сдачи
print("Задание 5.4")
while True:
    purchase_amount = float(input("Введите сумму покупки: "))
    if purchase_amount <= 0:
        print("Сумма покупки должна быть больше 0. Попробуйте снова.")
        continue
    payment = float(input("Введите внесенную сумму: "))
    if payment < purchase_amount:
        print(f"Не хватает {purchase_amount - payment:.2f}. Попробуйте снова.")
        continue
    if payment == purchase_amount:
        print("Спасибо!")
    else:
        print(f"Возьмите сдачу: {payment - purchase_amount:.2f}")
    break

# 5.5 Вывод значений функции y(x) = ax + b
print("Задание 5.5")
N = int(input("Введите количество значений N: "))
a = float(input("Введите коэффициент a: "))
b = float(input("Введите коэффициент b: "))
x1 = float(input("Введите значение x1: "))
x2 = float(input("Введите значение x2: "))

if x1 > x2:
    step = -1
else:
    step = 1

for i in range(N):
    x = x1 + i * step * (x2 - x1) / (N - 1)
    y = a * x + b
    print(f"y({x:.2f}) = {a}*{x:.2f} + {b} = {y:.3f}")
