# Van float switch

https://nassimm.github.io/van-float-switch/

A single web page that switches the alternator float mode on a Renault Master III / Opel Movano B (X62).
It talks to the van's USM through an ELM327-style Bluetooth LE adapter using Web Bluetooth
(on iPhone, open it in the Bluefy browser).

- **Float off**: the alternator holds the full charging voltage (`C_B_FloatingInhibit` = 1).
- **Float on**: factory behaviour (`C_B_FloatingInhibit` = 0).

Once float is disabled, the alternator holds its charging voltage (about 14.3 V) for as long as the engine runs,
instead of dropping to 13.5 V when the starter battery is full. The setting stays until you switch it back.

The page reads the setting before writing and reads it back afterwards. It can send only those two writes.

At your own risk. The commands were verified on one 2016 Movano (USM `USM_2010_X61_X62_016_7`);
other vans may have a USM version without this setting.
