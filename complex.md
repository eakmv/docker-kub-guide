---
description: Multi-container application.
---

# complex

Данное приложение вычисляет число Фиббоначи.

![](.gitbook/assets/image%20%289%29.png)

  Рассмотрим специально усложненную архитектуру приложения.

![](.gitbook/assets/image%20%286%29.png)

Так выглядит само приложение, видим, что в Postgres хранятся одни значения, а в Redis - другие.

![](.gitbook/assets/image%20%283%29.png)

Когда пользователь нажимает Submit происходит следующее:. Пользовательнажимет кнопку React App делает API-запрос к Express серверу. Express сервер смотрит какое число ему передали и записывает его в Postgres, также это число передается в Redis. При поступлении нового числа в Redis вызывается Worker, который считает значение Фиббоначи и обратно возвращает резлуьтат в Redis.

![](.gitbook/assets/image.png)

![&#x43D;&#x430;&#x441;&#x442;&#x440;&#x43E;&#x439;&#x43A;&#x430; nginx](.gitbook/assets/image%20%2821%29.png)

![nginx](.gitbook/assets/image%20%2818%29.png)

![](.gitbook/assets/image%20%2816%29.png)

