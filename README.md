# MPSIEM-normalization
Normalization formulas for Positive Technologies MaxPatrol SIEM

Формулы нормализации для PT MaxPatrol SIEM для:
	прокси-сервера SQUID
	VPN-сервера SoftEther
	инструмента анализа IOCs Loki (при настройке отправки логов работы Loki по syslog на коллектор MP SIEM).
		
	
Правила локализации для указанных правил:
1. Proxy_Squid_syslog_access:
	Клиент прокси-сервера {src.ip} получил доступ к {dst.hostname}
2. VPN_attempting_to_connect:
	Клиент {subject.name} инициировал подключение к VPN {event_src.hostname} с хоста {src.hostname} с IP-адреса {src.ip}
3. VPN_authentication_failed:
	Аутентификация пользователя {subject.name} завершилась с ошибкой
4. VPN_client_connected:
	Клиент с IP-адресом {src.ip} подключился к порту {dst.port} узла {event_src.hostname} с порта {src.port} успешно
5. VPN_Session_allocated:
	Пользователь {subject.name} с MAC {src.mac} получил IP-адрес {src.ip} на шлюзе {dst.ip}
6. VPN_Session_disconnected:
	Клиент {subject.name} с IP-адресом {src.ip} и портом {src.port} отключился
7. VPN_Success_auth:
	Пользователь {subject.name} прошел аутентификацию на узле {event_src.host} со статусом {status}
8. LOKI_normalization_155:
	Ошибка на узле {event_src..host} модуля {subject.name} по анализу объекта {object.name}
9. LOKI_normalization_156:
	На узле {event_src.host} модулем {subject.name} обнаружен тип угрозы {object.property} по причине {reason}
10. LOKI_normalization_158:
	на узле {event_src.host} был инициализирован модуль {datafield1}
