=== uLogin  ===
Donate link: http://ulogin.ru/
Tags: ulogin, login, social, authorization
Tested up to: 2.3.1-pl
Stable tag: 2.0.1

uLogin — это инструмент, который позволяет пользователям получить единый доступ к различным Интернет-сервисам без необходимости повторной регистрации,
а владельцам сайтов — получить дополнительный приток клиентов из социальных сетей и популярных порталов (Google, Яндекс, Mail.ru, ВКонтакте, Facebook и др.)



== Установка ==

Установите пакет через Управление пакетами MODx.

Подробнее:
(если не загружаете из репозитория)
1. Скопировать архив в директорию core\packages\
2. В панели управления MODx перейти на страницу Управление пакетами
- пункт меню для версии 2.3.x: Приложения -> Установщик
             для версии 2.2.x: Система -> Управление пакетами
3. Нажать на отображение стрелки кнопки "Загрузить дополнения", выбрать пункт "Искать пакеты локально"
4. После загрузки пакета uLogin нажать на кнопку "Установить", в открывшемся окне - "Продолжить"



== Дополнительная информация ==

uLogin — это инструмент, который позволяет пользователям получить единый доступ к различным Интернет-сервисам без необходимости повторной регистрации,
а владельцам сайтов — получить дополнительный приток клиентов из социальных сетей и популярных порталов (Google, Яндекс, Mail.ru, ВКонтакте, Facebook и др.)

Чтобы создать свой виджет для входа на сайт достаточно зайти в Личный Кабинет (ЛК) на сайте http://ulogin.ru/lk.php,
добавить свой сайт к списку "Мои сайты" и на вкладке "Виджеты" добавить новый виджет. Вы можете редактировать свой виджет самостоятельно.
Важно! Для успешной работы плагина необходимо включить в обязательных полях профиля поле Еmail в Личном кабинете uLogin.



== Страница настроек uLogin ==

Приложения->uLogin - Здесь Вы можете указать значение параметра "uLogin ID" Ваших виджетов,
а также указать группу и права, для новых, регистрирующихся через uLogin, пользователей.

Важно: По умолчанию новым пользователям присваивается группа "uLogin" с ролью "Member"



== Описание сниппетов ==

Сниппет - [[uLogin.Form]] :  Отображение виджета (аналогичен сниппету [[uLogin]] в режиме, когда пользователь неавторизован)

Пример вызова:
[[!uLogin.Form?&id=`1`]]

Параметры:
id - идентификатор в таблице виджетов uLogin (см. страницу настроек uLogin);
uloginid - параметр uLogin ID из ЛК (то же, что и "uLogin ID" на странице настроек uLogin);
display_always - отображать виджет всегда (1) или только когда пользователь неавторизован (0 - по умолчанию);
show_message - отображать сообщения (1 - по умолчанию) или не отображать для данной формы (0);
ul_id   - атрибут id блока виджета;

redirect - адрес обратной ссылки (по умолчанию формируется автоматически);
callback - js-функция, которая получит токен после авторизации (по умолчанию формируется автоматически);

Далее следуют параметры, для настроек виджета без использования настроек из личного кабинета uLogin:
display - вид виджета (small/panel/window);
fields  - обязательные запрашиваемые поля профиля пользователя (если данных нет, предлагается заполнить);
optional  - необязательные запрашиваемые поля профиля пользователя;
providers - перечень отображаемых провайдеров;
hidden - перечень скрытых провайдеров (other - все скрытые товары);


-------------
Сниппет - [[uLogin.Profile]] :  Пример Личного кабинета, отображает форму синхронизации, соцсети текущего пользователя
   (аналогичен сниппету [[uLogin]] в режиме, когда пользователь авторизован), позволяет указать ссылку на другой чанк.

Пример вызова:
[[!uLogin.Profile?&id=`1`]]

Параметры:
id - идентификатор в таблице виджетов uLogin (тоже, что и в uLogin.Form)
uloginid - параметр uLogin ID из ЛК (тоже, что и в uLogin.Form)
tpl - ссылка на чанк отображения личного кабинета
networks_msg - текст типа "User\'s accounts:"
usr_hello - приветсткие пользователя;
usr_profile - ссылка на профиль пользователя;
signout_url - Ссылка для выхода из профиля;
signout_msg - текст типа "Sign out";


-------------
Сниппет - [[uLogin.Networks]] :  Соцсети текущего пользователя, позволяет удалять аккаунты

Пример вызова:
[[!uLogin.Networks]]

Параметры:
no_delete - не позволяет удалить соцсеть из профиля


-------------
Сниппет - [[uLogin.Message]] :  Вывод сообщения об ошибках/успешном выполнении операции,
   позволяет указать ссылку на другой чанк

Пример вызова:
[[!uLogin.Message]]

Параметры:
id - ссылка на uLogin.Form (аналогично ul_id у uLogin.Form)
tpl - ссылка на чанк отображения вывод сообщений
title - заголовок сообщения
message - текст сообщения
type - тип сообщения (значения 'error'/'success')
display - отображать блок с сообщением (1) или не отображать (0 - по умолчанию)


-------------
Сниппет - [[uLogin]] - для совместимости со старой версией

Важно: использовать сниппет [[uLogin]] не рекомендуется!
Он оставлен только для совместимости с прежними версиями uLogin