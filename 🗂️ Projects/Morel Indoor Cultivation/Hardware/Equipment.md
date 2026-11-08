---
type: hardware
---
# Equipment

## Tent
North Spore BoomRoom II (listing: rack and tent 27"W x 19"D x 63"H, 5 racks, about 18 cu ft, Myco-Mister II ultrasonic humidifier, fan and ports). Cooling ability **not confirmed**. Located in the basement.

## Controllers owned
| Device | Use |
|---|---|
| MYCOntroller (BoomRoom humidity controller with sensor) | Tent humidity; specs unverified |
| Inkbird IHC200 humidistat (10 A, 100-265 VAC, 10-99% RH) | Tent (assigned). Decide primary vs backup against MYCOntroller |
| WH1436A 10 A 110 V | Heat only (no cooling). Tent heater |

## To buy (suggested, unpriced)
- 2x Inkbird ITC-308 (wine cooler, mini-fridge). Compressor delay setting PT = 3-5 min. Unit dial at maximum cold. Check compressor surge current against 10 A.
- Energy-monitoring plugs for heater, humidifier, each compressor.
- Sensors: Sensirion SCD41, SHT45, DS18B20 soil probe, capacitive soil moisture, float switch, leak sensors.

## Layout
| Zone | Control | ESP32 role |
|---|---|---|
| Tent | MYCOntroller / IHC200 humidity, WH1436A heat | monitor only |
| Wine cooler | ITC-308 | probe, leak, log cycles |
| Mini-fridge | ITC-308 | probe |

## Safety
GFCI outlets; electronics outside the wet zone; independent hardware thermostat and high-limit cutoff on heaters; relays default off; seal cable entries into the tent.

## Fan gap
No owned device does gentle timed air exchange (0.05-0.3 m/s in short bursts). First candidate for ESP32 control.

## Starter ESPHome config
See [[Hardware/morel-tent.esphome.yaml]] (untested; confirm pins).
