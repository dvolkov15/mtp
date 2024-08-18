Добмашнее задание на тему Уязвимости и атаки на информационные системы

Задание 1




Уязвимости которые были обнаружены:

https://www.exploit-db.com/exploits/17491\
https://www.exploit-db.com/exploits/30020\
https://www.exploit-db.com/exploits/6122\



Задание 2

SYN-сканирование: это наиболее распространенный метод сканирования, при котором сканер отправляет запрос SYN на целевой порт. Если порт закрыт, то целевой хост отсылает ответ RST, а если порт открыт, то хост отсылает ответ SYN/ACK. Ответ SYN/ACK является сигналом для сканера, что порт открыт, и он заносит это в свой список.
FIN-сканирование: при этом методе сканирования сканер отправляет пакет FIN на целевой порт. Если порт закрыт, то хост игнорирует пакет, а если порт открыт, то хост отсылает пакет RST, что также указывает на открытый порт.
Xmas-сканирование: это расширение метода FIN-сканирования, при котором сканер отправляет пакет, включающий флаги FIN, URG и PSH. Если порт закрыт, то хост игнорирует пакет, а если порт открыт, то хост отсылает пакет RST, что также указывает на открытый порт.
UDP-сканирование: этот метод сканирования используется для сканирования портов, которые работают с протоколом UDP. В отличие от TCP, протокол UDP не поддерживает установление соединения, поэтому при сканировании порта UDP сканер отправляет запрос на целевой порт, а если порт закрыт, то хост отсылает ответ ICMP port unreachable.


В целом, все эти методы сканирования используются для обнаружения уязвимостей и открытых портов на сетевых устройствах, но они отличаются по способу отправки запросов и обработке ответов. Кроме того, существуют различные методы защиты от таких атак, например, могут быть настроены файрволы и системы обнаружения вторжений, которые могут блокировать подозрительный трафик.


Как отвечает сервер?

При сканировании в режиме SYN отправляется серия пакетов с установленным только флагом SYN, без установки флагов ACK и FIN. Если порт открыт, то сервер должен ответить пакетом с установленными флагами SYN и ACK.
При сканировании в режиме FIN отправляется пакет с установленным флагом FIN. Если порт закрыт, то сервер должен ответить пакетом с установленным флагом RST (сброс соединения).
При сканировании в режиме Xmas отправляется пакет с установленными флагами FIN, PSH и URG. Если порт закрыт, то сервер должен ответить пакетом с установленным флагом RST.
При сканировании UDP отправляются пакеты с произвольным содержимым на случайный порт. Если порт закрыт, то сервер должен ответить пакетом с установленным флагом ICMP Destination Unreachable. Однако, если порт открыт, то сервер может не отвечать на такие пакеты вообще.
