#Импорт
from flask import Flask, render_template,request, redirect



app = Flask(__name__)

#Запуск страницы с контентом
@app.route('/')
def index():
    return render_template('index.html')


#Динамичные скиллы
@app.route('/', methods=['POST'])
def process_form():
   
    button_python = request.form.get('button_python')
    button_telegram = request.form.get('button_telegram')
    return render_template('index.html', button_python=button_python,button_telegram=button_telegram)
    

if __name__ == "__main__":
    app.run(debug=True)

    <!DOCTYPE html>
<html lang="ru">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0"
    />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" href="../static/css/style.css" />
    <title>Портфолио</title>
  </head>
  <body>
    <header class="header">
      <nav class="header__nav main-nav">
        <ul class="main-nav__list main-list">
          <li class="main-list__item list-item">
            <a class="list-item__link" href="#home">HOME</a>
          </li>
          <li class="main-list__item list-item">
            <a class="list-item__link" href="#about">ABOUT</a>
          </li>
          <li class="main-list__item list-item">
            <a class="list-item__link" href="#skills">MY SKILLS</a>
          </li>
        </ul>
      </nav>
    </header>
    <main class="main">
      <!-- Секция превью -->
      <section class="main__home home" id="home">
        <h1 class="home__title">Dmitrij Zavoronkovas</h1>
        <p class="home__subtitle">WEB-DEVELOPER, PYTHON PROGRAMMER</p>
      </section>
      <!-- Секция с рассказом о себе -->
      <section class="main__about about" id="about">
        <h2 class="about__title">ABOUT ME</h2>
        <div class="about__info info-block">
          <p class="info-block__text">
            I am 15 years old and my name is Dmitrij i like doing karate and gym and play games with my friends 
            i can do my dairy a bit and spot mistakes when i see one or two 
          </p>
          <img
            class="info-block__img"
            src="../static/img/profile.png"
            alt="me"
            width="250"
            height="250"
          />
        </div>
      </section>
      <!-- Секция со скиллами -->
      <section class="main__skills skills" id="skills">
        <h2 class="skills__title">MY SKILLS</h2>
        <form action="/" method="POST">
          <ul class="skills__list skills-list">
            <li class="skills-list__skill skill">
              <img
                class="skill__img"
                src="../static/img/python.png"
                alt="python"
                width="150"
                height="150"
              />
              <span class="skill__info">Skill info</span>
              <input class="skill__button" type="submit" name="button_python" value="SHOW PROJECT">
            </li>
            <li class="skills-list__skill skill">
              <img
                class="skill__img"
                src="../static/img/telegram.png"
                alt="telegram"
                width="150"
                height="150"
              />
              <span class="skill__info">Skill info</span>
              <input class="skill__button" type="submit" name="button_telegram" value="SHOW PROJECT">
            </li>
            <li class="skills-list__skill skill">
              <img
                class="skill__img"
                src="../static/img/html.png"
                alt="html"
                width="150"
                height="150"
              />
              <span class="skill__info">Skill info</span>
              <input class="skill__button" type="submit" name="button_html" value="SHOW PROJECT">
            </li>
            <li class="skills-list__skill skill">
              <img
                class="skill__img"
                src="../static/img/db.webp"
                alt="SQL"
                width="150"
                height="150"
              />
              <span class="skill__info">Skill info</span>
              <input class="skill__button" type="submit" name="button_db" value="SHOW PROJECT">
            </li>
          </ul>
        </form>
        {% if button_python%}
          <div class="skills__project project" id="project">
              <img class="project__img" src="../static/img/python-project.png" alt="project" width="500">
              <a class="project__link" href="">Открыть на GitHub</a>
          </div>
        {% endif %}  
        {% if button_telegram%}
         <div class="skills__project project" id="project">
              <img class="project__img" src="../static/img/python-project.png" alt="project" width="500">
              <a class="project__link" href="https://github.com/Dima155666/slang-translate/blob/main/main.py%20bot">Открыть на GitHub</a>
          </div>
        {% endif %}
      </section>
      <!-- Секция с формой обратной связи -->
      <section class="main__feedback feedback" id="feedback">
        <h2 class="feedback__title">FEEDBACK</h2>
        <form action="" method="POST" class="feedback__form form">
          <label for="email">
            <input type="email" class="form__input" name="email" id="email" placeholder="Введите E-mail" required>
          </label>
          <label for="text">
            <textarea name="text" class="form__input" id="text" cols="70" rows="10" required placeholder="Комментарий"></textarea>
          </label>
          <button class="form__button" type="submit">ОТПРАВИТЬ</button>
        </form>
      </section>
    </main>
    <!-- Подвал для ссылок на соц-сети -->
     ('https://github.com/Dima155666/homework-15/blob/main/homework%2015')
    <footer>

    </footer>
  </body>
</html>



