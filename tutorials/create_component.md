## Создание компонента

### Поиск документации

1. Найти нужный компонент на сайте производителя (в примере - конденсатор от _Samsung Electro-Mechanics_) и открыть документацию, т.е. _datasheet_ (в примере - иконка _Spec_)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_1.png)

2. Найти в документации размеры компонента и его характеристики, последние понадобятся при заполнении _Excel_-файла библиотеки

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_2.png)

### Создание условного графического обозначения (УГО)

1. Найти стандарт на УГО выбранного компонента (в примере - стандарт на конденсаторы ГОСТ 2.728-74)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_3.png)

2. Найти УГО для выбранного компонента (в примере - керамический неполярный конденсатор)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_4.png)

3. Здесь же ниже найти размеры УГО

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_5.png)

4. В _Altium Designer_ создать файл для УГО, пройдя по _File -> New -> Library -> Schematic Library_

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_6.png)

5. Нарисовать УГО компонента в соответствии со стандартом, принимая во внимание несколько важных советов:
    - Выводы рисуются с помощью _Pin_, обычно длиной 5 мм, цвет - черный
    - Настройки выводов открываются горячей клавишей _F11_ при их выборе
    - Выводы имеют параметры _Name_ и _Designator_ (обычно порядковые номера, начиная с 1), для пассивных компонентов их отображение должно быть скрыто
    - Корпус рисуется с помощью _Line_, цвет - синий
    - Шаг сетки можно задать в настройках (_Shematic - > Grids -> Metric Grid Presets_), а переключаться между вариантами - горячей клавишей _G_
    
![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_7.png)

6. Перейти в настройки всего компонента, щелкнув по свободной области и нажав _F11_. Заполнить поля _Design Item ID_, _Designator_, _Comment_ и _Description_:
    - _Design Item ID_ - заполняется в верхнем регистре и зависит от конкретного УГО (в примере - обозначение неполярного конденсатора, поэтому по законам логики поле заполняется как _CAPACITOR-NONPOLAR_)
    - _Designator_ - позиционное обозначение в соответствии со стандартом и обязательный знак вопроса, который при добавлении компонента на схему _Altium Designer_ почти автоматически заменит на порядковый номер (в примере - позиционное обозначение конденсатора по ГОСТ 2.710-81, т.е. _С?_)
    - _Comment_ - необходимая информация, отображаемая вместе с УГО компонента при добавлении на схему (в примере - номинальное значение емкости конденсатора, т.е. надпись "=Номинал", которая автоматически заменится на значение поля "Номинал" компонента в соответствии с _Excel_-файлом библиотеки)
    - _Description_ - дополнительная информация, описание компонента (в примере - краткое описание конденсатора, т.е. надпись "=Описание", которая автоматически заменится на значение поля "Описание" компонента в соответствии с _Excel_-файлом библиотеки)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_8.png)

7. Сохранить файл с УГО в папку _sch_ библиотеки, повторяя заполнение поля _Design Item ID_ в нижнем регистре и заменяя символы/знаки на нижнее подчеркивание (в примере - название файла в соответствии с _CAPACITOR-NONPOLAR_ записывается как _capacitor_nonpolar_)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_9.png)

### Создание посадочного места (т.е. _footprint_)

1. В _Altium Designer_ создать файл для посадочного места, пройдя по _File -> New -> Library -> PCB Library_. Затем открыть инструмент для создания посадочного места в соответствии со стандартами _IPC_, нажав _Tools -> IPC Compliant Footprint Wizard_

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_10.png)

2. Выбрать вариант корпуса для компонента (в примере - конденсатор с корпусом типа _CHIP_)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_11.png)

3. В полях выбора типа компонента _Package Type_ и расположения положительного вывода в случае полярных компонентов _Polarity Pin Location_ поставить нужный параметр. Остальные поля с размерами заполняются согласно документации (в примере - неполярный конденсатор, т.е. поля _Package Type_ и _Polarity Pin Location_ заполняются как _Chip Capacitor_ и _None_)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_12.png)

4. Далее нажимать _Next_, не меняя настроек, до появления следующего окна. Проверить толщину линии шелкографии в поле _Silkscreen Line Width_, значение должно составлять 0,2 мм

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_13.png)

5. Далее нажимать _Next_, не меняя настроек, до появления следующего окна. Проверить пункты:
    - _Add Courtyard Information_ (Зона запрещения) - толщина линии _Line Width_ 0,05 мм, расположение _Layer_ на слое _Mechanical Layer 15_
    - _Add Assembly Information_ (Контур корпуса) - толщина линии _Line Width_ 0,1 мм, расположение _Layer_ на слое _Mechanical Layer 11_
    - _Add Component Body Information_ (3D-модель) - расположение _Layer_ на слое _Mechanical Layer 13_

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_14.png)

6. Далее нажимать _Next_, не меняя настроек, до появления следующего окна. Выбрать пункт _Use suggested values_ для заполнения полей по умолчанию, затем отключить и исправить значение в поле _Name_ на наименование корпуса согласно документации, использовать верхний регистр (в примере - конденсатор с типоразмером корпуса 0402, т.е. поле _Name_ заполняется как "C0402", позиционное обозначение добавлено для исключения путаницы при создании иных компонентов с аналогичным типоразмером)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_15.png)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_16.png)

7. Далее нажимать _Next_, не меняя настроек, до появления следующего окна. Выбрать пункт _Current PcbLib File_, остальные пункты оставить без изменений. Пройти далее и завершить создание компонента

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_17.png)

8. Добавить слои _Mechanical 7_ и _Mechanical 9_ для отображения информации с полей _Comment_ и _Designator_ компонента. Для этого горячей клавишей _L_ открыть окно _View Configuration_, далее _Layers -> Mechanical Layers -> Add Mechanical Layer_, заполнить поля - название слоя _Layer Name_ и номер слоя _Layer Number_ (например, _Mechanical 9_ и _9_)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_18.png)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_19.png)

9. Внизу рабочего окна выбрать нужный слой и добавить с помощью _String_ надписи. На слой _Mechanical 7_ - _.Comment_, на слой  _Mechanical 9_ - _.Designator_ (точка обязательна). Открыть свойства надписей, выбрав их и нажав _F11_, проверить шрифт и высоту текста. Рекомендумые параметры: _GOST MT_, _Bold(B)_, высота текста 1,2 мм
    - ПРИМЕЧАНИЕ: Шрифт _GOST MT_ должен быть установлен в используемой операционной системе

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_20.png)

10. Сохранить файл с посадочным местом в папку _pcb_ библиотеки, повторяя заполнение поля _Name_ в нижнем регистре и заменяя символы/знаки на нижнее подчеркивание (в примере - название файла в соответствии с _C0402_ записывается как _c0402_)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/create_component/create_component_21.png)

11. Готово! Компонент создан

12. *Для полноценной работы необходимо внести компонент в _Excel_-файл библиотеки (см. руководство "Пополнение библиотеки с помощью _GitHub Desktop_")

_Warning!_ Заполнение многих полей, выбор названий файлов и другие действия во многом индивидуальны. В данном случае они обусловлены внутренними правилами организации библиотеки, логическими рассуждениями и накопленным опытом, а также действующими стандартами
