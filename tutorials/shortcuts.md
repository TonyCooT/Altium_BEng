## Список горячих клавиш в _Altium Designer_

Горячие клавиши или сочетания клавиш могут быть полезны для ускорения выполнения многих действий в программе

Просмотр и редактирование сочетаний клавиш одинаковы для файлов _SchDoc_ и _PcbDoc_:
  - Прописать в поисковом поле в верхнем правом углу окна программы _"Customize"_ и выбрать в списке _Toolbars > Customize_
  - В открывшемся окне выбрать вкладку _Commands_ и установить в списке _Categories_ параметр _[All]_. Справа от окна появится таблица с колонками:
    - название действия _Caption_
    - основное сочетание клавиш _Shortcut_ 
    - альтернативное сочетание клавиш _Alternative_
  - Выбрать нужное действие и нажать _Edit_
  - В окне _Edit Command_ установить нужное сочетание клавиш, изменив значение поля _Primary_
  
Ниже приведены некоторые полезные сочетания клавиш, установленные по умолчанию
 
![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/shortcuts/shortcuts_1.png)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/shortcuts/shortcuts_2.png)

![](https://github.com/TonyCooT/Altium_BEng/blob/master/images/shortcuts/shortcuts_3.png)
 
### Общие

| Сочетание клавиш | Действие |
| :---:            | ---      |
| _TAB_                                                                | при перемещении объекта открыть окно его параметров                                                                                         |
| _X_                                                                  | при перемещении объекта зеркально отразить его по оси _X_                                                                                   | 
| _Y_                                                                  | при перемещении объекта зеркально отразить его по оси _Y_                                                                                   |
| _SHIFT_ + _CTRL_ + _T_                                               | выровнять выбранные объекты по верхнему краю                                                                                                |
| _SHIFT_ + _CTRL_ + _B_                                               | выровнять выбранные объекты по нижнему краю                                                                                                 | 
| _SHIFT_ + _CTRL_ + _L_                                               | выровнять выбранные объекты по левому краю                                                                                                  | 
| _SHIFT_ + _CTRL_ + _R_                                               | выровнять выбранные объекты по правому краю                                                                                                 | 
| _SHIFT_ + _CTRL_ + _H_                                               | равномерно распределить выбранные объекты по горизонтали                                                                                    | 
| _SHIFT_ + _CTRL_ + _V_                                               | равномерно распределить выбранные объекты по вертикали                                                                                      |
| _SHIFT_ + _F_                                                        | при последующем нажатии на объект открыть инструмент поиска _Find Similar Objects_                                                          | 
| _SHIFT_ + _C_                                                        | очистить текущий фильтр выделения объектов                                                                                                  |
| _CTRL_ + _Mouse-wheel Up_ / _Page Up_ / _Middle-click_ + _Mouse_     | приблизить                                                                                                                                  |
| _CTRL_ + _Mouse-wheel Down_ / _Page Down_ / _Middle-click_ + _Mouse_ | отдалить                                                                                                                                    |
| _ALT_ + _F5_                                                         | переключить оконный/полноэкранный режим                                                                                                     | 
| _CTRL_ + _HOME_                                                      | перейти к началу координат (по умолчанию, в левом нижнем углу)                                                                              | 
| _CTRL_ + _A_                                                         | выбрать все                                                                                                                                 |
| _CTRL_ + _Y_                                                         | вернуть изменение                                                                                                                           |
| _CTRL_ + _Z_                                                         | отменить изменение                                                                                                                          | 
| _A_                                                                  | открыть меню с функциями выравнивания _Align_                                                                                               |

### _Schematic Editor_

| Сочетание клавиш | Действие |
| :---:            | ---      |
| _G_                                                                  | переключить шаг сетки                                                                                                                       |
| _SPACEBAR_                                                           | при перемещении объекта повернуть его на 90°                                                                                                |
| _BACKSPACE_                                                          | удалить последний участок при прокладывании проводника и др.                                                                                |

### _PCB Editor_

| Сочетание клавиш | Действие |
| :---:            | ---      |
| _L_                                                                  | при перемещении объекта перенести его на противоположную сторону                                                                            |
| _N_                                                                  | при перемещении объекта скрыть отображение направления цепей                                                                                |
| _SPACEBAR #1_                                                        | при перемещении объекта повернуть его на _N°_ (шаг задается в настройках _PCB Editor -> General_)                                           |
| _Q_                                                                  | переключить единицы измерения _metric_ (метрическая)/_imperial_ (английская)                                                                |
| _G_                                                                  | открыть меню выбора сетки                                                                                                                   |
| _CTRL_ + _G_                                                         | открыть настройки текущей сетки                                                                                                             |
| _SHIFT_ + _R_                                                        | переключить режим трассировки (игнорирование/огибание/"расталкивание" препятствий)                                                          |
| _SPACEBAR #2_                                                        | при трассировке переключить направление угла                                                                                                |
| _SHIFT_ + _SPACEBAR_                                                 | при трассировке переключить стиль угла (если не включено ограничение в настройках _PCB Editor -> Interactive Routing -> Restrict To 90/45_) |
| _BACKSPACE_                                                          | удалить последний участок при трассировке                                                                                                   |
| _CTRL_ + _Left-click #1_                                             | автоматически завершить трассировку проводника до конечной цели                                                                             |
| _ESC_                                                                | прервать трассировку                                                                                                                        |
| _CTRL_ + _Left-click #2_                                             | при нажатии на один элемент подсветить все остальные элементы этой цепи                                                                     |
| _CTRL_ + _M_                                                         | измерить расстояние                                                                                                                         | 
| _SHIFT_ + _S_                                                        | включить/выключить выделение выбранного слоя                                                                                                | 
| _L_                                                                  | открыть настройки слоев печатной платы _View Configuration_                                                                                 |

### _3D_ визуализация

| Сочетание клавиш | Действие |
| :---:            | ---      |
| _2_                                                                  | переключить вид в _2D_                                                                                                                      |
| _3_                                                                  | переключить вид в _3D_                                                                                                                      |
| _9_                                                                  | повернуть _3D_ вид в вертикальное положение                                                                                                 |
| _0_                                                                  | повернуть _3D_ вид в горизонтальное положение                                                                                               |
| _CTRL_ + _F_                                                         | повернуть _3D_ вид на 180°                                                                                                                  |
| _SHIFT_                                                              | включить сферу поворота для _3D_ вида                                                                                                       |
| _CTRL_ + _C_                                                         | создать из текущего _3D_ вида картинку формата _.bmp_ (можно вывести в любой удобный редактор сочетанием клавиш _CTRL_ + _V_)               |
                                                                                                                      