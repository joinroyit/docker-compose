#php xdebug

- Dockerfile - установка, и включение расширения.
- php.ini - установка "xdebug.mode=debug, xdebug.idekey=PHPSTORM"
- docker-compose.yml - XDEBUG_CONFIG: "client_host=192.168.x.xxx"; PHP_IDE_CONFIG: "serverName=alias"
- настройка связей. phpstorm - settings -> PHP -> Servers