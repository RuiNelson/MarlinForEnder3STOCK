# For Cura:

## Starting Gcode:

    ; BEGIN STARTING -----------
    G28                                                 ; Home
    G29                                                 ; AutoLevel
    G90      											; Absolute positioning
    G1 X0.0 Y000.0 Z2.0 F03000                          ; Move up a bit
    M140 S{material_bed_temperature_layer_0}			; Start heating the Bed
    M104 S{material_print_temperature_layer_0} 			; Start heating the Hotend
    M109 S{material_print_temperature_layer_0} 			; Wait for hotend temp
    M190 S{material_bed_temperature_layer_0} 			; Wait for bed temp
    G92 E0												; Reset Extruder
    G1 E20 F1200 	                                    ; Purge 20mm
    G92 E0                                              ; Reset Extruder Again
    G1 X0 Y0 Z0 F1000.0                                 ; Start Position For Lines
    G1 Y60.0 E9.0 F1000.0                               ; First Intro line
    G1 Y100.0 E21.5 F1000.0                             ; Second Intro line
    G92 E0 												; Final Reset Extruder
    ; ----------- END INIT

## Ending Gcode:

    ; BEGIN ENDING -----------
    M104 S0                         ; Cooldown Hotend
    M140 S0                         ; Cooldown Bed
    G91                             ; Set coordinates to relative
    G1 Z10                          ; Up 1cm
    G90                             ; Absolute coordinates
    G1 X0 Y235 F99999               ; Tray to the front
    M300 S2500 P2000                ; Beep
    M84                             ; Disable stepper motors
    ; ----------- END ENDING


# For Slic3r:

## Starting Gcode:

    ; BEGIN STARTING -----------
    G28                                                 ; Home
    G29                                                 ; AutoLevel
    G90      											; Absolute positioning
    G1 X0.0 Y000.0 Z2.0 F03000                          ; Move up a bit
    M140 S[first_layer_bed_temperature]		        	; Start heating the Bed
    M104 S[first_layer_temperature] 		        	; Start heating the Hotend
    M109 S[first_layer_temperature]			            ; Wait for hotend temp
    M190 S[first_layer_bed_temperature]	     			; Wait for bed temp
    G92 E0												; Reset Extruder
    G1 E20 F1200 	                                    ; Purge 20mm
    G92 E0                                              ; Reset Extruder Again
    G1 X0 Y0 Z0 F1000.0                                 ; Start Position For Lines
    G1 Y60.0 E9.0 F1000.0                               ; First Intro line
    G1 Y100.0 E21.5 F1000.0                             ; Second Intro line
    G92 E0 												; Final Reset Extruder
    ; ----------- END INIT

## Ending Gcode:

    ; BEGIN ENDING -----------
    M104 S0                         ; Cooldown Hotend
    M140 S0                         ; Cooldown Bed
    G91                             ; Set coordinates to relative
    G1 Z10                          ; Up 1cm
    G90                             ; Absolute coordinates
    G1 X0 Y235 F99999               ; Tray to the front
    M300 S2500 P2000                ; Beep
    M84                             ; Disable stepper motors
    ; ----------- END ENDING
