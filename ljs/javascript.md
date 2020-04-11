---


---

<h1 id="ljs">Ljs</h1>
<p>Это глобальный объект который регистрируется автоматически, некое хранилище для исполнителей и его плагинов.<br>
В нем уже присутствует обслуживание регистраторов самих исполнителей и их дополнений или плагинов.<br>
Данный объект не может быть объявлен дважды.<br>
<code>ljs</code>  объект состоит из трёх частей, все они являются расширением. Главный родительский класс - это набор методов для регистрации и управления самими исполнителями, следующий отвечает за вспомогательные методы <code>helpers</code>  и последний для регистрации разного рода расширений самого <code>ljs</code>.</p>
<h2 id="подробно-о-методах">Подробно о методах</h2>
<h3 id="exec">exec</h3>
<pre><code>/**
 * @param data [string|Array|Object]
 * @param params [any]
 * @param storage_data [object]
 * @returns {null}
 */
exec (data, params = null, storage_data = {})
</code></pre>
<p>Метод для вызова исполнителя.<br>
Параметр <code>data</code> может быть строкой для выполнения одного исполнителя или логической последовательности (<a href="/">см. Логическая последовательность строки исполнителя</a>). Так же это может быть массив с перечнем исполнителей или объект так-же с перечнем исполнителей и их параметрами, где ключ это имя исполнителя а содержимое это параметры передаваемые в него.<br>
В следующий параметр <code>params</code> мы передаём данные которые необходимо отправить в исполнитель (только если это строковая логическая последовательность).<br>
И последний <code>storage-data</code> - это хранилище данных исполнителя которое доступно внутри класса исполнителя по ссылке <code>this.storage</code>, эти данные доступны для всех указаных исполнителей в параметре <code>data</code>. Так-же в хранилище хранятся некоторые системные данные (<a href="/">см. Системные данные хранилища</a>)</p>
<h3 id="parse">parse</h3>
<pre><code>/**
 * @param str [string]
 * @param storage [object]
 * @returns {*}
 */
