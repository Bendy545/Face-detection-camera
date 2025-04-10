# Kamera s detekcí obličeje

## Úvod
Cílem tohoto projektu bylo navrhnout a zrealizovat kamerový systém, který dokáže rozpoznat obličej a který snímaný obraz přenáší pomocí wifi sítě na zobrazovací zařízení.

## Systém
Celý software je napsán v Arduino IDE a využívá základní knihovnu ESP32 CameraWebServer, která zajišťuje funkčnost webového serveru a komunikaci s kamerou. Webserver umožňuje přístup ke streamu a základním nastavením přímo z prohlížeče.

### Programování
Společně se systémem kamery byly využity dvě knihovny – mDNS a WiFiManager.
#### mDNS
- Knihovna mDNS (Multicast DNS) umožňuje přiřadit webovému serveru, který kamera vytvoří po připojení k WiFi síti, snadno zapamatovatelnou adresu esp32cam.local místo klasické IP adresy.
- Pro správnou funkčnost musí být zařízení, přes které chceme kameru ovládat, na stejné WiFi síti.
  ![image](https://github.com/user-attachments/assets/d90ac366-96f5-4dd3-8937-3bc7f8442035)

#### WiFiManager
- Přes WiFiManager lze nakonfigurovat, na jakou WiFi se má kamera připojit.
![image](https://github.com/user-attachments/assets/e8cb4b65-82d8-4f3d-8ab8-27d4ff4abc18)

## Spuštění
Po zapojení do napájení se automaticky vytvoří WiFi hotspot ke kterému musíme zadat heslo: 12345678, na který se lze připojit přes mobilní zařízení (např. chytrý telefon) nebo počítač. Na stránce, která je kamerou vytvořena, se lze připojit po zadání SSID a hesla k WiFi. Na webové rozhraní kamery, pomocí kterého lze ovládat její funkce, se lze připojit zobrazovacím zařízením, které musí být připojeno do stejné WiFi sítě jako je kamera, zadáním adresy esp32cam.local.
