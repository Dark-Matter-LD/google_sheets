Скрипты на Python, которые:
1. Получают данные с документа при помощи Google API, сделанного в Google Sheets:
 - Авторизуются в системе googlesheets и googledrive;
 - Создают таблицу в googlesheets;
 - Дают доступ юзеру с правами редактирования;
 - Реализована возможность передачи прав владения другому юзеру (с указанием почты);
 - Добавляет входные данные в google-таблицу;
 2. Парсят курс доллара с API Центробанка РФ;
 3. Записывают полученные данные из гугл таблицы в СУБД PostgreSQL:
 - Открывают таблицу в googlesheets, вытаскивают все данные в виде словаря, словарь преобразуют в dataframe;
 - В Dataframe добавляет колонку "Стоимость в рублях": Спаршенный курс доллара * колонка "Стоимость в долларах"
 - Записывает dataframe в Postgres при помощи SqlAlchemy.
  - Скрипт работает постоянно для обеспечения обновления данных в онлайн режиме (запись каждые n-секунд)
  
  Используемые библиотеки:
  gspread, pandas, sqlalchemy, time, httplib2, apiclient, oauth2client
