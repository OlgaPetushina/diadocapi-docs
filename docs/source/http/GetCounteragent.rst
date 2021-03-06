GetCounteragent
===============

На текущий момент доступно 2 версии данного метода:

-  :ref:`v2`

-  :ref:`v1`

.. _v2:

v2
--

Имя ресурса: **/V2/GetCounteragent**

HTTP метод: **GET**

Параметры строки запроса:

-  *myOrgId*: идентификатор организации, для которой осуществляется поиск контрагента;

-  *counteragentOrgId*: идентификатор организации-контрагента.

В запросе должен присутствовать HTTP-заголовок ``Authorization`` с необходимыми данными для :doc:`авторизации <../Authorization>`. Пользователь имеет право производить манипуляции со списком контрагентов организации myOrgId или запрашивать его, если у него есть доступ хотя бы в один из ящиков этой организации.

В теле ответа содержится информация о контрагенте с идентификатором *counteragentOrgId* для организации *myOrgId*.

Эта информация выдается в виде сериализованной структуры данных :doc:`../proto/Counteragent`, где вложенная структура :doc:`Departments <../proto/Department>` содержит только видимые подразделения, а также их родительские подразделения.

Возможные HTTP-коды возврата:

-  200 (OK) - операция успешно завершена;

-  400 (Bad Request) - данные в запросе имеют неверный формат или отсутствуют обязательные параметры;

-  401 (Unauthorized) - в запросе отсутствует HTTP-заголовок ``Authorization``, или в этом заголовке содержатся некорректные авторизационные данные;

-  403 (Forbidden) - доступ к списку контрагентов организации myOrgId с предоставленным авторизационным токеном запрещен;

-  404 (Not Found) - между организациями myOrgId и counteragentOrgId партнерские отношения никогда не устанавливались;

-  405 (Method not allowed) - используется неподходящий HTTP-метод;

-  500 (Internal server error) - при обработке запроса возникла непредвиденная ошибка.

.. _v1:

v1
--

Имя ресурса: **/GetCounteragent**

HTTP метод: **GET**

Параметры строки запроса:

-  *myOrgId*: идентификатор организации, для которой осуществляется поиск контрагента;

-  *counteragentOrgId*: идентификатор организации-контрагента.

В запросе должен присутствовать HTTP-заголовок ``Authorization`` с необходимыми данными для :doc:`авторизации <../Authorization>`. Пользователь имеет право производить манипуляции со списком контрагентов организации myOrgId или запрашивать его, если у него есть доступ хотя бы в один из ящиков этой организации.

В теле ответа содержится информация о контрагенте с идентификатором counteragentOrgId для организации myOrgId. Эта информация выдается в виде сериализованной структуры данных :doc:`../proto/Counteragent`.

Возможные HTTP-коды возврата:

-  200 (OK) - операция успешно завершена;

-  400 (Bad Request) - данные в запросе имеют неверный формат или отсутствуют обязательные параметры;

-  401 (Unauthorized) - в запросе отсутствует HTTP-заголовок ``Authorization``, или в этом заголовке содержатся некорректные авторизационные данные;

-  403 (Forbidden) - доступ к списку контрагентов организации myOrgId с предоставленным авторизационным токеном запрещен;

-  404 (Not Found) - между организациями myOrgId и counteragentOrgId партнерские отношения никогда не устанавливались;

-  405 (Method not allowed) - используется неподходящий HTTP-метод;

-  500 (Internal server error) - при обработке запроса возникла непредвиденная ошибка.