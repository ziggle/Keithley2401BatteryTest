<p align="center">
  <img src="Images/Keithley2401a.png" width="500"/>
</p>
<br>
<h3 align=center>Battery State-of-Charge Measurement Using the Keithley Meter </h2>
<h4 align=center>This repo contains my work on interfacing to the Keithley 2401a sourcementer for battery SOC measurements.</h3>
<br>

#  SOC Measurement with the Keithley 2401A.

# Abstract
This repo contains an example of a battery characterization test using the Keithley 2401A 4-wire sourcemeter. It also contains the simplest example I could come up with that illustrates:

* Current Drive, Voltage Measurement
* Voltage Drive, Current Measurement

Note that battery measurements are quite straightforward. Unfortunately, hardware measurements are sometimes complicated by input issues. For example, some hardware expects certain voltage levels or it will not start. The Keithley must apply that start voltage before it moves to the the desired test voltage.

# Background

## Definitions

A battery discharge cycle is defined by one parameter:

<dl>
<dt><i>I<sub>Load</sub></i></dl>
<dd>The constant current applied during the discharge phase. In practice, battery current varies widely. For test purposes, we only apply a constant load. In general, the constant load is set to the mean of the actual load current applied in the application.</dd>
</dl>
<br>
A battery charge cycle is defined by the following parameters:
<dl>
<dt><i>I<sub>CC</sub></i></dl>
<dd>The constant current applied during the constant current phase of charging.</dd>
<dt><i>V<sub>CV</sub></i></dl>
<dd>This is maximum voltage applied to the battery during the charging process. This voltage controls the termination of the constant current phase and sets the charge voltage during the constant voltage phase.</dd>
<dt><i>I<sub>TERM</sub></i></dt>
<dd>This is the current at which the constant current phase terminates.</dd>
<dt><i>V<sub>TERM</sub></i></dt>
<dd>The voltage at which battery discharge ceases.</dd>
</dl>
<br>

## Battery Basics

### Discharge Cycle

A battery's load profile in actual use is highly variable. For battery characterization purposes, we apply a constant voltage that is usually set to the mean current the battery is expected to deliver. The discharge cycle terminates when the battery voltage drops to <i>V<sub>TERM</sub></i>.

### Charge Cycle

A charge cycle is composed of two parts:

* Constant Current<br>For battery voltages less than <i>V<sub>CV</sub></i>, the battery is charged using a constant current. This phase terminates when the battery attains the specified threshold.
* Constant Voltage<br>When the battery reaches <i>V<sub>CV</sub></i>, the charge algorithm applies a constant voltage. This phase terminates when the battery charge current falls below <i>I<sub>TERM</sub></i>.

# Analysis

## Data Pipeline

## ETL

## SOC Generation

## Results
