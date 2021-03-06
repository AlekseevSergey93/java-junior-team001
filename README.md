# Метафора
Быстрый и лаконичный консольный чат для поклонников CLI.


# Функциональные требования

## Посылка сообщения
### User Story
Я, как пользователь, хочу послать сообщение, чтобы его увидели другие пользователи чата.
### Acceptance Test
#### Given
- Запущены клиентское и серверное приложения.
#### When
- Я печатаю и отсылаю сообщение в чат с помощью команды "/snd <сообщение>"
#### Then
- Я вижу свое сообщение с датой и временем.
- Другие пользователи видят мое сообщение с датой и временем.

## Просмотр полной истории
### User Story
Я, как пользователь, хочу видеть все сообщения за все время существования чата, чтобы найти нужное мне сообщение.
### Acceptance Test
#### Given
- Запущены клиентское и серверное приложения.
#### When
- Я ввожу команду "/hist".
#### Then
- Я вижу полный список всех сообщений чата с датой и временем.

 Нефункциональные требования

## Usability
- Процесс ввода сообщения не должен прерываться приходящими сообщениями.
- Запуск клиента одним скриптом.
- Запуск сервера одним скриптом.
- Лаконичный простой консольный интерфейс.
- Для лаконичности размер сообщения ограничен 150 символов.

## Performance
- Система должна гарантировать throughput 0,1k сообщений в секунду (без учета сетевой latency).
- Система должна гарантировать response time не более 0.2 сек
- Система должна гарантировать емкость до 1k работающих одновременно пользователей.

## Consistency
- Пользователи видят сообщения в том же порядке, в котором они их посылают.
- История храниться в том же порядке, в котором пользователи посылали сообщения.
- История сообщения актуальна.
- Вывод истории сообщений приоритетнее вывода текущих сообщений.
- Вывод текущих сообщений актуален.

## Fail-over
- Допускаются отказы системы пользователю в случае отказов сети и подсистемы хранения.


# Внутренние регламенты

- Все решения по дизайну обоснованы и задокументированы в javadoc
- Публичный API задокументирован в JavaDoc
- Cборка только через maven
- Все ошибки и отказы журналируются в консоль
- Код читабелен и соответствует Java Code Style Convention
- Отсутствуют dead code и dead comments
- Все рефакторинги делались только автоматически
- Успешное прохождение статического анализа кода в IDEA: отсутствие файндингов
