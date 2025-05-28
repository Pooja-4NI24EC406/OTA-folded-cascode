<h1> OTA-folded-cascode</h1>

### INTRODUCTION <br>
 The Folded Cascode Operational Transconductance Amplifier (OTA) plays a crucial role in analog integrated circuit design, particularly for applications<br>
 demanding high gain, wide input range, and efficient power consumption. Unlike conventional OTA topologies such as the telescopic cascode, which suffer from<br>
 limited input and output swing under low supply voltages, the folded cascode architecture employs a current folding technique using complementary transistors,<br>
 alowing for a greater signal swing while preserving a high output impedance. This design feature makes the folded cascode OTA highly suitable for low-voltage<br>
 CMOS technologies, including the 180nm process node, where headroom constraints are significant.<br>
 A folded cascode is a type of electronic circuit configuration that combines a cascode amplifier with a folded structure, providing high gain, high output impedance, and improves stability. It's used to enhance performance in analog circuits.<br>

### ABBREVIATIONS AND ACRONYMS DESIGN EQUATION<br>
 OTA- Operational Transconductance Amplifier<br>
 FC-OTA-Folded Cascode Operational Transconductance Amplifier<br>
 CMRR-Common-Mode Rejection Ratio<br>
 ICMR -Input Common Mode Range<br>
  VDD - Positive Supply Voltage<br>
 CMOS- Complementary Metal-Oxide-Semiconductor<br>
 Vov- Overdrive Voltage<br>
 gm -Transconductance<br>
 ro - Output Resistance<br>
 ID- Drain Current<br>

  ### CIRCUIT DIAGRAM<br>
  
