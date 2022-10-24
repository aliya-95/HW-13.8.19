tickets = int(input("Сколько билетов вы хотите приобрести на мероприятие? "))
age = list(map(int, input("Просьба указать возраст посетителей через пробел: ").split()))
while tickets != len(age):
    age = list(map(int, input("Количество посетителей не совпадает с количеством билетов.\n"
                              "Просьба указать возраст посетителей через пробел: ").split()))
price = []
for i in age:
    if i in range(0, 18):
        price.append(0)
    elif i in range(18, 25):
        price.append(990)
    else:
        price.append(1390)

if tickets > 3:
    print("Сумма к оплате с учетом 10%-ой скидки на полную стоимость заказа за регистрацию больше 3-х человек: ", sum(price) - ((sum(price) / 100) * 10), "рублей")
else:
    print("Сумма к оплате: ", sum(price), "рублей")