###Получение дополнительных TV-параметров для документа

*Замечание: Этот метод не работает при вызове из подключенного файла (include, include_once, require, require_once).*

*Замечание: рекомендуется всегда указывать номер документа, так как при его опускании метод работает с ошибками.*

array getTemplateVars(array $idnames[, string $fields[, int $docid[, int $published[, string $sort[, string $dir]]]]]);

**$idnames** - массив TV-параметров
Массив названий
Массив идентификаторов

**$fields** - список параметров, которые нужно возвращаться для дополнительных TV- параметров.
Список параметров через запятую
* - возвращаться все параметры
По умолчанию: *

**$docid** - документ, для которого нужно получить TV-параметр
Идентификатор документа
По умолчанию: текущий документ

**$published** - опубликованы ли документы
0 - документы не опубликованы
1 - документы опубликованы
По умолчанию: 1

**$sort** - поле по которому сортируются TV-параметры
По умолчанию: rank

**$dir** - правило сортировки TV-параметров
ASC - в порядке возрастания
DESC - в порядке убывания
по умолчанию: ASC

***

####Формат данных результата:

	Array ( [0] => Array ( 
				[id] => 4 
				[type] => text 
				[name] => МойПараметр 
				[caption] => Заголовок 
				[description] => Описание 
				[editor_type] => 0 
				[category] => 0 
				[locked] => 0 
				[elements] => Текст 
				[rank] => 0 
				[display] =>  
				[display_params] =>  
				[default_text] =>  
				[value] => Это наша текущая страница 
				) 
			... 
			)

####Пример

	$txt = $modx->getTemplateVars(array('МойПараметр','ЕщеПараметр'), '*', 11);
	//вернет информацию по дополнительным параметрам МойПараметр и ЕщеПараметр для текущего документа.