parse (str, storage = {})
</code></pre>
<p>Метод для парсинга любой строки со вставками исполнителей и заменяет их на результат выполнения самого исполнителя. Синтаксис для вхождения исполнителя <code>&gt;&gt;</code>. Предположим что у вас есть исполнитель который возвращает строку с именем пользователя и у вас есть строка с обычным текстом между которого необходимо вставить это имя. Для этого достаточно сделать следующее:</p>
<pre><code>ljs.parse(“Hello dear &gt;&gt;user::name, on you email &gt;&gt;user::email send a message with registration code");
</code></pre>
<p>Так же возможно передать параметры в исполнители, для этого необходимо передать параметры в круглых скобках разделяя параметры двойным пайпом, например:</p>
<pre><code>ljs.parse(“Hello dear &gt;&gt;users::find(state.user_id || name), you have a &gt;&gt;user::messages(new) new messages”);
</code></pre>
<h3 id="call">call</h3>
<pre><code>/**
 * @param command [string]
 * @param storage [object]
 * @returns {undefined|*}
 */
 call (command, storage = {})
</code></pre>
<p>Метод для единичного вызова исполнителя в виде строки как в методе <code>parse</code> только без символа вхождения, например:</p>
<pre><code>ljs.call(“users::find(state.user_id)”);
// или
ljs.call(“user::name”);
</code></pre>
<p>Этот метод используется только внутри метода <code>parse</code> и в дальнейшем о нем речи не пойдёт.</p>
<h3 id="toexec">toExec</h3>
<pre><code>/**
 * @param name [string]
 * @param closure [function]
 * @returns {this}
 */
 toExec (name, closure)
</code></pre>
<p>Метод для добавления простого исполнителя в виде функции. Например:</p>
<pre><code>ljs.toExec(“user_name”, (...params) =&gt; {
    return “Xsaven”;
});

ljs.exec(“user_name”);
</code></pre>
<h3 id="removeexec">removeExec</h3>
<pre><code>/**
 * @param name [string]
 * @returns {this}
 */
</code></pre>
<p>Удаляет простой исполнитель созданный методом <code>toExec</code>.</p>
<h3 id="regexec">regExec</h3>
<pre><code>/**
 * @param class [Executor]
 * @param name [string|null]
 * @returns {this}
 */
</code></pre>
<p>Метод для регистрации класса исполнителя, подробнее (<a href="/">см. Организация класса исполнителя</a>)</p>
<h4 id="системные-методы">Системные методы</h4>
<h3 id="local">_local()</h3>
<p>Метод который переключает режим локальной разработки на режим продакшена и обратно.</p>
<h3 id="disparch_event">_disparch_event</h3>
<pre><code>/**
 * @param name
 * @param detail
 * @returns {this}
 * @private
 */
_dispatch_event (name, detail = this)
</code></pre>
<p>Вызывает внутреннее событие, все события регестрируются на <code>document</code>.<br>
Встоеные события:<br>
<code>ljs:instance</code> - выполняется при создании экземпляра класса <code>ljs</code>.<br>
<code>ljs:load</code> - выполняется после того как модуль будет полностью загружен, как правило это событие используется для вливания пользовательских расширений.<br>
<code>ljs:global:*</code> - где <code>*</code> - это имя глобального модуля который только что зарегестрировался.<br>
<code>ljs:proto:*</code> - где <code>*</code> - это имя прототипа который только что был добавлен.<br>
<code>ljs:macro:*</code> - где <code>*</code> - это имя только что добавленного макроса.<br>
<code>ljs:alert_system</code> - выполняется каждый раз когда приходит системное сообщение отправленное через исполнителя <code>toast</code>.<br>
<code>ljs:nav:not_load</code> - выполняется каждый раз когда не вышло загрузить страницу (только при использовании плагина <code>nav</code>).<br>
<code>ljs:nav:send</code> - выполняется каждый раз перед запросом на получение новых данных страницы (только при использовании плагина <code>nav</code>).<br>
<code>ljs:nav:complete</code> - выполняется каждый раз после загрузки данных новой страницы (толко при использовании плагина <code>nav</code>).<br>
<code>ljs:nav:error</code> - выполняется каждый раз когда при загрузки данных страницы произошла ошибка (только при использовании плагина <code>nav</code>).<br>
А также присутствует ряд событий для состояний значений о них (<a href="/">см. Состояния</a>).<br>
Добавить собственный слушатель событий:</p>
<pre><code>document.addEventListener(“my_event_name”, ({details}) =&gt; {
    console.log(details); //{my_params: true}
});
// Or
$(document).on(“my_event_name”, ({details}) =&gt; {
    console.log(details); //{my_params: true}
});
// And call this event
ljs._dispatch_event(“my_event_name”, {my_params: true});
</code></pre>
<h3 id="log">_log</h3>
<pre><code>/**
 * @param data {any}
 * @param type {string}
 * @private
 */
</code></pre>
<p>Системный вывод в консоль, отличается от обычного тем что выводит данные только в том случае если разработка ведётся локально или вручную переключено состояние с продакшена на локаль методом <code>_locale</code>.<br>
Ряд подобных методов которые просто отличаются по типу:</p>
<h4 id="error">_error</h4>
<h4 id="info">_info</h4>
<h4 id="warn">_warn</h4>
<p>Все они используют внутри себя метод <code>_log</code>.</p>
<h3 id="detail">_detail</h3>
<p>Метод для вывода любой детальной информации в консоль, особенностью этого метода является то что он основан на методе <code>_log</code> но помимо всего этого чтобы он начал выводить данные надо не только переключится на локаль но и включить этот вывод методом <code>ljs.applyDetails()</code> и отключается точно так же, данные о включённом состоянии хранятся с помощью <code>LStorage</code> (<a href="/">см. Работа с локальным хранилищем</a>).</p>
<h3 id="query">_query</h3>
<pre><code>/**
 * @param name [string]
 */
</code></pre>
<p>Метод для получения гет параметров ссылки:</p>
<pre><code>// http://localhost?page=3
ljs._query(“page”); // 3
</code></pre>
<h3 id="dot">_dot</h3>
<pre><code>/**
 * @param object [object|array]
 */
</code></pre>
<p>Превращает многоуровневый в одноуровневый складывая все ключи в один разделяя их только точкой:</p>
<pre><code>let obj = {a: 1, b: {c: 2, d: 3}, e: 4};
let new_obj = ljs._dot(obj);
// {“a”: 1, “b.c”: 2, “b.d”: 3, “e”: 4}
</code></pre>
<h3 id="isprocess">isProcess</h3>
<pre><code>/**
  * @returns {boolean}
  */
</code></pre>
<p>Вернёт истину в любой момент когда будет выполнятся ajax запрос.</p>
<h3 id="extend">extend</h3>
<pre><code>/**
 * @param name
 * @param extendClass
 * @returns {LJS}
 */
</code></pre>
<p>Расширяет экземпляр новым обьектом инициализируя его сразу после объявления:</p>
<pre><code>ljs.extend(“date”, Date);
</code></pre>
<h1 id="executors">Executors</h1>
<p>Исполнители - это специальные классы, которые регистрируются внутри ljs и их возможно вызвать постой строкой <code>string</code> или обьектом, например <code>”info”.exec()</code>.<br>
Данный подход блестяще подходит для исполнения тех или иных команд которые получены были от сервера. Если грубо, это набор неких команд для реакции лендинга с помощью <code>JavaScript</code> полученных в ответ на <code>Ajax</code> запрос.</p>

