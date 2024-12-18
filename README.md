# Лабораторна робота №6 з дисципліни «Комп’ютерні мережі» «Засвоєння принципів перетворення DNS-імен в IP-адреси»

## Мета роботи
Використовуючи програму моделювання комп’ютерних мереж засвоїти принципи адресації на канальному та мережевому рівнях моделі OSI, принципи динамічного призначення IP-адрес і принципів перетворення DNS-імен в IP-адреси.

## План виконання лабораторної роботи
Завдання №1. Побудова локальної мережі з двома робочими станціями.
Завдання №2. Засвоєння принципів адресації на канальному і мережевому рівнях.
Завдання №3. Засвоєння принципів динамічного призначення IP-адрес.
Завдання №4. Засвоєння принципів перетворення DNS-імен в IP-адреси.
Завдання №5. Ознайомлення з відомостями про структуру перехресного кабеля. 

## Завдання

### Завдання №1
* Відкрити програму Cisco Packet Tracer, вибрати End Devices і перетягнути мишкою на робоче поле дві робочі станції 
* Далі потрібно з’єднати дві робочі станції кабелем. Для цього вибрати Connections і перехресний кабель 
* Причини використання перехресного кабелю описані в розділі «Використання перехресного кабелю»
* Мишкою вибрати першу робочу станцію і підключити кабель до FastEthernet0 
* Перетягнути мишкою з’єднання на другу робочу станцію і вибрати також FastEthernet0 
* В результаті можна побачити, що з’єднання між робочими станціями відбулося – засвітилися зелені індикатори link
* Тепер потрібно вказати статичну IP-адресу комп'ютера. Для цього зробити подвійний клік по першій робочій станції, перейти в меню Desktop і вибрати режим IP Configuration 
* Після цього задати IP-адресу і маску.
* На другій робочій станції виконати такі ж дії, але вказати IP-адресу 192.168.1.2
* Тепер на другій робочій станції вибрати режим Command Promt 
* Відкривається командний рядок. З командного рядка виконати команду ping 192.168.1.1, в результаті виконання якої видно, що зв’язок між робочими станціями встановлений.
* На станції PC1 створено пакет (конверт), який чекає початку просування його мережею. Запустити просування пакету покроково можна, натиснувши на кнопку «Capture/Forward» (Вперед) у вікні симуляції. Якщо натиснути на кнопку «Auto Capture/Play» (відтворення), то можна спостерігати весь цикл проходження пакету мережt.. В закладці «Event list» (Список подій) можна бачити успішний результат «пінгування» 

### Завдання №2
* За допомогою програми Packet Tracer побудувати мережу.
* Призначити робочим станціям IP-адреси та маску. Перші три байти IP-адрес збігаються з адресою мережі, а останній байт дорівнює відповідно 1 та 2.
* Визначити MAC-адресу кожної робочої станції за допомогою команди ipconfig /all з командного рядка.
* На робочій станції PC1 з командного рядка виконати команду arp –a. Зафіксувати отриманий результат.
* На робочій чтанції PC1 з командного рядка виконати команду ping на адресу счтанції PC2, після чого знову виконати команду arp –a. Пояснити отриманий результат.
* На робочій станції PC1 з командного рядка виконати команду arp –d. Пояснити призначення ключа –d.
* Перейти в режим "Simulation". Із командного рядка робочої станції PC1 виконати команду ping на IP-адресу станції PC2. На «Simulation panel» натиснути кнопку «CaptureForward». Пояснити призначення пакетів, що відправляються зі станції PC1. Натиснути кнопкою миші на кожному із створених пакетів і переглянути їх вміст. Звернути увагу на адреси відправника та отримувача. Натискаючи на «CaptureForward» прослідкувати за формуванням та передачею створених пакетів мережею, одночасно спостерігаючи за командним рядком.
* Пояснити призначення ARP-пакету.
* Зробити висновки.

### Завдання №3
* За допомогою програми Packet Tracer побудувати мережу
* Перейти до режиму «Simulation» .
* Вибрати режим конфігурування сервера. Призначити IP-адресу, перші три байти якої збігаються з адресою мережі, а останній байт дорівнює 100.
* У режимі конфігурування перейти до вкладки DHCP і налаштувати таким чином: у полях Default Gateway та DNS Server ввести адреси, перші три байти яких збігаються з адресою мережі, а останній байт відповідно дорівнює 254 та 253. У полі Start IP Adress ввести адресу, перші три байти якої збігаються з адресою мережі, а останній дорівнює 10. Значення поля Maximum number of Users встановити рівним 15. 
* На PC1 включити динамічний режим конфігурування адрес (DHCP). Впевнитись, що поле IP-адреси, маска підмережі, шлюз за замовчуванням та DNS-сервер порожні. Не закриваючи вікна конфігуровання PC1 натиснути кнопку «CaptureForward». 
* Переглянути вміст пакета, що передав PC1, звернути увагу, що вказано в полі адреси отримувача, порівняти вміст пакетів «Inbound PDU» та «Outbound PDU». Визначити, яку інформацію передав DHCP-сервер станції. 
* Послідовно натискаючи на кнопку «CaptureForward» спостерігати за рухом пакетів та аналізувати їх вміст. Дочекатися завершення конфігурування. На робочій станції PC1 переглянути вміст полів: IP- адреса, маска підмережі, шлюз за замовчуванням та DNS- сервер.
* Зробити висновки.

### Завдання №4
* За допомогою програми Packet Tracer побудувати мережу. Призначити такі IP-адреси: перші три байти всіх адрес відповідають адресі мережі, останній байт PC1 – 1; DNS- сервера – 253; HTTP-сервера – 252.
* На PC1 в полі DNS вказати відповідну адресу.
* На DNS-сервері в вкладці DNS додати запис, в якому в полі Domain Name вказати ім’я scs.kpi.ua, а в полі IP-Address – адресу HTTP-сервера.
* Перейти до режиму «Simulation».
* На PC1 в командному рядку виконати команду ping, вказавши доменне ім’я scs.kpi.ua та натиснути кнопку «Capture/Forward».
* Натискати кнопку «Capture/Forward», поки на PC1 не буде сформований DNS-запит. Пояснити призначення ARP-пакетів, які були сформовані на попередніх кроках.
* Коли DNS-запит надійде на сервер, переглянути його вміст (Inbound PDU) та вміст відповіді (Outbound PDU). Пояснити інформацію, що міститься в цих пакетах.
* Натиснути кнопку «Capture/Play» та дочекатися завершення виконання команди, пояснити причину утворення всіх пакетів.
* Перейти в режим «Real Time».
* У налаштуваннях DNS-сервера відключити DNS-сервіс. У полі URL веб браузера  на PC1 набрати IP-адресу HTTP-сервера. Зафіксувати результат. Замість IP-адреси HTTP-сервера набрати його DNS-ім’я. Пояснити отриманий результат. Не закриваючи вікна веб браузера включити DNS-сервіс. Зафіксувати зміни, що відбулися.

### Завдання №5
* Навести теоретичні відомості про кабель типу «вита пара». Використання  перехресного кабелю
