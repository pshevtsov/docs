# Политика работы с версиями {{ CH }}

{{ CH }} использует политику частых релизов. В {{ mch-name }} для использования доступен ограниченный набор версий {{ CH }}, который постоянно актуализируется. При устаревании версии {{ CH }}, используемой в кластере {{ mch-name }}, версия этого кластера обновляется. 

Обновление до актуальных версий позволяет получать новую функциональность, патчи и исправления, направленные на улучшение безопасности, что повышает общую стабильность кластера.
Каждая версия {{ CH }}, которая поддерживается {{ mch-name }}, проходит всестороннее тестирование. 

После обновления до новой поддерживаемой версии {{ CH }} ваши данные останутся в целости и будут доступны.


## Политика поддержки версий {#versioning-policy}

{{ mch-name }} использует два типа версий {{ CH }}:
- **LTS** (версии с расширенным периодом поддержки, Long-Term Support). 

  Срок поддержки LTS-версий — один год, новые версии выпускаются каждые полгода.

  Поддерживаются две LTS-версии: текущая и предыдущая. 
  
  При релизе в {{ mch-name }} новой LTS-версии предыдущая LTS-версия становится неподдерживаемой. Пользователям, у которых развернуты кластеры на текущей LTS-версии, будут отправлены уведомления о том, что поддержка этой версии будет прекращена через полгода.

- **Промежуточные**.

  Поддерживаются три самых новых промежуточных версии {{ CH }}, не являющихся LTS-версиями. 

  При релизе в {{ mch-name }} новой промежуточной версии {{ CH }} самая старая из трех поддерживаемых промежуточных версий становится неподдерживаемой.

Вы можете вручную [изменить версию кластера](../operations/cluster-version-update.md) на одну из поддерживаемых версий.

{% note warning %}

* Создание новых хостов в кластерах на неподдерживаемой версии {{ CH }} становится невозможным.
* Кластеры на неподдерживаемой версии {{ CH }} будут автоматически обновлены в соответствии с [политикой обновления](#update-policy).

{% endnote %}


## Политика обновления {#update-policy}

{% list tabs %}

- LTS-версии

  Кластер {{ mch-name }} на неподдерживаемой версии {{ CH }} будет обновлен до следующей LTS-версии.
  
  ![image](../../_assets/mdb/mch-update-policy-lts.svg)
  
  {% note warning %}
  
  Уведомления о планируемом обновлении кластеров, использующих неподдерживаемую LTS-версию, будут отправлены пользователям за **два месяца**, за **один месяц** и за **одну неделю** до обновления.

  {% endnote %} 

- Промежуточные версии

  Кластер {{ mch-name }} на неподдерживаемой версии {{ CH }} будет обновлен либо до LTS-версии, если она доступна, либо до самой новой промежуточной версии.
  
  ![image](../../_assets/mdb/mch-update-policy.svg)
  
  {% note warning %}
     
  * Уведомления о планируемом обновлении кластеров, использующих неподдерживаемую промежуточную версию, будут отправлены пользователям за **одну неделю** до обновления.
  * В случае перехода на LTS-версию к кластеру будет применяться соответствующая политика обновлений.

  {% endnote %}

{% endlist %}