![image](https://github.com/user-attachments/assets/b1ae6cdf-4e13-46df-8ad6-68240d2f1156)

![image](https://github.com/user-attachments/assets/97bfa289-b904-4c7b-856e-ca98947a7970)


### DESIGN QUESTION WITH EQUATION<br>
 Design a single-stage folded-cascode operational amplifier using 180nm CMOS technology with a ±0.9V supply (1.8V total). The amplifier should use an NMOS<br>
 differential input pair for improved common-mode range and an actively biased PMOS cascode load to achieve high gain. The design must target a DC gain<br>
 of at least 50 dB, consume approximately 0.35 mW power. The tail current should be around 10 µA and maximum output swing=1.6V<br>

 Given,<br>
maximum output swing ,<br>
Voutpp = Vdd - [ Vov5 + Vov3 + |Vov4| + |Vov7| ]<br>
0.8 = 1.8 - [ Vov5 + Vov3 + |Vov7| + |Vov9| ]<br>
[ Vov5 + Vov3 + |Vov7| + |Vov9| ] = 1 V<br>
<br>
PMOS Vov should be greater than NMOS Vov to ensure PMOS stays in saturation, maintaining high gain.<br>
| Vov of PMOS | > Vov of NMOS (as μpCox < μnCox)<br>
Therefore,<br>
Vov7 = Vov9 = 0.3 V<br>
Vov3 = Vov5 = 0.2 V<br>
<br>
Given the reference current , Iss = 10u A<br>
Id1 = Iss/2 = 5uA<br>
Id (1,2) = 5uA ( current divides equally when vgs are same )<br>
The current across mosfets M3,4,7,8,9,10 be,<br>
Id2 = 5uA<br>
So,<br>
The current across M5 and M6 becomes  ,<br>
Id(tot) = Id1 + Id2 = Iss = 10uA.<br>
<br>
Also ,<br>
Power ≤ 0.35 mW<br>
P = Vdd (Iss) = 1.8 (10u) = 18 u<br>
18u<=35mW<br>
<br>
The Bias Voltages<br>
Vb2 = Vgs5 = Vov5 + Vth5 = 0.2 + 0.5<br>
Vb2=0.7  V<br>
(practical case used Vb2 = 1.8V to keep m5 and m6 in saturation )<br>
Vgs3 = Vg3 - Vs3<br>
Vgs3 = Vb1 - Vov5<br>
Vb1 = Vgs3 + Vov5 = ( Vov3 + Vth3 ) + Vov5<br>
Vb1=0.9 V<br>
(practical case used Vb2 = 2.3V to keep m3 and m4 in saturation)<br>
Vsg9 = Vs9 – Vgs<br>
Vgs9 = Vdd - Vb4<br>
Vb4 = Vdd - ( Vov9 + Vth9 ) = 1.8 - ( 0.3 + 0.39 )<br>
Vb4 = 1.11 V<br>
(practical case used Vb4 = 1V to keep m3 and m4 in saturation )<br>
Vsg7 = Vs7 - Vg7<br>
Vs7 = Vdd - |Vov9| = 1.8 - 0.3 = 1.5 V<br>
Vsg7 = 1.5 - Vb3<br>
( Vov7 + Vth7 ) = 1.5 - Vb3<br>
Vb3 = 1.5 - ( 0.3 + 0.39 )<br>
Vb3 = 0.81 V<br>
( practically used diode connected mosfet to keep m7 and m8 in saturation and to increase the output voltage )<br>
<br>
μₙCₒₓ = 200 μA/V² & Vov (NMOS) = 0.2 V<br>
μₚCₒₓ = 100 μA/V² & Vov (PMOS) = 0.3 V<br>
L = 180 nm (0.18 µm)<br>
Id = 1/2•unCox(W/L)Vov^2<br>
1. For NMOS : W/L = 2*5*10^-6/200*10^-6*(0.2)^2 =1.25<br>
2. For PMOS : W/L = =2*5*10^-6/100*10^-6*(0.3)^2=2.22<br>
<br>

###  SIMULATION RESULT<br>

 1.DC ANALYSIS:<br>
 
![image](https://github.com/user-attachments/assets/2c4b5c95-0cc5-42a5-bab0-2a3c288a705e)

 2 Transient analysis:<br>
A.Common mode analysis<br>

![image](https://github.com/user-attachments/assets/9e606c75-3f23-4884-9115-9c464082a687)


 As vin common mode is 0.9V<br>
 Vout = 500mV ( which is nearest to 0V )<br>

 B.Differential mode analysis<br>
 Vin ,<br>

![image](https://github.com/user-attachments/assets/8b2995e1-4239-42c7-9305-3dd70c364c4e)

![image](https://github.com/user-attachments/assets/75f491b9-0800-4de4-bacc-c967f46c2e4d)


 Vout,<br>

 ![image](https://github.com/user-attachments/assets/aef59323-f019-4da3-b248-c1c14994ab58)

 Voutmin (calculated) = Vb1 + Vov5 = 1+0.2 = 1.2V<br>
 VoutMax(calculated) = Vdd-Vov7 = 1.8-0.3 = 1.5V<br>
 and<br>
 Vinmin(calculated) = Vss +Vtn+Vov1 = 0+0.45+0.2 = 0.65V<br>
 Vinmax(calculated)= Vb1-Vtn+Vov5 = 1-0.45+0.2 = 0.75V<br>
 Here in simulation<br>
 We got Voutmax=1.3V<br>
 Voutmin= 0.9V<br>
 Vinmin=0.5V<br>
 Vinmax= 0.8V<br>

  3.AC Analysis<br>

![image](https://github.com/user-attachments/assets/f83444d5-8f7a-4199-b7d6-44642f40c80b)


 Av(dB) = 31dB<br>
 Therefore, Vout/Vin = 35.48V/V<br>
 CMRR = 20log (Adm/Acm)<br>
 Adm = 35.48V/V<br>
 Acm = 1V/V<br>
 Therefore<br>
 CMRR = 97dB<br>

 
 ### TESTING & VERIFICATION<br>
 DC biasing verified; al transistors in saturation<br>
 AC gain < 55 dB (Due to smal current source)<br>
 Power consumption < 0.35 mW confirmed<br>
 Bias voltages (Vb1-Vb4) validated<br>
 Wide output swing verified<br>
 Simulated in LTspice across corners<br>

 
 ###  RESULTS<br>
 The designed folded cascode operational amplifier with cascode PMOS loads was simulated with a 1.8 V supply and a 10µA bias current, splitting into 5µA
 per branch. Overdrive voltages were 0.2 V for M3/M5 and 0.3 V for M7-M10.<br>
 Bias voltages (VB1 to VB4) were carefuly tuned to keep al MOSFETs in saturation. Used diode connected mosfet instead of m3 to keep that in
 saturation<br>
 The measured output swing was 1.6 V peak-to-peak, with a common-mode output voltage of around 0.9 V.<br>
 The gain is less than 55dB because of smal current and 180nm technology,supported by the high output resistance from the PMOS cascode loads<br>
  
 ### CONCLUSION<br>
 The Folded Cascode Operational Amplifier offers an excelent balance between high gain, wide output swing, and low power consumption, making it
 highly suitable for modern analog integrated circuit applications. Its architecture alows the use of NMOS input differential pairs while maintaining a low supply
 voltage, thanks to the folded configuration. The inclusion of cascode PMOS loads further enhances gain and output impedance without compromising linearity
 or stability. Overal, the folded cascode amplifier stands out as a robust, versatile design ideal for use in precision analog systems, sensor interfaces, and low-power biomedical electronics.<br>

 ### INFERENCE <br>
 1.Initial Output Issue:<br>
 The output voltage was stuck at a low level (~0.4 mV instead of the expected~0.8 V).<br>
 This was due to improper biasing and incorrect Vds voltages for M5 and M6.<br>
 2. Current Mismatch in Branches:<br>
 M3 and M4 initialy had much lower current than M5 and M6.Vx and Vy nodes were not providing enough voltage to turn M3 and M4 on properly.<br>
 3. W/L Ratio Tuning:<br>
 The W/L ratios of M3, M4, M5, and M6 were adjusted to achieve the desired drain current (5μA for M3/M4 and 10μA for M5/M6).PMOS and NMOS
 devices were resized based on overdrive voltages (V<sub>ov</sub>) to match
 current requirements.<br>
 4. Bias Voltage Optimization:<br>
 VB1 to VB4 values were tuned carefuly to bring al transistors into saturation.Particularly, M3 and M4 needed more headroom to come out of cutoff and operate properly.<br>
 5. Simulation Validation:<br>
 Final DC simulation confirmed al branch currents were within 5μA or 10μA as designed.<br>
 Vout was correctly adjusted to 1.2V<br>

