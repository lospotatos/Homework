import numpy as np
number = np.random.randint(1,101)    # загадали число
print ("Загадано число от 1 до 100")
for count in range(1,101):         # более компактный вариант счетчика
    if number == count: break    # выход из цикла, если угадали      
print (f"Вы угадали число {number} за {count} попыток.")
def game_core(number):
    '''Сначала устанавливаем любое random число, а потом уменьшаем или увеличиваем его в зависимости от того, больше оно или меньше нужного.
       Функция принимает загаданное число и возвращает число попыток'''
    count = 1
    predict_min = 1 #нижняя граница прогноза
    predict_max = 100 #верхняя граница прогноза
    while True:
      predict_main=int((predict_min+predict_max)/2)#
      if number == predict_main: #Если загаданное число совпадает со спрогнозированным, то заканчиваем цикл
        break
      elif number > predict_main: # если загаданное число больше спрогнозированного, то прибавляем к нижней границе прогноза 1
          predict_min=predict_main+1
      else: 
          predict_max=predict_main-1 # если загаданное число меньше спрогнозированного, то уменьшаем верхнюю границу прогноща на 1
      count+=1 #после одной итерации увеличиваем счетчик попыток на 1
    return(count) # выход из цикла, если угадали      
        
def score_game(game_core):
    '''Запускаем игру 1000 раз, чтобы узнать, как быстро игра угадывает число'''
    count_ls = []
    np.random.seed(1)  # фиксируем RANDOM SEED, чтобы ваш эксперимент был воспроизводим!
    random_array = np.random.randint(1,101, size=(1000))
    for number in random_array:
        count_ls.append(game_core(number))
    score = int(np.mean(count_ls))
    print(f"Ваш алгоритм угадывает число в среднем за {score} попыток")
    return(score)

score_game(game_core)
