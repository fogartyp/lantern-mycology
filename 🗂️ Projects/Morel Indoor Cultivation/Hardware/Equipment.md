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

## Bangson mini-fridge (owned; updated 2026-11-08)
- Brand Bangson, 2-door with freezer box. Patrick confirmed it matches the vendor page for the 3.2 cu ft model (model label number not yet logged).
- Vendor claims (marketing, untested): exterior 19.68 x 17.9 x 34.01 in; 5-position knob; fridge range 33.8-46.4F. Source: bangsontech.com 3.2 cu ft 2-door listing.
- **Measured by Patrick:** interior is not a clean box; lower ~1/4 is unusable (shelf and side wall). A tote 8.5 x 5 x 5 in fits; about 5 stacked, door closes (loaded check done with the stack).
- Compressor unit (R600a label seen in photos; which unit it was on is not confirmed). Keep R600a lines intact; unplug before cleaning.
- Use: first-run trays/spawn per [[06-decisions/Decision Log]]. Real internal temperature not yet logged; log with a probe before use.
- Wine cooler: brand, model, compressor type and range still unknown (front panel read about 48F, setpoint unverified).
