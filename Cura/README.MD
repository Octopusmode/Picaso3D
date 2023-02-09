# Добавление принтера Picaso X/X Pro в Cura
---

В зависимости от версии Cura, содержимое папки resources из архива Ultimaker **Cura_PicasoX.zip** распаковать в соотвествующую папку (указаны пути установки Cura по-умолчанию):

**Cura 5.x:**
C:\Program Files\Ultimaker Cura 5.x\share\cura\resources\

**Cura 4.x:**
C:\Program Files\Ultimaker Cura 4.10\resources\

Запустить Cura. В списке доступных принтеров появится Picaso/Designer XPro.

![Добавление принтера](./img/cura_select_printer.png)

В поле "Начальный G-код для экструдера", чтобы после переключения сопел активное сопло прочищалось в специальном очистителе, необходимо прописать:

*Extruder 1 Start G-code (для первого или единственного экструдера):*

*T10 I5 S1 R1 P1*

*Extruder 2 Start G-code (для второго экструдера):*

*T11 I5 S1 R1 P1*

![cura_extruder_1](./img/cura_extruder_1.png)

![cura_extruder_2](./img/cura_extruder_2.png)

Для очистки сопел возможно использовать черновую башню, а не сопливчики: для этого в настройках принтера включить "быстрое переключение сопел".

Для Designer X необходимо изменить количество экструдеров (extruder count) = 1

![Добавление принтера](./img/cura_extruders_count.png)

Икс-серия сама всё умеет делать и при печати G-кода принтер выполняет зашитый в прошивку обязательный код перед печатью и после печати.

Для корректной работы системы контроля подачи пластика добавьте специальный скрипт. Для этого в меню *Extensions > Post processing > Modify G-code* нажмите *“Add a script”* и выберите *Search and Replace*. Впишите следующие скрипты:

*Search:*
*;LAYER:*

*Replace:*
*M532 X0 L*

![cura_script_0](./img/cura_script_0.png)

Дополнительная информация и инструкция по использованию сторонних слайсеров (Cura, PrusaSlicer) для принтеров Designer Classic, X, XPro, XL, XLPro в Центре поддержки: http://helpcenter.picaso-3d.ru/we-answer
