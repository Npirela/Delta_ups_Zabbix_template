# Delta_ups_Zabbix_template
zabbix Delta UPS model GES-103R212035 using the `DeltaUPS-MIB` template

# Template Delta UPS GES-103R212035 SNMP

## Overview

This template provides comprehensive monitoring for the Delta UPS model GES-103R212035 using the `DeltaUPS-MIB`. It is designed for Zabbix 7.0+ and supports all versions of SNMP (v1, v2c, v3).

It collects metrics across various aspects of the UPS including power input/output, battery status, environmental conditions, alarms, configuration, and control parameters. It includes Low-Level Discovery (LLD) for monitoring multiple input, output, and bypass lines dynamically.

## Authors

- npirela
- Qwen Ai
- MOD FROM 
 SIM template
 https://github.com/zabbix/community-templates/tree/main/Power_(UPS)/template_delta_ups_snmpv1/6.0

## Template

### Macros

| Name | Description | Default |
|------|-------------|---------|
| `{$BATTERY.CHARGE.CRIT}` | Critical threshold for battery charge (%) | `20` |
| `{$BATTERY.CHARGE.WARN}` | Warning threshold for battery charge (%) | `50` |
| `{$INPUT.VOLTAGE.HIGH.WARN}` | Warning threshold for high input voltage (V) | `260` |
| `{$INPUT.VOLTAGE.LOW.WARN}` | Warning threshold for low input voltage (V) | `200` |
| `{$OUTPUT.LOAD.HIGH}` | High threshold for output load (%) | `80` |
| `{$OUTPUT.LOAD.MED}` | Medium threshold for output load (%) | `60` |
| `{$OUTPUT.VOLTAGE.HIGH.WARN}` | Warning threshold for high output voltage (V) | `260` |
| `{$OUTPUT.VOLTAGE.LOW.WARN}` | Warning threshold for low output voltage (V) | `200` |
| `{$BYPASS.VOLTAGE.HIGH.WARN}` | Warning threshold for high bypass voltage (V) | `260` |
| `{$BYPASS.VOLTAGE.LOW.WARN}` | Warning threshold for low bypass voltage (V) | `200` |
| `{$TEMP.CRIT}` | Critical threshold for temperature (°C) | `50` |
| `{$TEMP.WARN}` | Warning threshold for temperature (°C) | `40` |
| `{$ENV.TEMP.CRIT}` | Critical threshold for environment temperature (°C) | `35` |
| `{$ENV.TEMP.WARN}` | Warning threshold for environment temperature (°C) | `30` |
| `{$ENV.HUMIDITY.CRIT}` | Critical threshold for environment humidity (%) | `80` |
| `{$ENV.HUMIDITY.WARN}` | Warning threshold for environment humidity (%) | `70` |

### Items

