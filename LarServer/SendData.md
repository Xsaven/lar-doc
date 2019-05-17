# Отправка данных

Вместе с сервером поставляются функции помошники для отправки данных в браузер клиенту, это: `send_data` , `inDisplay` , `inAllDisplay`.

## send_data
Первая функция, основная, именно она реализует все отправки данных через `Process` `->` `TCP` `->` `WebSocet Server` `->` `Browser`.

```php
/**
 * @param $data  
 * @param array $conditions  
 * @param array $queue  
 * @return bool  
 * @throws Exception  
 */
 function send_data($data, $conditions = [], $queue = [])
```
## inDisplay
У этой функции очень интерестные возможности.
1. Она отправляет данные только в ту вкладку браузера, которая на данный момент активна пользователем процесса.
2. Если запрос на отправку данных через эту функцию пошол непосредственно с загружаемого процесса пользователя, то все данные, отправяются в задачи пользователя, затем, после соединения владельца этого процесса, ему в браузер отправляются все теже данные только со списка задач (выполняются одноразово, как и запрос). Ну а если отправить с контроллера который обрабатывается аякс запросом проще простого.
```php
/**  
 * @param $data  
 * @param array $conditions  
 * @return bool  
 * @throws Exception  
 */
 function inDisplay($data, $conditions = [])
```
## inAllDisplay
Эта функция делает все тоже-самое что и `inDisplay` только во все открыты вкладки браузера владельца сессии.
```php
/**  
 * @param $data  
 * @param array $conditions  
 * @return bool  
 * @throws Exception  
 */
 function inAllDisplay($data, $conditions = [])
```

## $conditions

#### CONN_ID = TRUE|FALSE|INT|ARRAY;
Указать идентификатор соединения  
```  
true - Отправлять пакеты только в текущее соеденение пользователя. 
false - Отправить пакеты во все соединения пользователя.  
int - Отправить пакеты в указанный идентификатор соеденения. (only dev)  
array - Отправить пакеты в указанные идентификаторы соеденения. (only dev)  
```

#### PERSON_ID = STRING
  
Указать адрес получателя  
```php  
use Lar\LServe\Passport;

Passport::getMyId(); // Возвращает уникальный идентификатор пользователя  
```  
Если отсуцтвует идентификатор персоны, отправляет всем соединениям.

#### GUARDED = TRUE|FALSE  
Отправить данные соединениям которые прошли верификацию Гвардом в системме (Для того что-бы верификация прошла, в модели `guard'а` необходимо прописать публичное свойство: 
```php
public $ids = ["id", "email"];  
```  
А затем классу `\\App\\Providers\\AppServiceProvider` в методе `boot` дописать следующую настройку:
```php
use Lar\LServe\Passport;

Passport::addGuardIdentification(); // Добавит стандартного guard'a "web"
Passport::addGuardIdentification("custome_guard"); // Также можно свего guard'a зарегестрировать.
```
**Описание возможных параметров:**
```
true - Пользователи которые прошли верификацию guard  
false - Пользователи которые не прошли верификацию guard  
```  
> При отсуцтвии опции проверка совершатся не будет  

#### GUARD = STRING  
Параметр указывает на то что надо отправить данные тем пользователям(лю) кторые прошли верификацию указанным `guard`
```php
["GUARD" => "web"]
```

#### WEB_* = MIX
Данный параметр позволяет отправить данные непосредственно пользователю `guard'a`. 

`*` - Это любое имя поля модели

> Если это кастомный `guard` то начинатся будут его параметры точно так же как и его имя только Upper Case, по анологии с `web` `guard`

```php
class User extends Model {
	public $ids = ["id", "email"];
}
...
inAllDisplay(["ljs._info" => "Hello"], ["WEB_ID" => 1]);
// OR
inAllDisplay(["ljs._info" => "Hello"], ["WEB_EMAIL" => "root@gmail.com"]);
// OR
inAllDisplay(["ljs._info" => "Hello"], ["WEB_ID" => 1, "WEB_EMAIL" => "root@gmail.com"]);
```
