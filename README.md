# neuromask_emulator

Emulates neuromask data transferring via udp protocol

##Task:
To write python service which receives packets and writes the metrics they contain in JSON wide format, with configurable number of lines per file.
There can be many devices sending data in this format to one service.
Написать сервис, который поддерживает получение пакетов в таком формате от большого количества устройств и записывает содержащиеся в них данные в JSON, в широком формате, с выбранным количеством строк на файл.

##Packet description
Начало  передачи  2 байта
0xAAF0
Размер данных 2 байта

Уникальный идентификатор 3 байта
 
Метка времени 4 байта (миллисекунды от начала работы маски)
 
дальше идет key value датчиков
key: 1  байт value: 4 байта  (тип float)
 
Конец передачи данных 2 байта  
0xAAF1
