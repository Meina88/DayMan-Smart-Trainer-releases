# DayMan Smart Trainer — Firmware releases

Binarios del firmware **PDM Smart Trainer**: una controladora BLE FTMS para
ESP32-S3 que reemplaza la electrónica de control de un rodillo Wahoo KICKR v6.
Este repositorio solo contiene los releases. El código fuente se mantiene en
un repositorio privado.

> ⚠️ **Proyecto experimental, de uso personal.** El firmware maneja el freno
> electromagnético del rodillo. Usalo bajo tu propia responsabilidad.

## Qué hay en cada release

| Archivo | Qué es |
|---|---|
| `pdm_smart_trainer.bin` | Imagen de la aplicación para OTA (partición `ota_0` / `ota_1`) |

Cada release corresponde a un tag `vX.Y.Z` del código fuente y lo compila
automáticamente una GitHub Action, con ESP-IDF v5.5.1 y target `esp32s3`.

## Cómo actualizar

### Desde el rodillo (recomendado)

1. Conectate a la red Wi-Fi **PDM-Trainer** y abrí http://192.168.4.1.
2. En **Actualizar firmware → Wi-Fi de tu casa**, cargá tu red para que la
   placa tenga internet (se hace una sola vez).
3. Al abrir la página, la placa busca sola la última versión. Si hay una
   nueva, tocá **Instalar**.

Durante la descarga el freno queda suelto, y al terminar la placa se
reinicia sola. Si el firmware nuevo falla al arrancar, un reset vuelve a la
versión anterior.

### Manual

Descargá `pdm_smart_trainer.bin` del release y cargalo en
**Actualizar firmware → Desde un archivo**.

## Requisitos

- Una placa que ya tenga un firmware con soporte OTA, es decir con la tabla
  de particiones de dos slots de 3 MB. La primera instalación se hace por USB
  (puerto COM) desde el código fuente, no con estos binarios.
- Un ESP32-S3 con 16 MB de flash (probado en una YD-ESP32-S3).
