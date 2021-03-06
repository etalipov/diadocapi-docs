MoveDocuments
=============

Имя ресурса: **/MoveDocuments**

HTTP метод: **POST**

Параметры строки запроса: НЕТ

В запросе должен присутствовать HTTP-заголовок ``Authorization`` с необходимыми данными для :doc:`авторизации <../Authorization>`.

В теле запроса должна содержаться структура :doc:`../proto/DocumentsMoveOperation`, сериализованная в протобуфер.

Метод перемещает заданный список документов в заданное подразделение организации.

Для использования этого метода текущий пользователь должен иметь доступ ко всем перемещаемым документам.

Возможные HTTP-коды возврата:

-  200 (OK) - операция успешно завершена;

-  400 (Bad Request) - данные в запросе имеют неверный формат или отсутствуют обязательные параметры;

-  401 (Unauthorized) - в запросе отсутствует HTTP-заголовок ``Authorization``, или в этом заголовке содержатся некорректные авторизационные данные;

-  403 (Forbidden) - доступ к ящику с предоставленным авторизационным токеном запрещен;

-  405 (Method not allowed) - используется неподходящий HTTP-метод;

-  500 (Internal server error) - при обработке запроса возникла непредвиденная ошибка.