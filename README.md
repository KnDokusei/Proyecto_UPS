# UPS shield para STM32 Nucleo

Fuente de alimentación ininterrumpida en formato shield para placas STM32 Nucleo, diseñada en Altium Designer. Se alimenta por USB y carga una batería de litio de una celda, que mantiene la salida cuando falta el USB.

Proyecto en equipo, noviembre de 2025.

## Bloques

| Bloque | Componente | Función |
|---|---|---|
| Entrada | USB4125-GF-A | Conector USB |
| Carga | MCP73831T-2DCI | Cargador lineal Li-Ion/Li-Po de 4,2 V |
| Batería | JST PH de 2 pines (B2B-PH-K-S) | Conexión de la celda |
| Elevador | TPS61090 | Convertidor elevador síncrono desde la batería |
| Selección | TPS2121 | Multiplexor entre la entrada USB y la salida del elevador |
| Supervisión | ATtiny414 | Microcontrolador, programado por UPDI |
| Programación | Samtec TSM-103-01-S-DV (2×3) | Conector UPDI |
| Interfaz | TL3365 y dos LED | Pulsador e indicadores |

Señales entre bloques: `USB_Present`, `Batery_Charging`, `LBO_FLAG` (batería baja, del TPS61090), `EN_BOOST` y `UPDI`.

El shield usa la huella Arduino Uno R3, que es la de los conectores Arduino de las Nucleo.

## Archivos

- `UPS_project.PrjPcb`: proyecto principal. Abrirlo en Altium Designer.
- `UPS.SchDoc`: esquemático.
- `PCB_SHIELD_UPS.PcbDoc`: PCB del shield.
- `*.SchLib` y `*.PcbLib`: librerías de los componentes.
- `PCB_Project_2.PrjPcb` y `PCB1.PcbDoc`: otra versión de la placa sobre el mismo esquemático.
