# LEDEqualizer

Документация: Music LED Equalizer

Хардуер:
- 5 LED диода
- breadboard
- JW-110x10 - свързващи проводници
- Audio splitter
- CONN AUDOIO JACK 3.5ММ
- Arduino Uno
- резистор 
- кондензатор 

КАК РАБОТИ? 

Audio Splitter-a получава аналогов сигнал на входа. Този аналогов сигнал се улавя с digitalRead();
Сгнала минава през така наречения LOW PASS FILTER, който се състои от резистор със съпротивление 16kΩ и кондензатор с капацитет 0,1µF. 
Филтърът гарантира, че всичко над 100Hz (BASS) честота ще бъде игнорирано. В софтуера на макета се записва променлива от тип float, която
не спира да приема вече пореобразуваните от филтъра сигнал. Стойността на тази променлива определя от къде до къде ще светят диодите спрямо
получения импулс. Разделя се най-голямата стойност на променливата на 5 равни по дължина честотни диапазона(колкото е броя на диодите). След което, 
константно се следи дали аналоговия сигнал е между тях.

КАКВО МОЖЕ ДА СЕ ИМПЛЕМЕТИРА?

Да се добавят други филтри за честота като MIDRANGE 500Hz - 1000Hz и TREBLE около 8kHz 
Да се мапват стойностите на аналоговия сигнал посредством сигмоидална функция, а не чрез статично зададена стойност.
Да се вгради на универсална платка.
