# Heya

Heya is a library for quickly building driving robots, including paddle driven NodeBoats. 

The following code is all you need to get a basic paddle boat up and running, using a web interface for controlling your NodeBoat with the arrow keys or WASD keys:

```
var heya = require('heya');
var Spark = require('spark-io');

heya.create({
  controller: new heya.controllers.WebKeyboard(),
  driver: new heya.drivers.PawelBot({
    leftServo: 'A0',
    rightServo: 'A1',
    io: new Spark({
      token: process.env.SPARK_TOKEN,
      deviceId: process.env.SPARK_DEVICE_ID
    })
  })
});

```

More information can be found on [Heya's GitHub page](https://github.com/bryan-m-hughes/heya).