Team-Gauntl33t-Project-Lance
============================

VR Haptic Feedback Glove

**Notes on 3D printing**

The `.stl` files included in this repository were created with Blender, consequenlty for some users, the model appears to be broken and cannot be printed as-is. If this is the case, the model can be repaired with [Netfabb](http://www.netfabb.com/).

**Modifying the existing .stl files**

If you're a total noob to CAD, [TinkerCAD](https://tinkercad.com/) is recommended.

**Notes on Servos**

Servos used for this project are the Hitec HS-322HD. Other servos could be used, but the servo horn design may not fit. Feel free to submit horn designs that fit other servos!

Inspiration for the horns taken from the [InMoov robot hand](http://www.thingiverse.com/thing:17773/#instructions), whose design process can be found [here](http://funlab.fr/funwiki/doku.php?id=projets:construction_du_robot_inmouv) (the link is in French, but Google Translate does a pretty good job).

**Notes on Controller**

Which Microcontroller to use? Since all that's really required to work with the motors and the Peltier cells (coming soon!) is an H-Bridge (for reversing the current directions so you can change the Peltier cells from cooling to heating) and some PWM, there's no definitive reason to use one over the other.

**If you are using the Raspberry Pi**

For controlling using software PWM (which is accurate enough for our purpouses) on the Raspberry PI install [RPIO](https://pypi.python.org/pypi/RPIO) and to get started controlling the motors use the following example.


```
from RPIO import PWM

servo = PWM.Servo()

# Add servo pulse for GPIO 17 with 400µs which is the minimum for the Hitec HS-322HD
servo.set_servo(17, 400)

# Add servo pulse for GPIO 17 with 2400µs (2.4ms) which is the maximum for the Hitec HS-322HD
servo.set_servo(17, 2000)

# Clear servo on GPIO17
servo.stop_servo(17)
```

**If you are using an Arduino**

There's PWM pins already included! No worries!
