
import random

print("ПРИКЛЮЧЕНИЕ В ТЁМНОМ ЛЕСУ")
print("Ты проснулся на лесной поляне. Нужно найти выход.\n")

health = 3
has_key = False

while health > 0:
    print("\nКуда пойти?")
    print("1 — К старой башне")
    print("2 — В тёмную пещеру")
    print("3 — К лесному выходу")

    choice = input("> ").strip()

    if choice == "1":
        if not has_key:
            print("\nВ башне ты находишь блестящий ключ!")
            has_key = True
        else:
            print("\nВ башне больше ничего нет.")

    elif choice == "2":
        event = random.choice(["treasure", "monster", "nothing"])

        if event == "treasure":
            print("\nТы нашёл целебную ягоду. Силы восстановлены!")
            health = min(health + 1, 3)
        elif event == "monster":
            health -= 1
            print("\nИз темноты выпрыгнуло лесное чудище! Ты потерял одну жизнь.")
        else:
            print("\nПещера пуста. Только капли воды падают с потолка.")

    elif choice == "3":
        if has_key:
            print("\nКлюч подошёл к замку на воротах.")
            print("Ты выбрался из леса. Победа!")
            break
        else:
            print("\nВыход закрыт. Сначала нужно найти ключ в старой башне.")

    else:
        print("\nВведи 1, 2 или 3.")
        continue

    print("Жизни:", health)

if health == 0:
    print("\nСилы закончились. Приключение завершено.")
    print# dark-forest-game.
Текстовая приключенческая игра на Python.
