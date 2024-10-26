Event loop (цикл событий) - это механизм, используемый в асинхронном программировании для управления событиями и
обработки асинхронных операций. Event loop обеспечивает эффективное выполнение нескольких задач без блокировки основного
потока выполнения.

Основная идея event loop заключается в том, что программа постоянно ожидает появления новых событий, а затем выполняет
соответствующую обработку каждого события. Вместо того, чтобы ожидать завершения каждой операции, программа передает
операции асинхронный обратный вызов и продолжает обрабатывать другие события.

Event loop обычно состоит из следующих компонентов:

1. Очередь событий (event queue): здесь собираются все события, ожидающие обработки.
2. Цикл событий (event loop): он циклически проверяет очередь событий и обрабатывает каждое событие.
3. Обработчики событий (event handlers): функции или методы, которые выполняются в ответ на определенное событие.

Процесс работы event loop выглядит следующим образом:

1. Инициализация программы и создание event loop.
2. Регистрация обработчиков событий, которые будут вызываться при наступлении определенных событий.
3. Запуск цикла событий.
4. Цикл событий проверяет очередь событий.
5. Если в очереди есть событие, цикл событий вызывает соответствующий обработчик события.
6. Обработчик события выполняет свою логику и может породить новые события или выполнить асинхронные операции с помощью
   колбэков или промисов.
7. Цикл событий продолжает обрабатывать оставшиеся события в очереди.
8. Когда очередь становится пустой, цикл событий переходит в режим ожидания новых событий.
9. Если новое событие появляется в очереди, цикл событий возобновляется и продолжает обработку событий.

Event loop позволяет эффективно использовать ресурсы системы, поскольку программа не блокируется на длительные операции
ожидания. Вместо этого она может продолжать обрабатывать другие события, что особенно полезно в среде с множеством
одновременных операций, таких как веб-серверы или пользовательские интерф