| Name | Description | Type | Key |
|------|-------------|------|-----|
| UPS Manufacturer | The name of the UPS manufacturer. | SNMP agent | `dupsIdentManufacturer` |
| UPS Model | The model name of the UPS. | SNMP agent | `dupsIdentModel` |
| UPS Software Version | The software version of the UPS. | SNMP agent | `dupsIdentUPSSoftwareVersion` |
| Agent Software Version | The version of the SNMP agent software. | SNMP agent | `dupsIdentAgentSoftwareVersion` |
| UPS Name | The name of the UPS. | SNMP agent | `dupsIdentName` |
| Attached Devices | Information about devices attached to the UPS. | SNMP agent | `dupsAttachedDevices` |
| Rating Output Power (VA) | The rated output power of the UPS in Volt-Amperes. | SNMP agent | `dupsRatingOutputVA` |
| Rating Output Voltage | The rated output voltage of the UPS. | SNMP agent | `dupsRatingOutputVoltage` |
| Rating Output Frequency | The rated output frequency of the UPS. | SNMP agent | `dupsRatingOutputFrequency` |
| Rating Input Voltage | The rated input voltage of the UPS. | SNMP agent | `dupsRatingInputVoltage` |
| Rating Input Frequency | The rated input frequency of the UPS. | SNMP agent | `dupsRatingInputFrequency` |
| Rating Battery Voltage | The rated battery voltage of the UPS. | SNMP agent | `dupsRatingBatteryVoltage` |
| Low Transfer Voltage Upper Bound | The upper bound for low voltage transfer point. | SNMP agent | `dupsLowTransferVoltUpBound` |
| Low Transfer Voltage Lower Bound | The lower bound for low voltage transfer point. | SNMP agent | `dupsLowTransferVoltLowBound` |
| High Transfer Voltage Upper Bound | The upper bound for high voltage transfer point. | SNMP agent | `dupsHighTransferVoltUpBound` |
| High Transfer Voltage Lower Bound | The lower bound for high voltage transfer point. | SNMP agent | `dupsHighTransferVoltLowBound` |
| Config Buzzer Alarm State | The state of the buzzer alarm configuration. | SNMP agent | `dupsConfigBuzzerAlarm` |
| Config Buzzer State | The state of the buzzer configuration. | SNMP agent | `dupsConfigBuzzerState` |
| Config Sensitivity | The sensitivity level configuration. | SNMP agent | `dupsConfigSensitivity` |
| Config Low Voltage Transfer Point | The configured low voltage transfer point. | SNMP agent | `dupsConfigLowVoltageTransferPoint` |
| Config High Voltage Transfer Point | The configured high voltage transfer point. | SNMP agent | `dupsConfigHighVoltageTransferPoint` |
| Shutdown Type | The type of shutdown configured. | SNMP agent | `dupsShutdownType` |
| Auto Reboot Enabled | Whether auto reboot is enabled. | SNMP agent | `dupsAutoReboot` |
| Battery Charge Level | The estimated charge remaining on the UPS battery expressed in percentage of full charge. | SNMP agent | `dupsBatteryCapacity` |
| Battery Voltage | The current voltage of the UPS battery. | SNMP agent | `dupsBatteryVoltage` |
| Battery Current | The current flowing through the UPS battery. | SNMP agent | `dupsBatteryCurrent` |
| Battery Condition | The condition of the UPS battery. | SNMP agent | `dupsBatteryCondition` |
| Battery Status | The status of the UPS battery. | SNMP agent | `dupsBatteryStatus` |
| Battery Charge Status | The charging status of the UPS battery. | SNMP agent | `dupsBatteryCharge` |
| Seconds on Battery | The number of seconds the UPS has been on battery power. | SNMP agent | `dupsSecondsOnBattery` |
| Estimated Battery Runtime | The estimated remaining battery run time. | SNMP agent | `dupsBatteryEstimatedTime` |
| Internal Temperature | The internal temperature of the UPS. | SNMP agent | `dupsTemperature` |
| Output Power Source | The current source of power for the UPS output. | SNMP agent | `dupsOutputSource` |
| Output Frequency | The frequency of the UPS output. | SNMP agent | `dupsOutputFrequency` |
| Number of Output Lines | The number of output lines on the UPS. | SNMP agent | `dupsOutputNumLines` |
| Number of Input Lines | The number of input lines on the UPS. | SNMP agent | `dupsInputNumLines` |
| Number of Bypass Lines | The number of bypass lines on the UPS. | SNMP agent | `dupsBypassNumLines` |
| Scheduled Test Type | The type of scheduled test configured. | SNMP agent | `dupsTestType` |
| Last Test Results Summary | A summary of the results from the last UPS test. | SNMP agent | `dupsTestResultsSummary` |
| Environment Temperature | The temperature measured by the environmental sensor. | SNMP agent | `dupsEnvTemperature` |
| Environment Humidity | The humidity measured by the environmental sensor. | SNMP agent | `dupsEnvHumidity` |
| ICMP ping | Checks if the host is accessible using ICMP ping. | Simple check | `icmpping` |

