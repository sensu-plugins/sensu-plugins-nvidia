## sensu-plugins-nvidia

[ ![Build Status](https://travis-ci.org/sensu-plugins/sensu-plugins-nvidia.svg?branch=master)](https://travis-ci.org/sensu-plugins/sensu-plugins-nvidia)
[![Gem Version](https://badge.fury.io/rb/sensu-plugins-nvidia.svg)](http://badge.fury.io/rb/sensu-plugins-nvidia)
[![Code Climate](https://codeclimate.com/github/sensu-plugins/sensu-plugins-nvidia/badges/gpa.svg)](https://codeclimate.com/github/sensu-plugins/sensu-plugins-nvidia)
[![Test Coverage](https://codeclimate.com/github/sensu-plugins/sensu-plugins-nvidia/badges/coverage.svg)](https://codeclimate.com/github/sensu-plugins/sensu-plugins-nvidia)
[![Dependency Status](https://gemnasium.com/sensu-plugins/sensu-plugins-nvidia.svg)](https://gemnasium.com/sensu-plugins/sensu-plugins-nvidia)

## Functionality

Plugin to collect metrics from your NVIDIA GPU.

### metrics-nvidia.rb

Collects metrics by calling `nvidia-smi` internally.

#### parameters

- `-s, --scheme`: The scheme to concatenate the metrics with (default: `HOSTNAME.nvidia`)

#### metrics

Multiple GPUs are supported and labeled by BusID in Hex (e.g. `nvidia.bus0x02.temperature.gpu`). For each PCI bus you will get the following metrics:

- `nvidia.busBUS_IN_HEX.fan.speed`: Speed of the card's fan (RPM)
- `nvidia.busBUS_IN_HEX.memory.free`: Unused memory available to the card (MiB, mebibyte)
- `nvidia.busBUS_IN_HEX.memory.total`: Total amount of memory available to the card (MiB, mebibyte)
- `nvidia.busBUS_IN_HEX.memory.used`: Memory used by the card (MiB, mebibyte)
- `nvidia.busBUS_IN_HEX.power.draw`: Power draw of the card (Watt)
- `nvidia.busBUS_IN_HEX.temperature.gpu`: Temperature of the card (Degree Celsius)
- `nvidia.busBUS_IN_HEX.utilization.gpu`: GPU utilization of the card (percent)
- `nvidia.busBUS_IN_HEX.utilization.memory`: memory utilization of the card (percent)

*If you do not get all of the listed values, you GPU probably does not support the feature. To check, you can query it yourself by running* `nvidia-smi --query-gpu=METRIC --format=csv`.  
(e.g. `nvidia-smi --query-gpu=power.draw --format=csv`)


## Usage

To collect metrics with the scheme of your choice:

```plain
metrics-nvidia.rb --scheme YOUR_SCHEME_HERE
```

## Installation

```plain
sensu-install --plugin sensu-plugins-nvidia
```

In order to use this plugin you will need the official NVIDIA command line interface `nvidia-smi` which is distributed with their drivers.

For more help see [Installation and Setup](http://sensu-plugins.io/docs/installation_instructions.html).

