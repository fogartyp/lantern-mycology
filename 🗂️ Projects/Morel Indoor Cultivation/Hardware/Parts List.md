---
type: hardware
status: draft-not-ordered
updated: 2026-11-08
---
# Parts list (monitor-only nodes)

**Nothing here is ordered.** Ordering needs Patrick's approval. Prices were read from vendor pages on 2026-11-08, before tax and shipping, and may change. Shipping across five vendors is not compared.

Configs: [[Hardware/morel-tent.esphome.yaml]] (tent node) and [[Hardware/bangson-fridge.esphome.yaml]] (Bangson node). Both are validated with `esphome config` only; neither is flashed or tested on hardware.

## To buy
| Part | Qty | Price | Node / use | Source |
|---|---|---|---|---|
| ESP32-DevKitC-32E | 1 | $9.80 | Tent | Mouser |
| Adafruit SCD-41 CO2/temp/RH | 1 | $49.95 | Tent air | adafruit.com/product/5190 |
| Adafruit SHT45 temp/RH | 1 | $12.50 | Tent twin sensor | adafruit.com/product/5665 |
| Waterproof DS18B20 probe | 1 | $9.95 | Tent soil/surface temp | adafruit.com/product/381 |
| DFRobot SEN0193 moisture sensor | 1 | $5.90 | Tray moisture (raw until calibrated) | dfrobot.com/product-1385.html |
| ELECALL ES10010 4" float switch | 1 | $8.99 | Reservoir low | Amazon B01LWX97CC |
| Adafruit hookup wire set, 22AWG, 6 x 25 ft | 1 | $19.95 | Both nodes | adafruit.com/product/3111 |
| Hammond 1591USBK ABS enclosure | 1 | $10.54 | Tent node | DigiKey |
| ESP32-DevKitC-32E | 1 | $9.80 | Bangson | Mouser |
| Waterproof DS18B20 probe | 2 | $19.90 | Bangson top and bottom air | adafruit.com/product/381 |
| Inkbird ITC-308 | 1 | $35.99 | Bangson control | inkbird.com |
| **Priced total** | | **$193.27** | | |

## Owned
Raspberry Pi, TP-Link power-monitoring plugs (model unconfirmed), Make resistor pack (4.7 kOhm to be checked), electrical wire (type unknown).

## Unpriced
5 V USB supply per node, cable glands, board standoffs, second enclosure for the Bangson node.

## Notes and checks
- **Enclosure:** Hammond datasheet (rev 07.01.2020) gives inside 4.470 x 4.470 x 2.161 in and outside 4.724 x 4.724 x 2.323 in. ESP32-DevKitC-32E board is 54.4 x 27.9 mm (Mouser). Height with headers not found; measure on arrival. IP54 is from the DigiKey listing only. The drawing has no holes, so cable entries need glands or grommets.
- **Float switch:** listing is a vendor claim. Normally-open vs closed is not stated; test with a multimeter and flip `inverted` in the config if needed. Mounting in the Myco-Mister II tank is unresolved. "110V" in the title is a rating; we use 3.3 V only. Mains never touches it. The PumpSpy VS-200 was rejected (120 VAC sump pump switch).
- **Probe addresses:** the Bangson config has placeholder DS18B20 addresses. Flash once, read real addresses from the boot log, paste in.
- **ITC-308:** probe inclusion not confirmed. The compressor's current and surge against the ITC-308 rating are unchecked. Set PT delay to 3-5 min, fridge dial at max cold. Patrick does the wiring. Originally planned to wait for the empty-chamber test; Patrick chose to include it.
- **Rejected:** North Spore autofill float valve (different part: it fills the tank and sends no signal); Adafruit enclosures 903 and 905 (out of stock when read); ESP32-S3 boards (would need a pin-map change).
- **Not in this list:** a second ESP32 config for anything beyond the Bangson, energy monitoring (TP-Link plugs instead), the wine cooler (brand and model unknown).
