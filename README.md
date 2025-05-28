### OTA-folded-cascode
<h2>INTRODUCTION</h2>
 The Folded Cascode Operational Transconductance Amplifier (OTA) plays a
 crucial role in analog integrated circuit design, particularly for applications
 demanding high gain, wide input range, and efficient power consumption. Unlike
 conventional OTA topologies such as the telescopic cascode, which suffer from
 limited input and output swing under low supply voltages, the folded cascode
 architecture employs a current folding technique using complementary transistors,
 alowing for a greater signal swing while preserving a high output impedance. This
 design feature makes the folded cascode OTA highly suitable for low-voltage
 CMOS technologies, including the 180nm process node, where headroom
 constraints are significant.
 A folded cascode is a type of electronic circuit configuration that combines a cascode amplifier with a folded structure, providing high gain, high output impedance, and improved stability. It's used to enhance performance in analog circuits.<br>

<h2>ABBREVIATIONS AND ACRONYMS DESIGN EQUATION</h2>
 OTA- Operational Transconductance Amplifier<br>
 FC-OTA-Folded Cascode Operational Transconductance Amplifier<br>
 CMRR-Common-Mode Rejection Ratio
 ICMR -Input Common Mode Range
  VDD - Positive Supply Voltage
 CMOS- Complementary Metal-Oxide-Semiconductor
 Vov- Overdrive Voltage
 gm -Transconductance
 ro - Output Resistance
 ID- Drain Current

  ### CIRCUIT DIAGRAM<br>
  
![image](https://github.com/user-attachments/assets/b1ae6cdf-4e13-46df-8ad6-68240d2f1156)


### DESIGN QUESTION WITH EQUATION<br>
 Design a single-stage folded-cascode operational amplifier using 180nm CMOS
 technology with a ±0.9V supply (1.8V total). The amplifier should use an NMOS
 differential input pair for improved common-mode range and an actively biased
 PMOS cascode load to achieve high gain. The design must target a DC gain
 of at least 50 dB, consume approximately 0.35 mW power. The tail current
 should be around 10 µA and maximum output swing=1.6V