#### Discovered Items (LLD)

| Name | Description | Type | Key |
|------|-------------|------|-----|
| Output Voltage (Line {#SNMPINDEX}) | The output voltage on a specific line. | SNMP agent | `dupsOutputVoltage.[{#SNMPINDEX}]` |
| Output Current (Line {#SNMPINDEX}) | The output current on a specific line. | SNMP agent | `dupsOutputCurrent.[{#SNMPINDEX}]` |
| Output Power (Line {#SNMPINDEX}) | The output power on a specific line. | SNMP agent | `dupsOutputPower.[{#SNMPINDEX}]` |
| Output Load (Line {#SNMPINDEX}) | The output load percentage on a specific line. | SNMP agent | `dupsOutputLoad.[{#SNMPINDEX}]` |
| Input Voltage (Line {#SNMPINDEX}) | The input voltage on a specific line. | SNMP agent | `dupsInputVoltage.[{#SNMPINDEX}]` |
| Input Current (Line {#SNMPINDEX}) | The input current on a specific line. | SNMP agent | `dupsInputCurrent.[{#SNMPINDEX}]` |
| Bypass Voltage (Line {#SNMPINDEX}) | The bypass voltage on a specific line. | SNMP agent | `dupsBypassVoltage.[{#SNMPINDEX}]` |
| Bypass Current (Line {#SNMPINDEX}) | The bypass current on a specific line. | SNMP agent | `dupsBypassCurrent.[{#SNMPINDEX}]` |

### Triggers

| Name | Description | Expression | Priority |
|------|-------------|------------|----------|
| {HOST.NAME}: Battery charge < {$BATTERY.CHARGE.WARN}% | Triggers if the battery charge drops below the warning threshold. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsBatteryCapacity)<{$BATTERY.CHARGE.WARN}` | Warning |
| {HOST.NAME}: Battery charge < {$BATTERY.CHARGE.CRIT}% | Triggers if the battery charge drops below the critical threshold. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsBatteryCapacity)<{$BATTERY.CHARGE.CRIT}` | High |
| {HOST.NAME}: Battery condition is bad | Triggers if the battery condition is reported as bad. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsBatteryCondition)=3` | High |
| {HOST.NAME}: Battery status is low | Triggers if the battery status is reported as low. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsBatteryStatus)=3` | High |
| {HOST.NAME}: Internal temperature > {$TEMP.WARN}°C | Triggers if the internal temperature exceeds the warning threshold. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsTemperature)>{$TEMP.WARN}` | Warning |
| {HOST.NAME}: Internal temperature > {$TEMP.CRIT}°C | Triggers if the internal temperature exceeds the critical threshold. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsTemperature)>{$TEMP.CRIT}` | High |
| {HOST.NAME}: Output power source changed | Triggers if the output power source changes. | `(last(/Template Delta UPS GES-103R212035 SNMP/dupsOutputSource,#1)<>last(/Template Delta UPS GES-103R212035 SNMP/dupsOutputSource,#2))=1` | Information |
| {HOST.NAME}: Last UPS test resulted in error | Triggers if the last UPS test resulted in an error. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsTestResultsSummary)=3` | Warning |
| {HOST.NAME}: Environment temperature > {$ENV.TEMP.WARN}°C | Triggers if the environment temperature exceeds the warning threshold. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsEnvTemperature)>{$ENV.TEMP.WARN}` | Warning |
| {HOST.NAME}: Environment temperature > {$ENV.TEMP.CRIT}°C | Triggers if the environment temperature exceeds the critical threshold. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsEnvTemperature)>{$ENV.TEMP.CRIT}` | High |
| {HOST.NAME}: Environment humidity > {$ENV.HUMIDITY.WARN}% | Triggers if the environment humidity exceeds the warning threshold. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsEnvHumidity)>{$ENV.HUMIDITY.WARN}` | Warning |
| {HOST.NAME}: Environment humidity > {$ENV.HUMIDITY.CRIT}% | Triggers if the environment humidity exceeds the critical threshold. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsEnvHumidity)>{$ENV.HUMIDITY.CRIT}` | High |
| {HOST.NAME} is unavailable by ICMP | Triggers if the host is unavailable by ICMP ping. | `max(/Template Delta UPS GES-103R212035 SNMP/icmpping,#3)=0` | Average |

#### Discovered Triggers (LLD)

| Name | Description | Expression | Priority |
|------|-------------|------------|----------|
| {HOST.NAME}: Output voltage (Line {#SNMPINDEX}) is too low | Triggers if the output voltage on a specific line is too low. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsOutputVoltage.[{#SNMPINDEX}])<{$OUTPUT.VOLTAGE.LOW.WARN}` | Warning |
| {HOST.NAME}: Output voltage (Line {#SNMPINDEX}) is too high | Triggers if the output voltage on a specific line is too high. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsOutputVoltage.[{#SNMPINDEX}])>{$OUTPUT.VOLTAGE.HIGH.WARN}` | Warning |
| {HOST.NAME}: Line {#SNMPINDEX} load > {$OUTPUT.LOAD.MED}% | Triggers if the load on a specific line exceeds the medium threshold. | `avg(/Template Delta UPS GES-103R212035 SNMP/dupsOutputLoad.[{#SNMPINDEX}],5m)>{$OUTPUT.LOAD.MED}` | Warning |
| {HOST.NAME}: Line {#SNMPINDEX} load > {$OUTPUT.LOAD.HIGH}% | Triggers if the load on a specific line exceeds the high threshold. | `avg(/Template Delta UPS GES-103R212035 SNMP/dupsOutputLoad.[{#SNMPINDEX}],5m)>{$OUTPUT.LOAD.HIGH}` | High |
| {HOST.NAME}: Input voltage (Line {#SNMPINDEX}) is too low | Triggers if the input voltage on a specific line is too low. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsInputVoltage.[{#SNMPINDEX}])<{$INPUT.VOLTAGE.LOW.WARN}` | Warning |
| {HOST.NAME}: Input voltage (Line {#SNMPINDEX}) is too high | Triggers if the input voltage on a specific line is too high. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsInputVoltage.[{#SNMPINDEX}])>{$INPUT.VOLTAGE.HIGH.WARN}` | Warning |
| {HOST.NAME}: Bypass voltage (Line {#SNMPINDEX}) is too low | Triggers if the bypass voltage on a specific line is too low. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsBypassVoltage.[{#SNMPINDEX}])<{$BYPASS.VOLTAGE.LOW.WARN}` | Warning |
| {HOST.NAME}: Bypass voltage (Line {#SNMPINDEX}) is too high | Triggers if the bypass voltage on a specific line is too high. | `last(/Template Delta UPS GES-103R212035 SNMP/dupsBypassVoltage.[{#SNMPINDEX}])>{$BYPASS.VOLTAGE.HIGH.WARN}` | Warning |

## Setup

1.  Ensure your Delta UPS GES-103R212035 has SNMP enabled and is accessible from your Zabbix server/proxy.
2.  Import the `delta_ups_zbx7_comprehensive.json` template file into Zabbix.
3.  Link the imported template to the host representing your UPS.
4.  Configure the required SNMP community string (for v1/v2c) or user credentials (for v3) in the host's SNMP interface settings.
5.  Adjust the template macros (e.g., thresholds) if needed.

## MIBs Used

- DeltaUPS-MIB
- UPS-MIB (if implemented by device)
- SNMPv2-MIB
- RFC1213-MIB
## Template Version

1.0

## Zabbix Compatibility

7.0+


## Manual

[https://www.zabbix.com/documentation/current/manual/config/items/itemtypes/snmp](https://www.zabbix.com/documentation/current/manual/config/items/itemtypes/snmp)

## No Warranty

This template is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the template or the use or other dealings in the template.
