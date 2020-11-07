# Max-Print-3D-Config

- X (Width): 300
- Y (Depth): 300
- Z (Height): 300


1. Build plate shape: Rectangular
2. Origin at center: NO
3. Heated bed: YES
4. G-code flavor: RepRap

### Start G-code:

    M104 S185 ; set extruder temp
    M190 S{material_bed_temperature_layer_0} ; wait for bed temp
    M104 S{material_print_temperature_layer_0} ; set extruder temp
    M402
    G28; HOME GERAL
    M400
    G29 V4 T; AUTO NIVELAMENTO
    M400
    G1 X1 Y1 Z0.8 F1000; VAI PRA PONTO DE PURGA
    M109 S{material_print_temperature_layer_0} ; wait for extruder temp
    G92 E0; RESETA EXTRUSOR
    G1 X1.0 E9.0 F1000.0 ; PURGA
    G1 X100.0 E12.5 F1000.0 ; PURGA
    M117 IMPRIMINDO...
    M400

### End G-code:

    M107 ; DESLIGA FAN
    G1 X-8
    G1 Y100
    G1 Z 300
    M104 S0 ; DESLIGA AQUECIMENTO BICO
    M140 S0 ; DESLIGA AQUECIMENTO MESA
    M84 ; DESLIGA MOTORES
    M300 S4 P1000 ; GERA BEEP

- Nozzle size: 0.5mm
- Compatible material diameter: 1.75mm

### Examples

    https://www.thingiverse.com/