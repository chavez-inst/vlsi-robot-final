# Robot Móvil: Seguidor de Luz con Evasión de Obstáculos
**Proyecto Final - Diseño Digital VLSI 2026-2**

---

## Integrantes
* Chávez López B. Alejandro
* Chávez García Isaac
* De La Cruz Eduardo Miranda
* Saldivar Hernández Brian

---

## Descripción
Este proyecto consiste en un robot autónomo basado en la FPGA DE10-Lite, que debe seguir una fuente de luz y evadir obstáculos mediante sensores ultrasónicos.

---

## Checklist

### Fase 1: Subsistemas Aislados (Pruebas de Escritorio)
* [ ] **HW:** Armar el circuito acondicionador de los LDRs con el LM339 y calibrar con potenciómetros para obtener `0` o `1` lógico de forma limpia.
* [ ] **SW:** Adaptar el módulo PWM para motores.
* [ ] **SW:** Crear el módulo de lectura para el sensor HC-SR04 (generación de *Trigger* y conteo de tiempo de *Echo* para calcular distancia).
* [ ] **Integración:** Conectar el puente H a los motores y validar velocidades con el módulo PWM de la FPGA.

### Fase 2: Ensamblaje y Lógica Base
* [ ] **HW:** Ensamble del chasis, motores, batería y el regulador de 5V.
* [ ] **SW:** Diseñar FSM Principal con estados básicos: `Buscar` y `Seguir`.
* [ ] **Integración:** Primera prueba en piso conectando los LDRs a la FPGA para validar que el chasis persigue la luz correctamente.

### Fase 3: Comportamiento Complejo y Evasión
* [ ] **HW:** Montar y cablear los 4 sensores ultrasónicos perimetrales.
* [ ] **SW:** Expandir la FSM para los estados: `Esquiva`, `Giro-esquina` y `Meta`.
* [ ] **SW:** Implementar un temporizador paralelo para detección de atasco (maniobra de escape tras $N$ segundos estático).
* [ ] **Integración:** Pruebas en arena con obstáculos. Ajuste de umbrales y tiempos de giro.

### Fase 4: Adicionales y Entregables
* [ ] **SW:** Asignar salidas de depuración a la tarjeta (mostrar estado de FSM y % duty cycle en displays de 7 segmentos o LEDs).
* [ ] **Docs:** Recopilar esquemas eléctricos (schematics) y diagrama de bloques final.
* [ ] **Docs:** Grabar video demo mostrando todo el recorrido.
* [ ] **Docs:** Finalizar el reporte en LaTeX con arquitectura, verificación y resultados.

---

## Lista de Materiales

### Procesamiento
* [ ] 1x Tarjeta FPGA Terasic DE10-Lite

### Actuadores y Movimiento
* [ ] 1x Chasis para robot móvil (menos de 20 x 20 x 20 cm).
* [ ] 2x Motores DC con motorreductor.
* [ ] 2x Llantas para a los motores.
* [ ] 1x Caster wheel (para apoyo delantero/trasero).
* [ ] 1x Driver Puente H L293D o L298N para el control de potencia de los motores (buscar el L298N).

### Sensores
* [ ] 4x Módulos HC-SR04 (Sensores ultrasónicos para distancia y evasión).
* [ ] 4x Fotorresistencias (LDR) para la detección del vector de luz.

### Acondicionamiento de Señal
* [ ] 1x Circuito Integrado LM339 (Comparador de voltaje cuádruple) para digitalizar la señal de los LDRs.
* [ ] 4x Potenciómetros de 10kΩ o 50kΩ para calibrar el umbral de luz del comparador.
* [ ] Resistencias varias.
* [ ] 1x Circuito Integrado 74LS04N (Compuertas NOT) opcional.

### Energía y Cableado
* [ ] 1x Batería LiPo de 2 celdas (2S) o 3 celdas (11.1V) a 7.4V entre 1000 mAh y 2200 mAh (buscar la de 2 celdas).
* [ ] 1x Módulo Regulador de Voltaje DC-DC LM2596 (Buck Converter) calibrado a salida de 5V fijos (para no quemar la DE10-Lite ni los sensores).
* [ ] 1x Protoboard mediano.
* [ ] Jumpers variados.