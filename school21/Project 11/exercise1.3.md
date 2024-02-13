# Виды тестирования
## Определи типы тестирования, которые, на твой взгляд, необходимо провести для данного приложения (не меньше трёх). 

## К каждому типу проводимого тестирования необходимо дать краткую характеристику: что за вид тестирования и как он будет проводится
***

### 1. Функциональное тестирование:  
Функциональное тестирование – это вид тестирования, направленный на проверку соответствия функций программного обеспечения определенным требованиям и спецификациям. Этот процесс включает в себя тестирование отдельных компонентов, интерфейсов и взаимодействий в пределах приложения, чтобы убедиться в правильности выполнения всего функционала: от обработки ввода данных до взаимодействия с другими системами и вывода результатов работы. Проводится как вручную, так и с помощью автоматических инструментов.  

Процесс проведения: 
1. Подготовка Тестовых Сценариев и Кейсов: Создаются документироемые сценарии тестирования, чтобы охватить все возможные ситуации использования функционала – включая граничные условия и исключительные сценарии.  

2. Настройка Тестовой Среды: Настраивается среда, максимально приближенная к реальным условиям эксплуатации, где и будет проходить тестирование ПО.  

3. Выполнение Тестов: Пошагово выполняются заранее подготовленные тестовые кейсы и фиксируются результаты – успешно ли функция справилась с задачей в соответствии с требованиями.  

4. Регистрация Багов: Если обнаружены баги, они регистрируются в трекере задач для дальнейшего исправления разработчиками.  

5. Ретестирование и Регрессионное Тестирование: После исправления обнаруженных ошибок проводится повторное тестирование конкретного функционала (ретестирование) и проверка того, не повлияли ли изменения на другие части системы (регрессионное тестирование).  

6. Анализ Результатов и Отчётность: По окончании тестирования составляется отчет, в котором содержится анализ проведенных тестов, обнаруженных ошибок и рекомендации.  

### 2. Тестирование юзабилити:  
Юзабилити тестирование - это метод оценки продукта с точки зрения удобства и эффективности использования конечными пользователями. Основной его целью является установление того, насколько легко пользоваться функциями программы, как быстро пользователь может освоить интерфейс, находить необходимую информацию и выполнять задачи. Это тестирование также включает изучение реакций пользователей на различные аспекты продукта и корректировку дизайна и функциональности для максимального удобства использования.  

Процесс проведения:  
1. Планирование: Определяются цели тестирования, аудитория продукта и сценарии использования. Разрабатывается план, в который входит выбор методик тестирования и сбора данных.  

2. Набор Участников: Отбираются реальные пользователи, которые представляют целевую аудиторию продукта. Часто количество участников не большое, от 5 до 10, но они в достаточной мере представляют конечного пользователя.  

3. Создание Тестовых Сценариев: Разрабатываются сценарии действий, которые участники будут выполнять во время тестирования. Они должны охватывать различные функциональные аспекты.  

4. Проведение Тестирования: Организуется тестирование, в ходе которого участники выполняют задания, а наблюдатели фиксируют сложности, с которыми пользователи сталкиваются, их вербальные и невербальные реакции.  

5. Сбор и Анализ Данных: Результаты тестирования оцениваются на основе наблюдений, записанных комментариев, видео/аудио записей, а также (при соответствующих условиях) метрик, таких как время выполнения задачи и количество ошибок.  

6. Доработка Дизайна: На основе анализа данных разработчики вносят изменения в продукт с целью улучшения его юзабилити.  

7. Повторное Тестирование: Исправленный продукт может быть снова протестирован для удостоверения, что все проблемы устранены и улучшения положительно влияют на пользовательский опыт.  

### 3. Компатибилити тестирование:  
Компабилити тестирование — это метод проверки работы программного продукта в разных средах. Включает тестирование на различных устройствах, операционных системах и браузерах для обеспечения совместимости и корректной функциональности приложения в этих условиях.  

Процесс проведения:  
1. Определение Параметров: Разработка списка параметров среды, с которыми должно быть совместимо ПО, включая операционные системы, браузеры, устройства, версии программного обеспечения и аппаратное обеспечение.  

2. Планирование Тестирования: Создание детального плана тестирования, который включает матрицу тестирования совместимости для отслеживания сочетаний разных сред, которые необходимо протестировать.  

3. Настройка Тестовых Сред: Подготовка или настройка необходимых тестовых сред, иногда с использованием виртуальных машин или эмуляторов для эффективного тестирования различных конфигураций.  

4. Выполнение Тестов: Проведение серии тестов, чтобы оценить, как ПО функционирует в каждой из заранее определенных сред. Это может включать установку, запуск приложений, выполнение различных задач внутри приложений и оценку производительности.  

5. Фиксация Результатов: Запись результатов тестирования, включая особые условия или шаги, при которых возникают проблемы.  

6. Анализ Проблем: Определение, являются ли обнаруженные во время тестирования проблемы критическими или могут быть оставлены без изменений. Приоритизация ошибок для разработки решений.  

7. Устранение Найденных Проблем: Передача информации о проблемах разработчикам для внесения необходимых изменений и улучшений.  

8. Повторное тестирование: Повторное тестирование ПО после внесения изменений для убеждения в том, что ранее обнаруженные проблемы успешно устранены и что новые изменения не привели к дополнительным ошибкам в совместимости.  

9. Отчетность и Рекомендации: Подготовка окончательного отчета о состоянии совместимости ПО с рекомендациями и решениями по улучшению взаимодействия с целевыми средами.  

### 4. Локализационное тестирование:  
Локализационное тестирование — это процесс проверки ПО с целью удостовериться, что оно адаптировано для использования в конкретной целевой культурной среде и локализации. Включает проверку переводов, форматов дат, валют, правильности работы с текстом и других культурно-специфических факторов. Цель — обеспечить удобство и эффективность использования продукта местной аудиторией.  

Процесс проведения:  
1. Планирование Тестирования: Устанавливаются цели тестирования, выбираются целевые локализации и культуры для проверки. Разрабатывается детальный план тестирования, включающий в себя специфические кейсы и сценарии использования продукта в целевом регионе.  

2. Подготовка Тестовой Среды: Создается тестовая среда, которая эмулирует локализованные операционные системы, браузеры, настройки локалей и другие параметры, связанные с целевым языком и культурой.  

3. Лингвистическое Тестирование: Проверяется корректность перевода текста, включая орфографию, грамматику, пунктуацию и соответствие контексту.  

4. Тестирование инретфейса: Оценивается интерфейс и его элементы (кнопки, меню, диалоговые окна), чтобы убедиться в том, что переведенный текст корректно отображается и не выходит за границы предусмотренных элементов интерфейса.  

5. Функциональное Тестирование: Помимо перевода, проверяется функциональность продукта, чтобы убедиться, что локализованные версии работают так же, как и оригинальная.  

6. Культурное Тестирование: Обеспечивается соответствие продукта культурным особенностям целевого рынка, включая форматы дат, валют, адресов, телефонных номеров и другие локальные стандарты.  

7. Проверка Легализации Данных: Удостоверение, что весь локализованный контент соответствует законодательству страны (цензура, использование символов, изображений и т.д.).  

8. Документация и Отчётность: Сбор обнаруженных проблем, их категоризация и оформление отчёта для команды разработчиков для дальнейшего устранения ошибок.  

9. Исправление И Оценка Исправлений: Разработчики исправляют найденные недочеты, после чего происходит повторное тестирование, чтобы убедиться в успешности внесенных изменений.  