# Tinkerforge

Bindings and easy-to-use wrapper classes to make Crystal code interact with [TinkerForge](https://www.tinkerforge.com/) components.

## Installation

1. Add the dependency to your `shard.yml`:

   ```yaml
   dependencies:
     tinkerforge:
       github: mathalaxy/tinkerforge
   ```

2. Run `shards install`

## Usage

```crystal
require "tinkerforge"

staple = TF::Staple.new
staple.connect ip_address: "localhost", port: 4223

if staple.connected?
  staple.devices.each do |dev|
    case dev
    when TF::MasterBrick
      puts "Master of the universe!"
    when TF::RotaryPotiBricklet
      puts "Rotary Poti shows #{dev.position}"
    end
  end
end
```

## Development

Currently, there is only support for a very limited set of TF components, because these are what I use in other projects. Supported bricks/bricklets are:

- MasterBrick
- SilentStepperBrick
- RotaryPotiBricklet

If you would like to add support for other components, please feel free to contribute!

## Contributing

1. Fork it (<https://github.com/mathalaxy/tinkerforge/fork>)
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

## Contributors

- [mathalaxy](https://github.com/mathalaxy) - creator and maintainer
