## Создание компонента

### Поиск документации

1. Найти нужный компонент на сайте производителя (в примере - конденсатор от _Samsung Electro-Mechanics_) и открыть документацию (т.е. _datasheet_). В данном случае это иконка _Spec_

![create_component_1](images/create_component/create_component_1.png)

2. Найти в документации размеры компонента и его характеристики, последние понадобятся для заполнения _Excel_-таблицы библиотеки

![create_component_2](images/create_component/create_component_2.png)

### Создание условного графического обозначения (УГО)

1. Найти стандарт на УГО выбранного компонента (на конденсаторы - ГОСТ 2.728-74)

![create_component_3](images/create_component/create_component_3.png)

2. Выбрать УГО для своего компонента (для выбранного керамического неполярного конденсатора - обычное, первое)

![create_component_4](images/create_component/create_component_4.png)

3. Здесь же ниже найти размеры для выбранного УГО

![create_component_5](images/create_component/create_component_5.png)

4. В _Altium_ создать файл для схемы, пройдя по _File -> New -> Library -> Schematic Library_

![create_component_6](images/create_component/create_component_6.png)

5. Нарисовать УГО компонента в соответствии с ГОСТ, при этом:
    1. Настройки выводов открываются горячей клавишей _F11_ при их выборе
    2. Выводы рисуются с помощью _Pin_ длиной 5 мм
    3. Выводы имеют _Name_ и _Designator_, начиная с 1 (убедиться в этом и не забыть погасить их отображение в настройках, т.к. для пассивных компонентов это излишне)
    4. Корпус рисуется с помощью _Line_
    5. Шаг сетки можно задать в настройках (_Shematic - > Grids -> Metric Grid Presets_), а переключать - горячей клавишей _G_
    
![create_component_7](images/create_component/create_component_7.png)

6. Перейти в настройки всего компонента, щелкнув по любой части схемы вне его и нажав _F11_. Заполнить поля _Design Item ID_, _Designator_, _Comment_ и _Description_ следующим образом
    1. _Design Item ID_ - начинается с позиционного обозначения (для конденсатора - С), затем дефис и надпись, какая именно - вопрос открыт. Лучше всего примерно в таком виде - _C-50.0V_, где _50.0V_ - это номинальное напряжение данного конденсатора
    2. _Designator_ - позиционное обозначение конденсатора со знаком вопроса, который на схеме _Altium_ почти автоматически сам изменит на цифру
    3. _Comment_ - в данном случае мы вписываем сюда "=Номинал", при использовании компонента надпись автоматически заменится на значение его поля "Номинал" из _Excel_-файла библиотеки
    4. _Description_ - вписываем сюда "=Описание", при использовании компонента надпись автоматически заменится на значение его поля "Описание" из _Excel_-файла библиотеки

![create_component_8](images/create_component/create_component_8.png)

7. Сохраняем файл со схемой в папку _sch_ библиотеки, называя его по аналогии с _Design Item ID_, прописывая вместо позиционного обозначения полное название. Например, _C-50.0V_ преобразуется в _capacitor_50.0v_

![create_component_9](images/create_component/create_component_9.png)

### Создание посадочного места (т.е. _footprint_)

1. В _Altium_ создать файл для посадочного места, пройдя по _File -> New -> Library -> PCB Library_. Затем открыть инструмент для создания посадочного места в соответствии со стандартами _IPC_, нажав _Tools -> IPC Compliant Footprint Wizard_

![create_component_10](images/create_component/create_component_10.png)

2. Выбрать вариант корпуса своего компонента (в данном случае - _CHIP_)

![create_component_11](images/create_component/create_component_11.png)

3. В поле _Package Type_ выбрать нужный компонент. В поле _Polarity Pin Location_ данному неполярному конденсатору соответствует пункт _None_. Остальные поля с размерами заполняются согласно документации

![create_component_12](images/create_component/create_component_12.png)

4. Далее нажимать _Next_, не меняя настроек, до появления следующего окна. Проверить толщину линии шелкографии в поле _Silkscreen Line Width_, значение должно быть 0,2 мм

![create_component_13](images/create_component/create_component_13.png)

5. Далее нажимать _Next_, не меняя настроек, до появления следующего окна. Проверить пункты
    1. _Add Courtyard Information_ (Зона запрещения) - толщина линии _Line Width_ 0,05 мм, расположение _Layer_ на слое _Mechanical Layer 15_
    2. _Add Assembly Information_ (Контур корпуса) - толщина линии _Line Width_ 0,1 мм, расположение _Layer_ на слое _Mechanical Layer 11_
    3. _Add Component Body Information_ (3D-модель) - расположение _Layer_ на слое _Mechanical Layer 13_

![create_component_14](images/create_component/create_component_14.png)

6. Далее нажимать _Next_, не меняя настроек, до появления следующего окна. Выбрать пункт _Use suggested values_ для заполнения полей по умолчанию, затем отключить и исправить значение в поле _Name_ на позиционное обозначение и тип корпуса (однако и тут вопрос остается открытым). В данном случае - _C0402_

![create_component_15](images/create_component/create_component_15.png)

![create_component_16](images/create_component/create_component_16.png)

7. Далее нажимать _Next_, не меняя настроек, до появления следующего окна. Выбрать пункт _Current PcbLib File_, остальные оставить без изменений. Пройти далее и завершить создание компонента

![create_component_17](images/create_component/create_component_17.png)

8. Добавить слои _Mechanical 7_ и _Mechanical 9_ для отображения полей _Comment_ и _Designator_ компонента, соответственно. Для этого горячей клавишей _L_ открыть окно _View Configuration_, далее _Layers -> Mechanical Layers -> Add Mechanical Layer_. Заполнить поля слоя - название _Layer Name_ и номер _Layer Number_ (например, _Mechanical 9_ и _9_)

![create_component_18](images/create_component/create_component_18.png)

![create_component_19](images/create_component/create_component_19.png)

9. Внизу рабочего окна выбрать нужный слой и добавить с помощью _String_ надписи. На слой _Mechanical 7_ - _.Comment_, на слой  _Mechanical 9_ - _.Designator_ (точка обязательна). Открыть свойства надписей, выбрав их и нажав _F11_, проверить шрифт и высоту текста. Должно быть _GOST MT_, _Bold(B)_, высота текста 1,2 мм

![create_component_20](images/create_component/create_component_20.png)

10. Сохранить файл с посадочным местом в папку _pcb_ библиотеки, называя его по аналогии с _Name_ посадочного места. Например, _C0402_ -> _с0402_

![create_component_22](images/create_component/create_component_22.png)

11. Готово! Компонент создан
