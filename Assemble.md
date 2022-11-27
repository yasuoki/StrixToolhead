## Insert nuts
<img src="img/fig1.jpg" width="70%"><br>
<img src="img/fig2.jpg" width="70%"><br>
<img src="img/fig3.jpg" width="70%"><br>
<img src="img/fig4.jpg" width="70%"><br>
<img src="img/fig5.jpg" width="70%"><br>
<img src="img/fig6.jpg" width="70%"><br>

## Sleeve bearings
<img src="img/fig7.jpg" width="70%"><br>
<img src="img/fig8.jpg" width="70%"><br>

## Z Probe
<img src="img/fig9.jpg" width="70%"><br>
<img src="img/fig10.jpg" width="70%"><br>
<img src="img/fig21.jpg" width="70%"><br>
<img src="img/fig22.jpg" width="70%"><br>
<img src="img/fig23.jpg" width="70%"><br>

## Hotend
<img src="img/fig11.jpg" width="70%"><br>
<img src="img/fig12.jpg" width="70%"><br>

## Extruder
<img src="img/fig15.jpg" width="70%"><br>

## Mounting on Rail
<img src="img/fig13.jpg" width="70%"><br>
<img src="img/fig14.jpg" width="70%"><br>
<img src="img/fig16.jpg" width="70%"><br>
<img src="img/fig17.jpg" width="70%"><br>
<img src="img/fig18.jpg" width="70%"><br>

## Parts cooling fan
<img src="img/fig19.jpg" width="70%"><br>

## Hotend cooling fan
<img src="img/fig20.jpg" width="70%"><br>

## Microswitch and Servo
<img src="img/fig24.jpg" width="70%"><br>

## X End Stop
<img src="img/fig27.jpg" width="70%"><br>
<img src="img/fig28.jpg" width="70%"><br>

## Wirering
<img src="img/fig25.jpg" width="70%"><br>
<img src="img/fig26.jpg" width="70%"><br>
<img src="img/fig29.jpg" width="70%"><br>

## Configuration
~~~
#####################################################################
#   Retractable Probe Servo
#####################################################################
[servo RetractableProbe]
pin: PB6
initial_angle: 0
maximum_servo_angle = 180
minimum_pulse_width = 0.0005
maximum_pulse_width = 0.0024

[gcode_macro PROBE_OUT]
gcode:
    SET_SERVO SERVO=RetractableProbe ANGLE=180
    G4 P800

[gcode_macro PROBE_IN]
gcode:
    SET_SERVO SERVO=RetractableProbe ANGLE=0
    SET_SERVO SERVO=RetractableProbe WIDTH=0
    G4 P800

#####################################################################
#   Probe
#####################################################################
[probe]
pin: ^PB7
x_offset: -27.49
y_offset: 13.85
z_offset: 0
speed: 10.0
samples: 3
samples_result: median
sample_retract_dist: 3.0
samples_tolerance: 0.006
samples_tolerance_retries: 3
deactivate_on_each_sample: False
activate_gcode:
    PROBE_OUT
deactivate_gcode:
    PROBE_IN
~~~
