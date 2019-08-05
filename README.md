# Веб Push-уведомления в Firefox

Веб Push-уведомления позволяют веб-сайтам информировать пользователей о новых сообщениях или обновленном контенте. Во время работы с Firefox пользователь может получать в браузере уведомления от тех веб-сайтов, которым были предоставлены разрешения на отправку уведомлений. Пользователь может управлять уведомлениями, включая или отключая функцию их отправки.  

![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2017-10-18-05-45-38-20e1d7.png)

**Содержание**

- [Уведомления об обновлении](https://github.com/AnastasiaToropova/AnastasiaN/edit/new_branch/README.md "Уведомления об обновлении")
- [Что такое Веб Push?](https://github.com/AnastasiaToropova/AnastasiaN/edit/new_branch/README.md "Что такое Веб Push?")
- [Как это работает?](https://github.com/AnastasiaToropova/AnastasiaN/edit/new_branch/README.md "Как это работает?")
- [Какую информацию мне необходимо предоставить сайту?](https://github.com/AnastasiaToropova/AnastasiaN/edit/new_branch/README.md "Какую информацию мне необходимо предоставить сайту")
- [Какую информацию использует Firefox, чтобы обеспечивать работу Web Push?](https://github.com/AnastasiaToropova/AnastasiaN/edit/master/README.md "Какую информацию использует Firefox, чтобы обеспечивать работу Web Push?")
- [Как запретить отправку уведомлений для определенного сайта?](https://github.com/AnastasiaToropova/AnastasiaN/edit/master/README.md "HКак запретить отправку уведомлений для определенного сайта?")
- [Как добавить Веб Push на свой сайт?](https://github.com/AnastasiaToropova/AnastasiaN/edit/master/README.md "Как добавить Веб Push на свой сайт?")
- [Как запратить Firefox запрашивать разрешение на отправку уведомлений?](https://github.com/AnastasiaToropova/AnastasiaN/edit/master/README.md "Как запратить Firefox запрашивать разрешение на отправку уведомлений?")

## Уведомления об обновлении

Начиная с версии 44, Firefox может отображать уведомления на экране, даже если сайт не загружен на данный момент. Используя Push API  [W3C standard](https://www.w3.org/TR/push-api/), Firefox получает Push-сообщение и может отображать уведомления (с разрешения пользователя) в любое время. Сайты также могут использовать Push для обновления данных в фоновом режиме, не показывая уведомление пользователю. Если вы уже дали разрешение сайту для отправки уведомлений, сайт будет иметь возможность использовать Push API. Вы можете разрешить или запретить веб-сайтам отправлять уведомления в фоновом режиме, выполнив следующие действия:

1. Нажмите на значок ![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2016-02-25-12-29-33-78136e.png) чтобы вызвать [Центр управления](https://support.mozilla.org/en-US/kb/control-center-site-privacy-and-security-firefox);

2. Нажмите на кнопку в правом углу поля *Permissions tab*.
![](http://5o.f.mf-image.ru/d/eyJ0IjoiMjAxOS0wNy0yOVQxNTowOToyMy4wNjg3ODM2WiIsInRtIjoxNSwiYmQiOjEsImZkIjo1ODg3NDMxLCJyZiI6bnVsbCwic2wiOjAsImZuIjpudWxsLCJyIjoiaHR0cHM6Ly9teS1maWxlcy5ydS81ZTVzaHAiLCJsIjpudWxsfQ,,.23614028C46610B1137750B7774EB394./2222.png)

3. Поставьте галочку, если вы не хотите получать уведомления от Firefox в фоновом режиме. В обратном случае, снимите галочку.

![](http://a1.f.mf-image.ru/d/eyJ0IjoiMjAxOS0wNy0yOVQxNTo0NDoyNC44MDUxNDYzWiIsInRtIjoxNSwiYmQiOjEsImZkIjo1ODg3NDM0LCJyZiI6bnVsbCwic2wiOjAsImZuIjpudWxsLCJyIjoiaHR0cHM6Ly9teS1maWxlcy5ydS9qeWptNXgiLCJsIjpudWxsfQ,,.1BA3759115CEF724780AD8674BC72156./3333.png)

## Что такое Веб Push?

Веб Push - это дополнительная функция, которая позволяет веб-сайтам отправлять вам сообщения, даже если сайт не загружен. Сайты могут использовать эту функцию, чтобы предоставлять вам уведомления или обновлять данные в фоновом режиме.

Например, вы можете подписаться на получение уведомлений о новых акциях или предложениях от ваших любимых интернет-магазинов. Вы можете подписаться на получение уведомлений от различных веб-сайтов: к примеру, сайт, содержащий информацию о концертах, может предложить вам получение уведомления о выступлении любимой группы; вы позволяете этому сайту уведомить вас, и неделю спустя вы получаете уведомление о том, что ваша группа находится в туре.

Вы будете получать сообщения только с тех сайтов, которым вы дали на то разрешение.

## Как это работает?

Прежде всего, необходим установить [Service Worker](https://developer.mozilla.org/ru/docs/Web/API/Service_Worker_API) - фоновую веб-страницу с ограниченным набором функциональных возможностей, которая может подписываться на Push-сервис. Сайт будет отправлять push-сообщения через службу Веб Push Mozilla в браузер, который обработает это сообщение и отобразит уведомления на экране.

![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2016-01-22-13-08-43-059641.png)

Щелчок по уведомлению может открыть веб-сайт или переключиться на вкладку этого сайта, если она загружена.

## Какую информацию мне необходимо предоставить сайту?

Сайт, которому было предоставлено разрешение, может отправлять вам push-сообщения в фоновом режиме. Квота ограничивает количество push-сообщений без уведомления на экране, которые сайты могут вам отправить. Если веб-сайты превышают квоты, их push-сообщения будут отключены и пользователь должен будет снова зайти на сайт, чтобы снова на них подписаться. Веб Push-уведомления не позволяют веб-сайтам напрямую определить ваш IP-адрес.

## Какую информацию использует Firefox, чтобы обеспечивать работу Web Push?

Firefox поддерживает активное соединение со службой Push-уведомлений в целях получения push-сообщений до тех пор, пока он запущен. Соединение завершается после закрытия Firefox. На нашем сервере мы храним рандомизированный идентификатор для вашего браузера, наряду со рандомизированным идентификатором для каждого сайта, которому вы дали на то разрешение.

На Firefox для настольного компьютера, службы Push-уведомлений управляются Mozilla. Firefox для Android использует комбинацию службы Веб Push от Mozilla и платформы Cloud Messaging от Google для доставки уведомлений в Firefox для Android.

В обоих случаях, push-сообщения шифруются согласно [IETF spec](https://tools.ietf.org/html/rfc8030) и только ваша копия Firefox может их расшифровать. Зашифрованные сообщения хранятся на сервере, пока они не будут доставлены или просрочены.

## Как запретить отправку уведомлений для определенного сайта?
 
Веб Push-уведомления по умолчанию отключены в Firefox. Сайт не может отправить вам push-сообщение без вашего разрешения. Чтобы отказать отдельному сайту в праве отправлять вам push-сообщения:
 
1. Нажмите на кнопку ![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2017-10-22-15-37-15-18c775.png), затем нажмите на кнопку **Настройки**.

![](http://8g.f.mf-image.ru/d/eyJ0IjoiMjAxOS0wNy0yOVQxNTo0MDoyNi44MDM1MTM0WiIsInRtIjoxNSwiYmQiOjEsImZkIjo1ODg3NDUxLCJyZiI6bnVsbCwic2wiOjAsImZuIjpudWxsLCJyIjoiaHR0cHM6Ly9teS1maWxlcy5ydS9vbGJzOWEiLCJsIjpudWxsfQ,,.825F01B0A9C6229A17F4FAAB3459A56B./4.png)

2. Выберите панель *Приватность и защита* и прокрутите до раздела *Разрешения*.

3. Нажмите кнопку **Настройки…** в поле *Уведомления*.

![](http://lr.f.mf-image.ru/d/eyJ0IjoiMjAxOS0wNy0yOVQxNTo0OToyOC4wNzU1MTA3WiIsInRtIjoxNSwiYmQiOjEsImZkIjo1ODg3NDYzLCJyZiI6bnVsbCwic2wiOjAsImZuIjpudWxsLCJyIjoiaHR0cHM6Ly9teS1maWxlcy5ydS9mZ3JheTAiLCJsIjpudWxsfQ,,.DA2588ABFCD22F008DE25F51263E1109./5.png)
4. Выберите нужный веб-сайт, затем нажмите на кнопку **Удалить веб-сайт**

Чтобы отказать все сайтам в праве отправлять вам push-сообщения, выполните указанные выше шаги, но вместо выбора определённого сайта нажмите кнопку **Remove All Websites**. Веб-сайты не смогут отправлять вам сообщения и им нужно будет запросить у вас разрешение, чтобы отправить их в будущем.

|**Чтобы остановить уведомления для определенной веб-страницы (требуется перезагрузка страницы):** Нажмите на значок ![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2016-02-25-12-29-33-78136e.png), чтобы вызвать [Control Center](https://support.mozilla.org/en-US/kb/control-center-site-privacy-and-security-firefox), найдите поле *Отправка уведомлений* в разделе *Разрешения* и нажмите на кнопку **x** рядом с опцией *Разрешить*, чтобы запретить веб-сайтам отправлять уведомления.|
|----------------------------------------------------------------------------------------------------------------------|

## Как добавить Веб Push на свой сайт?

Статья [Push API specification](https://developer.mozilla.org/docs/Web/API/Push_API) объясняет, как создать Service Worker и отправлять push-сообщения.

## Как запратить Firefox запрашивать разрешение на отправку уведомлений? 

Если сайт сообщает Firefox, что он хочет показывать уведомления по умолчанию, Firefox спрашивает, хотите ли вы дать разрешение? Вы можете настроить Firefox на автоматическое отклонение разрешения без запроса. Даже после этого вы можете делать исключения для отображения уведомлений тем сайтам, которым вы доверяете или использования push-функций.
1. Нажмите на кнопку ![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2017-10-22-15-37-15-18c775.png) и выберите *Настройки*.
2. Выберите панель *Приватность и защита* и прокрутите до раздела *Разрешения*.
Нажмите на кнопку **Настройки…** справа от поля *Уведомления*.

![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2018-04-09-09-06-49-fc7acb.png)

3. Поставьте галочку в поле *Block new requests asking to allow notifications*, затем нажмите кнопку **Сохранить изменения**.
              


