# ST-Link v2.1 rev.B

<p align="center">
  <img src="files/preview_1.jpg" height="200"/>
  <img src="files/preview_2.jpg" height="200"/>
</p>

Программатор ST-Link V2-1 это внутрисхемный отладчик и программатор для микроконтроллеров серий STM32.
Программатор имеет SWD SWO RESET ( логический уровень 3.3 Вольта ) интерфейсы для работы с любым STM32 микроконтроллером, 
установленным на программируемой плате, VCP ( Virtual COM Port ) для использования UART интерфейса одновременно
с отладкой и  MSD (Mass Storage Device) для прошивки с помощью копирования файла .bin через проводник. Программатор
поддерживает автоматическое обновление встроенной прошивки для обеспечения последующей поддержки компанией ST.

`Schematic_ST-LINK_2.1_rev.B.pdf` - схема программатора

`Gerber_PCB_ST-LINK_2.1_rev.B.zip` - Gerber файл платы

`Protected-2-1-Bootloader.bin` - прошивка, содержащая загрузчик

Внимание: джампер SJ1 "PWRSELECT" распаивается в соответствии с измеряемым программатором напряжением питания - 
при замыкании верхней позиции измеряется напряжение питания МК непосредственно программатора, при замыкании нижней позиции
измеряется напряжение программируемого МК.

## Процесс установки:

 * Устанавливаем из архива программу STM32 ST-LINK Utility v4.3.0 ( с более поздними версиями работать не будет ).
	
 * Заливаем Protected-2-1-Bootloader.bin через SWD или DFU ( кому как удобнее ) на наш созданный программатор.

 <p align="center">
  <img src="files/01_connect.png" height="300"/>
  <img src="files/02_program.png" height="300"/>
  <img src="files/03_select_file.png" height="300"/>
  <img src="files/04_start.png" height="300"/>
</p>

 * Подключаем только что прошитый программатор через USB и в программе ST-LINK Utility v4.3.0 выбираем -ОБНОВЛЕНИЕ.

 <p align="center">
  <img src="files/05_update.png" height="300"/>
  <img src="files/06_prepare.png" height="300"/>
</p>

 * Нам предложат несколько вариантов : нам нужен STM32 + VCP + MSD ( для STM32F103CBT6 ) выбираем его и жмем обновить. 
 В случае использования МК с 64 кБ памяти ( STM32F103C8T6 ) выбираем STM32 + Audio ( вариант без MSD ).

 <p align="center">
  <img src="files/07_select_version.png" height="300"/>
</p>

 * Для обновления до последней версии прошивки можно использовать 
 <a href="https://www.st.com/en/development-tools/stm32cubeprog.html">STM32 Cube Programmer</a>.

  <p align="center">
  <img src="files/08_CubeProg.png" height="300"/>
</p>

 * Для работы версии 2-1 и VCP устанавливаем драйвера которые идут в данном архиве.
	
