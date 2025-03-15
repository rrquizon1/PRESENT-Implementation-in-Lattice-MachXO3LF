This is an implementation of PRESENT Encryption algorith in Verilog using Lattice MachXO3LF Starter Kit.

The PRESENT algorithm is an ultra-lightweight block cipher designed for resource-constrained environments, such as RFID tags, smart cards, and embedded systems. 
It was introduced in 2007 by researchers from Orange Labs, Ruhr University Bochum, and the Technical University of Denmark.

You can check out the original PRESENT Paper here: https://www.iacr.org/archive/ches2007/47270450/47270450.pdf

This implementation simplifies the input for demonstration purposes. This design has the following block diagram
![image](https://github.com/user-attachments/assets/1340730d-87b8-4622-a5df-188544604d8c)

This design can be modified to have 64 bit plain text input and 80 bit cipher text input. This design was simplified for hardware demonstration with MachXO3LF starter kit.

The plain text and keys used in this example are the test vectors indicated in the original paper:
![image](https://github.com/user-attachments/assets/6b5a1c62-0bcd-4c93-908d-0bb8c179c851)
 
See RTL simulation results below:
![image](https://github.com/user-attachments/assets/9eeb12f3-697e-4436-9aae-04e03f5c139a)
![image](https://github.com/user-attachments/assets/aac72a90-7a97-4bd5-a3d4-fb3d4f72cf68)
![image](https://github.com/user-attachments/assets/96c5f2f5-19a5-4bb9-82bc-205d5cbc6df5)
![image](https://github.com/user-attachments/assets/f6c50c80-e355-47d1-a2b5-8ff52c56ee43)


To verify in hardware, we used Lattice's built in Reveal Debug core. With Reveal we will be able to monitor multiple signals using some triggers.





