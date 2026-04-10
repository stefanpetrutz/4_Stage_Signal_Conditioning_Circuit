# 4_Stage_Signal_Conditioning_Circuit
I designed and simulated a 4-Stage Signal Conditioning Analog Circuit in LTspice featuring: Instrumentation Amplifier, Band-Pass Filter, Programmable Gain Amplifier (PGA), Full Wave Rectifier. The project was realised in LTspice.

## Stage 1: Instrumentation Amplifier ##

<img width="885" height="451" alt="image" src="https://github.com/user-attachments/assets/205d877b-e1fa-4a9f-a894-a68b3b13416e" />

Vout = (VA – VB) * (1 + 2*R1/RG) * R3/R2 + Vref 

Ad = (1 + 2*R1/RG) * R3/R2 = 1.5

1 + 2*R1/RG = (R2/R3) * 1.5

Aleg R3 = RG = 1 kΩ

1 + 2*R1 = R2 * 1.5 => R2 = (1 + 2*R1)/1.5

R1 = 1 kΩ => R2 = 2 kΩ

## Stage 2: Filter ##

<img width="945" height="465" alt="image" src="https://github.com/user-attachments/assets/ccaf8612-cad2-4b1c-8cf2-584b7bb2c982" />

|H0| = 2

Rin,min = 750 Ω

Q = 1

BW = 7 kHz

H(s) = Vout/Vin = H0 * (w0*s/Q)/(s^2+(w0/Q)*s+〖w0〗^2 )

C1 = C2 = C

Q = 1/2 *√(R2/R1)       R1 = 750 Ω

|H0| = 2Q^2   =>  1 = 1/4 * R2/R1 => R2 = 4R1 => R2 = 3 kΩ

w0 = 2* π*f0

f0 = BW*Q = 7 kHz

w0=  1/(√(R1*R2)*C)  = 1/1500C = 2*π * 7000 => C = 15 nF


## Stage 3: PGA ##

<img width="720" height="1013" alt="image" src="https://github.com/user-attachments/assets/76fe4d7a-285b-4305-a136-ace68c9b2ea5" />

A = 1 + Rf/RG

A1 = 1 + RF1/RG = 2.5 => RF1 = 1.5*RG

A2 = 1 + RF2/RG = 3.2 => RF2 = 2.2*RG

A3 = 1 + RF3/RG = 4 => RF3 = 3*RG

A4 = 1 + RF4/RG = 5 => RF4 = 4RG

RG = 1 kΩ

RF1 = 1.5 kΩ

RF2 = 2.2 kΩ

RF3 = 3 kΩ

RF4 = 4 kΩ

## Stage 4: Full Wave Rectifier ##

<img width="945" height="502" alt="image" src="https://github.com/user-attachments/assets/369342fb-7f38-4d07-b1b4-035610caa9e2" />


Vout = Vin, Vin > 0

Vout = (R1*R3-R2*R4)/(R1*R3)*Vin, Vin < 0

(R1*R3-R2*R4)/(R1*R3) = 1 => R2*R4/R1*R3 = 2 => R2*R4 = 2*R1*R3

R1 = R2 = R4 = R (aleg R = 1 kΩ) => R3 = R/2 => R3 = 500 Ω

## Simulations performed ##

* DCOP
* AC
* CMRR
* PSRR
* Slew Rate
* THD (Total Harmonic Distortion)
 
