# Apple-Watch

# Умные часы для оповещения о приближающемся поезде

## Описание проекта
Этот проект представляет собой систему для умных часов, которая:
1. Определяет расстояние до приближающегося поезда
2. Оповещает рабочих вибрацией, если поезд находится ближе 2 км

## Основные функции
- Подключение к Wi-Fi сети
- Подписка на MQTT-топик для получения координат поезда
- Расчет расстояния между текущим местоположением и поездом
- Визуальное отображение информации на OLED-дисплее
- Вибрационное оповещение при приближении поезда

## Технические характеристики
- Микроконтроллер: ESP32-S3
- Дисплей: OLED 128x64 пикселей (SSD1306)
- Протокол связи: MQTT
- Интерфейс: I2C для дисплея

## Настройка
1. Укажите параметры Wi-Fi в переменных:
   
   const char* ssid = "****";
   const char* password = "*********";

3. Настройте параметры MQTT-брокера:
   
   const char* mqtt_server = "*****************";
   const int mqtt_port = ******;
   const char* mqtt_user = "*****";
   const char* mqtt_pass = "*******";
   const char* mqtt_topic = "******";
   

4. Установите координаты местоположения рабочих:
   float x2 = 56.770509;  // Широта
   float y2 = 60.758024;  // Долгота


## Принцип работы
1. Часы подключаются к Wi-Fi и MQTT-брокеру
2. При получении новых координат поезда через MQTT:
   - Вычисляется расстояние между поездом и заданным местоположением
   - Если расстояние меньше 2 км - активируется вибрационный сигнал
   - На дисплей выводится информация о расстоянии до поезда

## Требования
- Библиотеки:
  - WiFi
  - PubSubClient
  - Wire
  - Adafruit_SSD1306
  - Adafruit_GFX

## Автор
 Ufa-Dynamics, Данияр Камаев
