import random
import string
import time

print("Hello, world!")

passwords = [
    "g7X!k2Pq9L#", "M4r@Z8sV1b%", "tY9^h3Wc6Q&", "pK2$e7Nf5Ux", "R8z*B1mV4q!",
    "sD3(La6T0w)", "uF5+g9Cj2Hy", "N1v#P6xR8zL", "oQ7?b4Sg3Kd", "hM2&y8Zp5Vc",
    "A9k!r3Tz6Qw", "cV4@p7Lx1Bn", "J8s^f2Gm5Hu", "eR6$y1Wq9Oz", "tP3*o8Nf0Kj",
    "lS5(Ze4Xc2V", "mH7+v9Bq1Yn", "qD2#u6Ck8Pr", "wF0?g5Lt3Mz", "zB1&n4Sj7Qx",
    "yK9!p2Vf6Rw", "xN4@h8Mq1Zd", "bT7^s3Lc5Gy", "iC6$e9Pw2Ux", "oL3*u1Zk7Vr",
    "fJ5(q4Bn8Ms", "vG2+z6Hd0Yp", "nQ8#t5Sc3Le", "rH1?m7Xy4Fk", "aP6&b2Vj9Zw",
    "S9k!g3Dq6Lp", "T4r@v8Hz1Mn", "U8s^y2Wm5Kb", "V6$e1Rp9Oz", "G3*o8Nf0Jt",
    "E5(q4Lc2Sv", "I7+v9Bq1Hy", "O2#u6Ck8Pr", "P0?g5Lt3Wz", "Q1&n4Sj7Xx",
    "K9!p2Vf6Rw", "L4@h8Mq1Zd", "M7^s3Lc5Gy", "N6$e9Pw2Ux", "B3*u1Zk7Vr",
    "C5(q4Bn8Ms", "D2+z6Hd0Yp", "F8#t5Sc3Le", "H1?m7Xy4Fk", "J6&b2Vj9Zw",
    "kZ9!r3Tq6Lp", "lX4@p8Vz1Bn", "mC8^f2Gs5Hu", "nE6$y1Wq9Oz", "oT3*o8Nf0Kj",
    "pS5(q4Ze2Vx", "qH7+v9Bq1Yn", "rD2#u6Ck8Pr", "sF0?g5Lt3Mz", "tB1&n4Sj7Qx",
    "uK9!p2Vf6Rw", "vN4@h8Mq1Zd", "wT7^s3Lc5Gy", "xC6$e9Pw2Ux", "yL3*u1Zk7Vr",
    "zJ5(q4Bn8Ms", "aG2+z6Hd0Yp", "bQ8#t5Sc3Le", "cH1?m7Xy4Fk", "dP6&b2Vj9Zw",
    "eS9!g3Dq6Lp", "fT4@v8Hz1Mn", "gU8^y2Wm5Kb", "hV6$e1Rp9Oz", "iG3*o8Nf0Jt",
    "jE5(q4Lc2Sv", "kI7+v9Bq1Hy", "lO2#u6Ck8Pr", "mP0?g5Lt3Wz", "nQ1&n4Sj7Xx",
    "oK9!p2Vf6Rw", "pX4@h8Mq1Zd", "qM7^s3Lc5Gy", "rN6$e9Pw2Ux", "sB3*u1Zk7Vr",
    "tC5(q4Bn8Ms", "uD2+z6Hd0Yp", "vF8#t5Sc3Le", "wH1?m7Xy4Fk", "xJ6&b2Vj9Zw",
    "yZ9!r3Tq6Lp", "zX4@p8Vz1Bn", "aC8^f2Gs5Hu", "bE6$y1Wq9Oz", "cT3*o8Nf0Kj",
    "dS5(q4Ze2Vx", "eH7+v9Bq1Yn", "fD2#u6Ck8Pr", "gF0?g5Lt3Mz", "hB1&n4Sj7Qx",
    "Alice_MrBist", "Charlie_990", "Eva_777", "Sam_Winchester-Sam", "Lara_Croft_01", "Neo_TheOne", "Mike_Tyson",
    "Messi_pushka_Ronaldo_Igrushka", "Farid_2013_27", "Dmitriy_Avdeev_2008", "Misha_Slon649374",
    "An*ya@g+Belaya", "password", "123", "123456789", "abc123", "GeekBrains", "Misha_zabivnoy", "' OR 1 = 1--",
    "let_me_in:)", "admin", "2@7843@+Lkl", "Why_i_love_python!?", "Nikita_dragon's_shadow", "secure*password123",
    "let_me_in_abrakadabra",
    "Germany_fan74@#+]p", "K*k@shk&_2024!SQL", "P5ssw#rd", "Tchenki", "vova_2008", "qwertyuiop",
    "abcdefghklmoprstuvwxyz",
    "okbo867@*3#", "Ninja_warrior_99@", "DragonSlayer_2024!", "Lord_of_@#+()", "Pythonist_senior#1",
    "Cyberpunk_2077@#78", "Reerdfffvfrvsxad%!@#^@!$#%^@",
    "gdfan&993432", "hacker_chicken_burger#!@", "balls", "what is a password?", "tvorog",
    "1488", "ordo3424", "hgvb", "root", "poiuytrewq", "1234qwerty", "1q2w3e4r", "qazwsx",
    "Ahmed_2007", "Svetlana_1980", "Olga_1955", "Natasha_Kuzya1970", "Irina_Sochi2014", "Elena_Nikolaevna1965",
    "Anime_lover2000", "Standoff_2015", "Zubenko_Mihail", "Vasya_Pupkin", "Mariush_Polsha",
    "Sam432+@", "password1", "njdcnsiv successful", "Vanya_hacker", "Evgeniy_Schevchuk", "Pavel_Durov", "Elon_Musk",
    "Jeff_Bezos", "Bill_Gates",
    "Mark_Zuckerberg", "Toni_Stark", "12345678910111213141516171819202122232425262728293031323334353637383940",
    "qwertyuiopasdfghjklzxcvbnm1234567890!@#$%^&*()_+-=[]{}/\/\/\|;:'\,.<>?`~",
    "переменная", "sudo hack password", "tell_me_the_password+0-=2340=223=-023@12321",
    "just_bruteforce_it", "Chudo_5Tortik_21", "Gopnikn9_2Syr_33", "Leprechaun3_6Banan", "Vishenka0_1Svetik", "Rybka_8Pirozhok_44", "Kotik7_5Veselchak", "Smesharik1_2Snezhok", "Zaychik3_9Marmelad",
    "Kreml1_8Chudo", "Panda2_4Tsvetik", "Gryzun4_6Malina", "Krevetka5_3Zvezda", "Mishka3_2Vishenka", "Lama6_1Kofe",
    "Cherepashka8_7Yogut", "Svetik9_0Bublik", "Veselchak5_2Pirog", "Zvezda4_3Tortik", "Rybka1_9Chudo", "Marmelad8_5Smesharik",
    "Kotik9_1Zaychik", "Gryzun3_7Malina", "drislomamonta", "kosvarKan00n", "chackakuku", "Petuhi1Koko", "chaynik_2077", "Aleksandr_Dub_1950",
    "Lavroviy_List", "Irina_Guzeevna", "Irina_Semenovna2014@#4#+-", "Olga_Petrovna1955@#--Asus_VivoBook_7245",
    "Natasha_Anton_leeeee@#@@34920--", "1111", "2222","123456789", "333", "444", "555", "0", "122333444455555666666777777788888888999999999",
    "world", "hello", "bye", "America", "roblox", 'love', "Dasha", "Artem", "kot", 'Elena', "Nikita", "Aleksandr",
    "Murad", "M", "Z", "l", "q", "Aleksey", "br", "145", "1111111111111111111111", "000000", "444", "e", "sport", "я админ"]
