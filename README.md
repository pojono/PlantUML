# PlantUML

В этом репозитории собраны примеры диграмм, созданных с помощью утилиты PlantUML по [модели C4](https://c4model.com/).

Модель С4 была создана, чтобы помочь командам разработчиков визуализировать архитектуру ПО. Это алгоритм создания карты Вашего кода, с различными уровнями детализации, точно так же, Google Maps хранит спутниковые снимки, снятые с разной точностью.

Существует 3 основных типа диаграмм, (4-ый использовать не рекомуендуется) от общего к частному:
1. Context
2. Container
3. Component
4. Class

Чтобы отказаться от рисования схем в графических редакторах и описывать архитектуру в виде кода, можно воспользоваться утилитой [PlantUML](https://plantuml.com/ru/) и расширением [C4-PlantUML](https://github.com/RicardoNiepel/C4-PlantUML). 

## Начало работы

Создайте файл `.puml` и напишите в начале файла `@startuml` и `@enduml` в конце. Вся диаграмма будет находиться между этими двумя командами. 

Добавьте импорт, например: `!includeurl https://raw.githubusercontent.com/RicardoNiepel/C4-PlantUML/master/C4_Container.puml`. Подробнее об импортах - далее.

Теперь создадим саму диаграмму. Вы можете использовать такие элементы, как `Person`,  `System`, `Container`, `Rel` и многие другие (полный список - ниже). Приведём пример:

```csharp
@startuml C4_Elements
!includeurl https://raw.githubusercontent.com/RicardoNiepel/C4-PlantUML/master/C4_Container.puml

Person(personAlias, "Label", "Optional Description")
Container(containerAlias, "Label", "Technology", "Optional Description")
System(systemAlias, "Label", "Optional Description")

Rel(personAlias, containerAlias, "Label", "Optional Technology")
@enduml
```
И Вы получите следующий результат:

![C4_Elements](http://www.plantuml.com/plantuml/png/xLXhKziu5FtkNw663oqpOGcq1PODcUPX2hCXOV8Ojaix6H4hYQUEv96KGdQx_tqbsH5EX5Phf_2fOWQCTU-vvrx9HuyFZ4FA5_F8UmsQ92AKYOSTP_EyLm6QX1W1l-rV-Pt1wBmhVZMxxMuFx9ohvWcaFbz68Pxcn1pupOjEWjY__DC71uUUnxw6E8OKpe4mWek83z03hqVX5CyHvc0iVY6QDRkdCBu90pu3XvLAvlqSFbmXnk0KzSE_43XuNybwKJJc44yZ1FxsW6XzWOe8NyRed62UU1og7ZQ30RaNoO49Z1Zo_id2r2abzoc4AYlOEL9DlP5Gvjji00bcSgfMxyW21v0kQxKLlmqM5iuL8y86ZtUggRSDGWD4RU_bY28GG3P3WQJv6hJXaYnulY6EY63Shd_g3WUZUd_K_zqVD2yoAT_1yTSfbSccF7pVRxIQ6OiPnC4z3Jb7672wGEO4aTbru1o1KfFCmp7eGyp0LR_a9NC5J0YHVweJ8kUF37D6KL2xWHIBUfvMzsL73JGfWXm5mfo286JZ1MCXmMM04GeOu0JS8V0DHc4WhRnN20UFAUfyLxaEkjUZLlUc8_nYvKiu9u9nACTOm6xQj_tpmQXt-V5Y028quTA5XjCPptY8mZUIMH6Yl1zlwhXyWqOY0yZA08qYU8UYtSo7K3exIz-MmDeCX0oaVcv0-I1dvDF0u3Rf_MAF83BheGZAbDaiZ7CcAbn7Aqu7vHNeuHezNTApKcaNh8op7TeFd4hokYovmd0qdk6judt6-_jL9hxZqmsXhDscy5-g-xA_jhzVMgk1u3QXP5uMPYGprYbjiwiCIdjxjTAk4qCdPeAPDXfrhMuDySc_IHsKjqdGx9CCgtjxag4RokJfCDBWQ-WT9Bx0EqAB55DaxSOgMjIdQwfZ52okm7H3RblaJUAj8iMLmcfKkBLzQUtOv1xRYLf2Eo5CXkuqDietB5A-uRMHu73xujcGOnj5EtqdWCbjcAjixI9baqkqaLvx-yBPiT64subQGbiW70pRkShNAr8-kRanS-pzWFhPmOLuMIjepyEDOP9qP_AuWmONA8fHxWEOSDRge639RggrOEzs5WO1mbzQUwfZpMVey1a-uTDp-FIUy6axVDgfZpekZacCJa4Ti53j41cPy7j8nSEISJJ_HPXSqt0EwHAW2Cc37pi5WvbX248CcCII7lr571FA1MB6wHgHM0I0EDZqPUdUEbg2CS5OFA40S0Au8ymbvWW7mXOkWX3XiSZ3_uReyeu4oxBSwC-06l5m32CL5nEyz_WcLeJA0fA5GK9Cp0drJ2RhmGFq3KKabfa8I2ZAKlJmVktt-jtEgF5nTNAldBmxF6xeVl-FWT_hrDiZm_3eHFvem_wd_i2_olGV71oTD5eca67ugsfvxmeinsFv-H1Sgvc7TttIDUyhbAdJeB5n8jseY7bohXo_RHoTMq_ow46Gmp0QlI1dFGfEyYTr-MCbdqp_b-2iPvQLwjlcyNcpugxp2t8sPxkxpjlVeznS3Yv6RV-ZtsbvCwaRJAVeHMYAS93S7NZVpy1Q4_yFX17uxdslRioCMce1abcgJ7HsDjjLoRDE6vMeISDKHTT1jQ4DL3k9X5HQvgNBQ-2dGfzN3nNX7BSXIORhDnKECFaG83QcJwD-nf_noi8IOPFlo7_WEJWRocEGDv2B9k0Cf-FrrQZco88f1vEy2LQKk1d1u5kqycxosrRU6QxujQ6ccFFs4DmcVlPBlk9xm2R170fgb87xaCz23FZBxGh7EhXb7pZOsEKLsUJz9fp6aO0KXBKHfEDPo0KPLbuv21OALpubjwNxB4aLC0uda-ARnQPOzEgN7R-NsRszUtlIQht_GRitNSSNMQHrEkwzHVxb-UVoB9oC2gUuUfoVPn7NMc3gfpvrcmALzruTPEThLiJoy305lJ2X3V4to1MNVJEX_CglNNEAlyx29llpc63vd9LzxUGM_CowySQzSA1T44SB1k9YouGcQrac-gQionWPPTz6lA-kknqXYndnFddVQ9nNVf1uw-os4--TYceMnTOvM1NxM9odMYVFfjW_5LjO6UEWhT8fy5owdi8_jwxhF0nTDtYyiAxRoScM7ZYJIL9Fc9NQwl0X7hen3uaSxvQ42jL_ucBySPNIWsouglqhYSXq-Hz0wQ4hcKt_DxhNGz4wOOE52V58Ho1yG3XOpAD_0G00 "C4_Elements")

В дополнение к этому Вы можете описать границы системы или компонента. Взгляните на следующий пример:

```csharp
@startuml Basic Sample
!includeurl https://raw.githubusercontent.com/RicardoNiepel/C4-PlantUML/master/C4_Container.puml

Person(admin, "Administrator")
System_Boundary(c1, "Sample System") {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Compare Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![Basic Sample](http://www.plantuml.com/plantuml/png/JOzFJy904CNl_HHhlPG4ss0yUG8QemSX3Irw94CxoYRxPpCx6qACtzr14Enbqdc_z-RjD38G9slK7ABkLGis6CnkjEjD6Z2HKJlc41-hYc1VVchUfMsAIBrtZ8xBtjjgfNkWmIyr1ZHL_N3N672yNhnM5Y8ZoMfJ2m_Q8PL1hcLPWnIzAs2mserLFZjE7Pc0FUMZh3s8qMxcFha1w53q4u5EvTH9oqVgArFoNPABFMut48AGxxXLin2C56FjNIwh-dQiPcrJBfywiH2g-tAY5c_rh-Pj05brUysCf5XRD18PfSdtkKl19r7mCoPYjaBpzuRhzNKKfyoNhcjQeOxGHRt6F2D7-SNZ-21l_rkcw8PapGy0)

Более сложные примеры собраны в этом репозитории в соответствующих папках.

## Основные элементы и связи между ними

### System Context & System Landscape diagrams

Import: `!includeurl https://raw.githubusercontent.com/RicardoNiepel/C4-PlantUML/master/C4_Context.puml`

Поддерживаемые элементы:

    Person
    Person_Ext
    System
    System_Ext 
    SystemDb
    SystemDb_Ext
    Boundary
    System_Boundary
    Enterprise_Boundary

### Container diagram

Import: `!includeurl https://raw.githubusercontent.com/RicardoNiepel/C4-PlantUML/master/C4_Container.puml`

Данный импорт также включает в себя все элементы контекстного уровня.

Поддерживаемые элементы:

    Container
    ContainerDb
    Container_Boundary

### Component diagram

Import: `!includeurl https://raw.githubusercontent.com/RicardoNiepel/C4-PlantUML/master/C4_Component.puml`

Данный импорт также включает в себя все элементы контекстного и контейнерного уровня.

Поддерживаемые элементы:

    Component
    ComponentDb

### Relations

Позволяют создавать связи между элементами. Все возможные элементы:

    Rel - расположение будет выбрано автоматически
    Rel_Back - в обратную сторону, также автоматически
    Rel_Neighbor - расположить рядом
    Rel_Back_Neighbor - рядом и в обратную сторону
    Rel_U - Up Вверх - конечный элемент расположить выше
    Rel_R - Right Вправо - конечный элемент расположить справа
    Rel_D - Down Вниз - конечный элемент расположить ниже
    Rel_L - Left Влево - конечный элемент расположить слева

Общий синтаксис такой:

```
Rel(from, to, "label", "technology")
```

## Настройки отображения

Вы можете управлять настройками отображения, добавив данные команды в свой `.puml` файл после import:

* `LAYOUT_TOP_DOWN` или `LAYOUT_LEFT_RIGHT` - располагать элементы сверху вниз или справа налево
* `LAYOUT_WITH_LEGEND()` - добавить легенду на схему
* `LAYOUT_AS_SKETCH()` - изменить стиль на "черновик"

Данные команды можно комбинировать вместе, например отобразить легенду и поменять стиль на "черновой".

## Дополнительная информация

Чтобы облегчить проектирование в IDE можно установить дополнительные плагины для проверки синтаксиса и отрисовки. 

### Требования для плагинов

Для их корректной работы необходимо иметь установленную Java и Graphviz.

- [Java][Java]: платформа для запуска PlantUML.
- [Graphviz][Graphviz]: необходима для расчёта позиций на диаграмме.

[Java]: http://java.com/en/download/ "Скачать Java"
[Graphviz]: http://www.graphviz.org/download/ "Скачать Graphviz"

### Быстрая установка graphviz для MacOS

```sh
brew cask install java
brew install graphviz
```

### Установка плагинов

* VSCode: https://github.com/qjebbs/vscode-plantuml
* Intellij IDEA: https://plugins.jetbrains.com/plugin/7017-plantuml-integration 

### Сниппеты

Для VSCode в репозитории в папке .vscode лежит сниппет __C4.code-snippets__ для ускорения ввода. Его нужно скопировать в папку .vscode Вашего проекта.

### Полезные ссылки и другие диагрммы

Сервис для онлайн генерации картинок: http://www.plantuml.com/plantuml/

В папке __entity-relationship__ также имеются два примера ER-диаграмм (не относятся к С4).
