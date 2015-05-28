# The Particle Core (aka Spark Core)

NodeBoats will use the [Particle Core](https://www.particle.io) (formerly known as the Spark). This is a microcontroller, similar to the Arduino in functionality, but with an integrated wifi chip. Perfect for Bots, like Boats, that need to be physically untethered from your computer!

### Setting Up Your Particle

Before you set up your Particle, make sure you have version 0.10 of [Node JS](https://nodejs.org) installed on your computer! If you use a different version or IO, you'll run into compatibility issues and it'll be a bad time.

#### Spark CLI

The Particle has a nifty mobile app that can help you claim it, but you should NOT use that! In a conference setting like this, it can have unpredictable results. Instead you should use spark-cli, Particle's command line tool.

You want to install version 1.2.0 of spark-cli. You can do this via npm:
```bash
npm install -g spark-cli@1.2.0
```

Once spark-cli is installed, you should plug in your Particle via USB. The light should be flashing blue. If it is not, hold down the "Mode" button until it does. Then run the command:
```bash
spark setup
```

Spark-cli will ask you to log in to your account, or create an account if you do not yet have one. Follow the instructions to set up your core. Make sure to take note of your Access Token and Core ID. You'll need these later.After you enter wifi credentials as part of your setup process, your Particle should restart. It will quickly blink green to indicate that it is connecting to the wifi. Once it connects it should begin breathing cyan. Press `Enter` to claim your core. Once it flashes rainbows your Core is claimed! Press `Enter` again. You can now give your Core a convenient nickname to substitue for the Core ID if you wish.

If, during this process, your Core starts blinking other colors, you can find out what they mean [here](http://docs.particle.io/core/#leds).

#### Voodoospark Firmware

When working with Johnny-Five, instead of using the Spark Cloud you'll be communicating with the Spark device locally using a custom firmware called VoodooSpark. VoodooSpark mimics the standard Spark firmware API and provides access to the Spark functionality via a local TCP connection.

This means we need to flash the spark with the [Voodoospark firmware](https://github.com/voodootikigod/voodoospark). The spark-cli actually comes bundled with Voodoospark, so doing this is pretty simple. Just type:
```bash
spark flash <enter your core id here> voodoo
```

Your Core will flash a bunch of colors to indicate that the firmware is updating, and when it's settled back into the breathing cyan pattern, the flash has been complete!

#### Moving on to Code!

Now you just need to install [Johnny-Five]() and it's [Spark-IO](https://github.com/rwaldron/spark-io) plugin, and you're ready to start coding!

```bash
# cd into your project directory first! 
npm install --save johnny-five
npm install --save spark-io
```

You're now all set to head over to the Spark-IO docs and try its "Hello World" - [blinking an led](https://github.com/rwaldron/spark-io#johnny-five-io-plugin)! Then move on to the [Johnny-Five](http://johnny-five.io) docs and have fun building your boat!
