# opc2redis
OPC client &amp; required components
=============
opccli2redis.exe шлюз для создания дуплексного канала обмена данными между сервером ОРС и Redis.
============
opccli2redis.ini
[general]
# progid сервера ОРС
opc_server_name=easyopc.da2.1
# имя исполняемого файла, которого надо дождаться в памяти для подключения
opc_server_exe=easyopc
# айпишник Redis
redis_ip = 127.0.0.1
# флаг передачи значения ключа редиса в виде json объекта
to_redis_as_json=0

[opc_source]
# источник тэгов орс-сервер
# слева - имя в орс-сервере
# справа - имя в редисе
x1_1=x1_1
[redis_source]
# источник тэгов редисё
# слева - имя в редисе
# справа - имя в орс-сервере
x1_1=x1_124
=============
OPC Core Components Redistributable (x86) 105.1.zip - системные библиотеки поддержки технологии ОРС. Требует Microsoft .NET Framework 2.0.
==============
OPCExplorer.exe тестовый клиент ОРС.

последовательность:
1. Установить OPC Core Components. 
2. Проверить доступность сервера через opcexplorer.
3. Проверить и изменить настройки шлюза в инифайле.
4. Добавить ярлык для opccli2redis.exe в автозагрузку, например планировщиком задач.
5. Запустить opccli2redis.exe.