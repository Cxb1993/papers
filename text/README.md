LaTeX-шаблон для русской кандидатской диссертации и её автореферата.

## Особенности
* Кодировка: UTF-8
* Стандарт: ГОСТ Р 7.0.11-2011
* Поддерживаемые движки: LaTeX, XeTeX

## Структура
* **Dissertation:** Структурированная система файлов с шаблоном диссертации
* **Synopsis**: Структурированная система файлов с шаблоном автореферата
* **Presentation:** Шаблон презентации
* **Documents:** Полезные документы (ГОСТ-ы и постановления)
* **PSCyr:** Пакет PSCyr + инструкции по установке
* **BibTeX-Styles:** Подборка русских стилевых пакетов BibTeX под UTF-8
* **Links.md:** Полезные ссылки

## Шрифты

### LaTeX + PSCyr
PSCyr — это пакет красивых русских шрифтов для LaTeX. К сожалению, его нужно устанавливать отдельно. Если он у вас не установлен, то ничего страшного — шаблон заработает и без него. Ну лучше бы его всё-таки поставить. Инструкции по установке PSCyr для различных конфигураций приведены [тут](PSCyr/README.md). Если вы не нашли подходящую вам инструкцию, но смогли выполнить установку самостоятельно, то большая просьба [поделиться](https://github.com/AndreyAkinshin/Russian-Phd-LaTeX-Dissertation-Template/pulls) вашими наработками.

### Linux + XeTeX
Для нормальной работы в системе должны быть установлены нужные шрифты. Например, для Ubuntu это можно сделать так:

```
$ sudo apt-get install msttcorefonts
$ sudo fc-cache -fv
```

Сборку можно производить следующими командами:

* диссертация: `latexmk -pdf -pdflatex="xelatex %O %S" dissertation`
* автореферат: `latexmk -pdf -pdflatex="xelatex %O %S" synopsis`

## Библиография
* Данный шаблон использует BibTeX для создания библиографии. Это рекомендуемый способ, но никто не мешает вам написать библиографию руками, если вы хотите.
* Отечественный ГОСТ очень суров, в настоящее время ещё не создали такой BibTeX-стиль, который бы ему полностью соответствовал. В данном шаблоне используется стиль *utf8gost71u.bst*, он более или менее вменяемый и достаточно близок к стандарту. Впрочем, при написании диссертации редко кто требует точного соответствия ГОСТ-у, лишь всё было оформлено красиво и однообразно. Если utf8gost71u.bst вас не устраивает, то вы можете выбрать любой другой стиль (из папки [BibTeX-Styles](BibTeX-Styles) или найденный в интернете). В файле biblio.bib аккуратно приведена вся библиография из ГОСТ Р 7.0.11-2011 и примеры всех типов документов на английском, так что вы можете попробовать все интересующие вас стили и увидеть, как каждый из них форматирует библиографию. 
* В стилевых файлов русских ГОСТ-ов многие типы документов (например, *PHDTHESIS* или *TECHREPORT*) сделаны очень плохо. В большинстве случаев лучше их вполне можно заменить на *ARTICLE* или *BOOK*.
* Лучше всего всегда обрамлять значение BibTeX-атрибутов в фигурные скобки или кавычки (т.е. вместо *month = jul* писать *month = {jul}*).
* Также лучше всегда указывать язык BibTeX-записи (например, *language = {russian}* или *language = {english}*).

## Пакеты и версии LaTeX
* Шаблон по умолчанию включает ряд распространённых пакетов, чтобы вы могли сразу ими пользоваться. Однако, на вашей машине какие-то пакеты могут быть не установлены. Если вам они не нужны, то вы можете их просто удалить (команда *\usepackage{<имя пакета>}*).
* Лучше всего использовать актуальные и полные версии LaTeX-дистрибутивов, это поможет избежать многих проблем. Например, [MikTeX](http://miktex.org/download) 2.9.4503+ для Windows.

## Благодарности
* Большое спасибо Юлии Мартыновой за [оригинальный вариант шаблона](http://alessia-lano.livejournal.com/4267.html).
* Большое спасибо [dustalov](https://github.com/dustalov), [Lenchik](https://github.com/Lenchik), [tonkonogov](https://github.com/tonkonogov) за значительный вклад и обсуждения.
* Спасибо [storkvist](https://github.com/storkvist), [kshmirko](https://github.com/kshmirko), [ZoomRmc](https://github.com/ZoomRmc), [tonytonov](https://github.com/tonytonov), [Thibak](https://github.com/Thibak), [eximius8](https://github.com/eximius8), [Nizky](https://github.com/Nizky) за полезные правки и замечания.