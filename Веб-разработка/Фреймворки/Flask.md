>Микрофреймворк для [[Python]].

Строгая структура проекта на flask:
```
Project\
	templates\
		index.html
		account.html
	static\
		css\
			style.css
		img\
			flower.png
			search.svg
		js\
			script.js
	instance\
		database.db
	app.py
```

> [!NOTE] Важно!
> Наименование файлов может быть любым, но их расположение и наименование директорий (за исключением директории самого проекта) должно быть строго таким, как на примере выше.


# Начало работы

Установка библиотеки через CMD:
```
pip install flask
```

Загружаем библиотеки:
```
from flask import Flask, render_template
from flask_sqlalchemy import SQLAlchemy
```

Настройка проекта:
```
app = Flask(__name__)
app.secret_key = b'секретный ключ'
```

Настройка БД:
```
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///database.db'
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False
db = SQLAlchemy(app)
```

Переход на страницу:
```
@app.route('/')  
def page_home():  
    return render_template('index.html')
```
