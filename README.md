# Lab 3 Write Up
Valeria Rodriguez

Ziyad Gawish 

EE 157

Lab Report

# Lab 3: Inductor Design and Characterization Lab

## Introduction
In this lab we will learn how to design an inductor to meet given performance specifications. We will select the core, gauge of the wire, and air gap in 
accordance with the given specifications. 

## Learning Objectives 
- Fabricate the inductor designed in our prelab and verify that it meets our design specifications
- Measure the DC resistance and inductance of our inductor at various operating points

## Background 
In this the lab, we fabricated and designed an indcutor that we verified met the design specifications which were as followed:
- 200 μH inductance ±5 percent
- 2 A dc current
- Current to saturate at 100 degrees C: 3 A (minimum)
- 0.40 W maximum power dissipation
- Operating at 10 kHz

We conducted tests to measure the DC resistance and inductance of our inductor at various operating points to verify if it met the specifications.

## Materials 

- 495-5432-ND (N30 material)
- 495-5372-ND Bobbin 
- Magnet wire (#20 AWG copper wire)
- Gapping material (Kapton)
- Analog Discovery 
- Impedance Analyzer for Analog Discovery
- Auxiliary inductor (5 mH)
- USB isolator module
- Thermal camera

## Fabrication/Methods

We selected the 495-5432-ND Core and corresponding 495-5372-ND Bobbin from the available options. An ungapped 495-5432-ND Core with N30 material uses something called relative core loss so we will estimate our constant to be .8kW/m^3 when operating at10kHz and temperature is 100 degrees C.

Given these values we then found the volume of the gap to be using the following formula: Vg = µ*L*(Imax)2/( Bmax)2. The cross-sectional area, A, is given by the data sheet: A = 60mm^2 and the gap length.

We got our desired gap length by dividing the desired Vg by our specified cross sectional area.
Then we calculated the number of turns necessary, with N = sqrt(Llg/u_oA_c) and winded the inductor while noting our packing factor.

In summary, we used a 495-5432-ND core, N30 material, bobbin 495-5372-ND and a #20 AWG wire in the fabrication of the wire.

<img width="493" alt="Screen Shot 2022-06-03 at 11 33 07 PM" src="https://user-images.githubusercontent.com/71746051/172269284-1c44f64d-1bad-4570-949b-3aaedc530cd3.png">

<img width="867" alt="Screen Shot 2022-06-03 at 11 53 46 PM" src="https://user-images.githubusercontent.com/71746051/172269290-0c384048-2833-49e3-a93b-6fe8f184c244.png">


## Characterization

### 1. DC Resistance

The DC resistance was measured with respect to frequency using the Impedance Analyzer. At 0 Hz, the DC resistance was 0.03 ohms. But, at higher frequencies, the current traveled through a smaller cross-sectional area of the wire and the impedance increased as the frequency increased. This phenomenon is known as the skin effect and happens as the current flows closer to the surface of the wire.

### 2. Inductance 

Record plots that illustrate how inductance varies with frequency and plots that illustrate how inductance varies with frequency and DC current.

![01A_L](https://user-images.githubusercontent.com/71746051/172272087-8ddd5102-126f-4dfb-bee4-509ffbcc7c86.png)

Inductance increased with frequency. This happens because the current flowing through the coils induces a magnetic field which causes a back emf voltage opposing the current flow. This relationship is given by the equation V = L di/dt. The higher the frequency, the higher the rate of change of the current,the higher the back emf voltage, leading to a higher inductance.

* Inductance at .5A

![50A_L](https://user-images.githubusercontent.com/71746051/172271455-27cc19ca-eac1-4cf1-818d-cae85059ec05.png)

* Inductance at 1A

![100A_L](https://user-images.githubusercontent.com/71746051/172271475-f061d105-257e-421a-8159-3eb5a28c8bc6.png)

* Inductance at 1.5A

![150A_L](https://user-images.githubusercontent.com/71746051/172271487-309f1658-833e-45b2-b93e-a2ff8d8c072b.png)

* Inductance at 2A

![200A_L](https://user-images.githubusercontent.com/71746051/172271497-547fb163-972c-4c58-b800-cc53f20fbf78.png)

* Inductance at 2.5A

![250A_L](https://user-images.githubusercontent.com/71746051/172271519-7f91993a-b7f7-4665-a183-584778df8cb4.png)

* Inductance at 3A

![300A_L](https://user-images.githubusercontent.com/71746051/172271542-f375f077-8ed5-41de-8863-05dbdade3523.png)


### 3. Test Setup using Auxiliary Inductor 

* Record plots that illustrate inductance at various currents at 10kHz.

![EE157_Lab3_(AvsT)Plot-1](https://user-images.githubusercontent.com/71746051/172271075-6505f893-3671-4e87-a911-233d4641c9a6.png)

As the current approaches the saturation point, the inductance decreases exponentially, as expected.

* Record plot showing how temperature changes as more current is applied to the inductor. 

![EE157_Lab3_(AvsT)Plot-1](https://user-images.githubusercontent.com/71746051/172271066-0c57d944-11ed-406c-a52b-1be51dac4305.png)

As expected, the temperature increased as the current increased. Although the overall impedance decreases as current increases, referencing the power equation of P = I^2 * R, the power dissipated increases as current increases. The power is dissipated as heat, leading to an increase in temperature.

## Analysis Questions

### 1. From your prelab design, estimate your core and winding losses when your inductor is subjected to a sinusoidal 1 A AC current waveform with a 2 A DC component. Is your estimate supported by measurements that you recorded in lab? (Note you will not explicitly do this measurement, but rather infer losses from DC resistance and your temperature measurements.)

The winding losses are given by the equation P = I_rms^2 * R_DC. This means that I_rms = 2 A + 1 A / sqrt(2). Our measurements demonstrated that the resistance increases as frequency increases. Therefore, we could also expect winding losses to increase as frequency increases. From our temperature measurements, there is an average increase of about 0.92 °C per amp increase in current. For a RMS voltage of 2.707 A, an increase of 1 A would cause the power to increase by 0.213 W. Since copper has a mass of 3.94 g/m and a heat capacity of 0.395 J/g°C, in order to raise our wire by 0.92 degrees, we would need 0.3634 J of energy. If we estimate that the change in temperature per amp takes about 3 seconds, the rate would be 0.121 W which is about 52.4% of the power dissipated from just increasing the current alone. This is reasonable given the <59% given in the datasheet.

    {P_{core} = K_1V_e}#gh-light-mode-only">
    P_{core} = K_1V_e}#gh-dark-mode-only">
    So our core loss is  {P_{core} = (.80kW/m^3)(4E-6) = .0032W}#gh-light-mode-only">
   P_{core} = (.80kW/m^3)(4E-6) = .0032W

 The R_DC = 0.0332 ohms and the P_winding is estimated to be about 0.2 W. This was actually supported by our measurements. 
 
    <img src="https://render.githubusercontent.com/render/math?math={P_{winding} = I^2R}#gh-light-mode-only">
    <img src="https://render.githubusercontent.com/render/math?math={\color{white}P_{winding} = I^2R}#gh-dark-mode-only">
    So our core loss is  P_{winding} = (2 + 1 / \sqrt(2))^{2}.3 = 2.2W}#gh-light-mode-only">
    <img src="https://render.githubusercontent.com/render/math?math={\color{white}P_{winding} = (2 + 1 / \sqrt(2))^{2}.3 = 2.2W}#gh-dark-mode-only">
    This means our overall loss was 2.2032.

### 2. Does your measured inductor meet the specification? If not, why not? And what steps could you take to redesign your inductor to meet the specification? 

Our inductor had a measured inductance of about 200 μH which was at the exact specification of 200 μH +/- 5%.  This could be due to manufacturing error with the air gap, but at first it didn't. We tackled this by changing the number of turns given by the equation N = sqrt(L * lg * ke / u_o * Ac). It turns out, we would have to increase the number of turns to compensate for the air gap error. After it matched the specifications for inductance and saturation limits but not power dissipation. Another redesign method we could tru is to use less resistive wire so that we can lower the losses in the windings.

### 3. The “air gap” used is actually a Kapton or paper gap. The Kapton/paper is non-magnetic, and behaves the same as a true air gap. What would happen if aluminum was used for the gapping material?

The inductance will most likely decrease because aluminum is a good conductor and as result, eddy currents will form on the metal due the time varying magnetic fields. This will create their own magnetic field which will oppose the external one. The permeability of aluminum is aluminum = 1.256665 * 10^−6 H/m which is similar to μ0. Our values would only change by a little if at all. 