def generate_password(length=12, num_digits=4, special_characters=False):
    if num_digits > length:
        print("Ты шо,количество цифр не может превышать общую длину пароля.")
        return None

    digits = random.choices(string.digits, k=num_digits)
    remaining_length = length - num_digits
    if special_characters:
        chars = string.ascii_letters + string.punctuation
    else:
        chars = string.ascii_letters + "_"

    other_chars = random.choices(chars, k=remaining_length)
    password_list = digits + other_chars
    random.shuffle(password_list)

    return ''.join(password_list)

def ask_user():
    global choice
    global password
    choice = input("Напишите 1, если вы хотите использовать готовые пароли, \n Напишите 2, если хотите сгенерировать пароль:")
    if choice == "1":
        password = random.choice(passwords)
    elif choice == "2":
        password = generate_password()
    if choice not in ["1","2"]:
        print("Неправильнный ввод")
        ask_user()

attempts = 200
def user_guess():
    global user_inp, attempts
    while attempts > 0:
        user_inp = input("Пароль (Если вы забыли пароль, то это не моя проблема): ")

        if user_inp == "' OR 1 = 1--":
            print("это не OWASP Juice Shop, чувак!")
            time.sleep(1)
            print("Вход в систему от имени админа...")
            time.sleep(3)
            print("SQL-иньекция успешно выполнена!")
            time.sleep(1)
            print("Победа!")
            time.sleep(3)
            exit()

        if user_inp == "sudo hack password":
            print("Взлом системы...")
            time.sleep(1)
            print("Доступ получен!")
            time.sleep(1)
            print("Игра пройдена!!!!!")
            time.sleep(1)
            print("Стоп, я же забыл...")
            time.sleep(1)
            print("[root] password: ")
            time.sleep(1)
            print("У вас нет пароля sudo, попробуйте другой взлом пароля который работает. (подсказка: одна из OWASP Top 10 уязвимостей)")
            ask_user()
            continue

        if user_inp == password:
            print("Отлично, игра пройдена, а вы награждаетесь званием лучшего BruteForce'ра!")
            time.sleep(3)
            exit()
        else:
            print("Неверно, попробуйте ещё раз")
            attempts -= 1
            print(f"Осталось попыток: {attempts}")

    print("Sorry, but too many attempts")
    exit()

ask_user()
user_guess()




