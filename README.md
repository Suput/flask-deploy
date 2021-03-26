# Настройка [Python](https://www.python.org/downloads/) сервера под [Heroku](https://dashboard.heroku.com/apps) развертывание

## Собственно развертывание
1. Создать файл с логикой вашего сервера
    > Допустим файл будет называться `main.py`
2. Обязательно указать, что порт для сервера необходимо брать из переменной окружения
    > [Ссылка на урок](https://lyceum.yandex.ru/courses/352/groups/2552/lessons/2055/materials/4802)  
    ```python
    if __name__ == '__main__':
       port = int(os.environ.get("PORT", 5000))
       app.run(host='0.0.0.0', port=port)
    ```
3. Создать `Procfile` в корне приложения, в котором указать, как запустить наше приложение  
    ```bash
    web: python main.py 
    ```
4. Создать `requirements.txt` в корне приложения, в котором указать все использованные модули и их версии  
    > Данный файл крайне желательно делать через инструменты Python
    ```bash
    pip freeze > requirements.txt
    ```
5. Запушить ваше приложение на [Github](https://github.com/)
6. Создать и развернуть приложение на [Heroku](https://dashboard.heroku.com/apps) согласно [учебнику](https://lyceum.yandex.ru/courses/352/groups/2552/lessons/2055/materials/4802#3)

## Как запустить данное приложение у себя на компьютере
1. Создание [виртуального окружения](https://docs.python.org/3/library/venv.html) для Python
    ```bash
   python -m venv venv
   ```
2. Установка модулей
    - Переместитесь в виртуальное окружение  
        Windows:
        ```bash
        .\venv\Scripts\activate
        ```
        Linux:
        ```bash
        ./venv/Scripts/activate
        ```
    - Установите модули из файла `requirements.txt`
        ```bash
      pip install -r requirements.txt
      ```
3. Запустите проект
    ```bash
   python main.py
   ```