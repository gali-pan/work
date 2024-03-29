# Задание №1 

## По уровню тестирования

### Модульное тестирование

1. Определение: Тестирование отдельных модулей или компонентов программного обеспечения.
2. Цель: Убедиться, что каждый модуль функционирует правильно в изоляции.
3. Особенности: Используются инструменты и фреймворки для тестирования кода; обычно выполняется разработчиками; может включать mock-объекты и стабы для имитации взаимодействия с другими модулями.
4. Пример: Тестирование функции сложения в калькуляторе, чтобы убедиться, что она возвращает правильный результат при вводе двух числовых аргументов.

### Интеграционное тестирование

1. Определение: Проверка взаимодействия между интегрированными модулями или компонентами системы.
2. Цель: Обнаружение дефектов в интерфейсах и взаимодействии между интегрированными частями.
3. Особенности: Обычно проводится после модульного тестирования; может использовать стабы и драйверы для имитации взаимодействия между модулями.
4. Пример: Тестирование взаимодействия между системой управления базой данных и бизнес-логикой приложения, чтобы убедиться, что данные корректно передаются и обрабатываются.

### Системное тестирование:

1. Определение: Тестирование комплекса программного обеспечения в целом.
2. Цель: Подтвердить, что система удовлетворяет всем заданным требованиям и спецификациям.
3. Особенности: Это высокоуровневый вид тестирования, включает в себя функциональные и нефункциональные тесты, обычно проводится на окружении, максимально приближенном к продуктивному.
4. Пример: Проверка работоспособности веб-платформы интернет-магазина, включая процессы регистрации, поиска товаров, оформления и оплаты заказа, а также функционирования сервисов поддержки клиентов.

## По степени автоматизации

### Ручное тестирование

1. Определение: Процедура проверки программного обеспечения, где тесты выполняются вручную тестировщиком без использования автоматизированных инструментов.
2. Цель: Обнаружение ошибок и дефектов, которые не были выявлены автоматическими тестами, и оценка пользовательского опыта.
3. Особенности: Ручное тестирование требует значительных временных ресурсов, но позволяет лучше понять реальный пользовательский опыт и тестировать сценарии, которые сложно автоматизировать.
4. Пример: Ручное проведение серии тестовых сценариев для проверки функциональности новой формы обратной связи на сайте, включая заполнение поля с электронной почтой, выбор темы запроса и отправку сообщения через форму.

### Полуавтоматизированное тестирование

1. Определение: Тестирование, при котором сочетаются элементы автоматического и ручного подходов, используя программное обеспечение для определения тестовых сценариев или выполнения отдельных задач, но при этом требующее участия человека для управления процессом тестирования или анализа результатов.
2. Цель: Уменьшить время и усилия, затрачиваемые на тестирование, повысить скорость выявления дефектов и повторяемость тестов, сохраняя при этом элемент контроля и владения процессом со стороны тестировщика.
3. Особенности: Задачи тестирования распределяются между человеком и программными средствами таким образом, чтобы максимизировать преимущества обоих подходов, часто требуется предварительная настройка тестовых скриптов, которые затем используются в комбинации с ручным управлением.
4. Пример: Использование программы для автоматического генерирования тестовых данных, которые затем вручную вводятся оператором в форму на веб-сайте, для проверки корректности обработки разнообразных входных данных системой.

### Автоматизированное тестирование

1. Определение: Применение специализированного программного обеспечения для выполнения тестов и сравнения фактических результатов с заранее определёнными ожиданиями без непосредственного участия человека.
2. Цель: Упрощение процесса тестирования и повышение его эффективности, обеспечение возможности быстро и часто проводить тесты, особенно при регрессионном тестировании.
3. Особенности: Подходит для повторяемых тестовых случаев; требует инвестиций времени и ресурсов для начальной настройки, но в долгосрочной перспективе экономит время; помогает в поиске дефектов при помощи проведения большого количества тестов в короткие сроки.
4. Пример: Настройка набора скриптов для автоматической проверки входа пользователя в систему посредством использования различных комбинаций имени пользователя и пароля, а также верификация правильности сообщений об ошибках при вводе некорректных данных. 
