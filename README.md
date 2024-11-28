# Smallest-220V-to-5V-Supply-for-IOT-applications
The requirement of stable DC power supplies in the IOT applications and in electronics designed products is very versatile.
See the full details from here:

The requirement of stable DC power supplies in the IOT applications and in electronics designed products is very versatile. Most of the circuits working at higher voltage say 220v either need a logic converter or linear step down units to lower down the voltage. But in the application where area and size matters a lot, we can not use this approach. On the other hand there are some transformer less supplies that are not that stable and can not produce required current for these applications. The ripples in power supplies and high voltage spikes can damage the overall product if any other options are taken into consideration. To solve the problem I searched on the web and found a good solution which is used in a lot of applications related to IOT smart things, and this is OB2222 high performance low cost power switching IC.

OB2222M is a high performance, high precision and low cost PWM Power switch for non-isolated buck and buck-boost applications. It combines a dedicated current mode PWM controller with a high voltage power. With a precise inner resistor divider, constant voltage regulation of 5.0V at universal AC input can be guaranteed.

It comes with low startup current and low operating current contribute to a reliable power on startup and low standby power consumption with OB2222M. Constant power operation is supported at over load application with OB2222M, which makes it suitable for small home appliance applications where instant large power consumption is required such as start-up of a fan.

FEATURES
Universal AC input range and 5.0V output voltage

Constant power mode operation at over load application

Current mode control  40kHz (typical) maximum switching frequency

Frequency-reduction and burst mode control for high efficiency

Frequency shuffling for EMI improvement

Power on soft-start

Output short-circuit protection

On-chip Over Temperature Protection (OTP)

VDD Over Voltage Protection (OVP)

VDD Under Voltage Lockout Protection (UVLO)

Circuit Diagram:

I got my reference schematics from the datasheet, the AC input is first rectified through a full bridge and given to the common pin of the IC which works as a reference to it. Then to soft start the IC from the DC rectified voltage 1M resistors are used which lower down the current hence form a voltage drop. Some rectification units are required at the DC output to remove the ripples in supply. An inductor, capacitor and fast diode at the output section form a close loop for proper switching of this buck boost convertor. A diode from the output fed up the feedback pin which helps the IC to maintain a constant voltage at higher loads also. With a max power rating of 1.5w this is capable of delivering current up to 200mA which is ideal for a lot of IOT related applications.

I modified the schematics according to the one given here, the half bridge rectifier at the input with some extra filtering unit (pie filter) and the other section, remains the same. The input capacitors are of 400V 2.2uf. One special thing here is that this power supply IC reacts very dramatically to the other value components and compatible components. So try to find and assemble it with the same components as given in the modified circuit.

Components Required:

Resistor fuse 2.2R/1W 

Diode 1N4007, M7, ES1J

Capacitor 223 Polyster film 400V

Capacitor 2.2uF /400V 

Capacitor 330uF /10V, 4.7uF /50V 

SMD Capacitor 1uF /25V

SMD Resistance 1R0 /1% /1206, 1K /5% /0603, 2M /5% /1206 

OB2222M SOP8 

Inductor 1mH, 350uH

PCB design:

I want to lower down the form factor in order to fit it inside some designed housing for electronics. So I go with a very standard size of 20*40mm. Output section is kept away from the input section to reduce the EMI and noise problems. All the high frequency sections and closed loops are kept short for the same noise reason. The SMD are kept at the bottom plane and all TH components at the top plane. Find your Gerber files and schematics on the PCBWAY hub.
Big thanks to PCBWay for sponsoring the PCBs for this project! Their high-quality manufacturing and quick turnaround made this build possible.

First time power on:

The board has a fuse (2.2 ohm) for protection but I always recommend using a second fuse for safety. Note the output voltage after supplying it with 220V AC. If the output voltage is lower check the output capacitor value and to put a bigger one, if still there are any problems check your fast switching diode.

Working:

The IC works fine with the components listed in the schematics, I tested out the power supply in the constant voltage and constant current mode. The maximum available current is 220mA at 5v which pushes the total wattage to 1.1W. There are some other documents from the onbright where the circuit diagram is incorrect, to go with my modified schematics is the final and working solution for that. Behind the scenes, PCBWay provided the custom PCBs that brought this idea to life—reliable, precise, and affordable! Find your Gerber files and schematics on the PCBWAY hub.
