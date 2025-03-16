This is an implementation of PRESENT Encryption algorith in Verilog using Lattice MachXO3LF Starter Kit. This project was designed using Lattice Diamond 3.13. 

The PRESENT algorithm is an ultra-lightweight block cipher designed for resource-constrained environments, such as RFID tags, smart cards, and embedded systems. 
It was introduced in 2007 by researchers from Orange Labs, Ruhr University Bochum, and the Technical University of Denmark.

You can check out the original PRESENT Paper here:[PRESENT Original Paper](https://www.iacr.org/archive/ches2007/47270450/47270450.pdf) 

This implementation simplifies the input for demonstration purposes. This design has the following block diagram
![image](https://github.com/user-attachments/assets/1340730d-87b8-4622-a5df-188544604d8c)

This design can be modified to have 64 bit plain text input and 80 bit cipher text input. This design was simplified for hardware demonstration with MachXO3LF starter kit:
![image](https://github.com/user-attachments/assets/88a7d594-34ff-43e8-9b47-d146b8b5321d)



The plain text and keys used in this example are the test vectors indicated in the original paper:
![image](https://github.com/user-attachments/assets/6b5a1c62-0bcd-4c93-908d-0bb8c179c851)
 
See RTL simulation results below:

![image](https://github.com/user-attachments/assets/9eeb12f3-697e-4436-9aae-04e03f5c139a)
![image](https://github.com/user-attachments/assets/aac72a90-7a97-4bd5-a3d4-fb3d4f72cf68)
![image](https://github.com/user-attachments/assets/96c5f2f5-19a5-4bb9-82bc-205d5cbc6df5)
![image](https://github.com/user-attachments/assets/f6c50c80-e355-47d1-a2b5-8ff52c56ee43)


To verify in hardware, we used Lattice's built in Reveal Debug core. With Reveal we will be able to monitor multiple signals using some triggers. We need to use the reveal inserter to check our plaintext, ciphertext, and key. We set this settings in the Trace Signal Setup tab.
![image](https://github.com/user-attachments/assets/9ac95dc3-4aaa-4d1c-8b37-7894730b30f1)
Then we set the trigger signal at Triger Signal Setup tab. For this example, I used done signal as my trigger. If it done becomes 1 it will trigger the capture:
![image](https://github.com/user-attachments/assets/cb62cc46-e6e0-43ae-ba27-db7b3412fdbf)

After setting the reveal inserter, make sure that .rvl file is included in the Debug Files:
![image](https://github.com/user-attachments/assets/f52debf2-6d75-436c-9bdf-c0f314cda89f)

For more instructions with Reveal Analyzer, you can check on this link:[Reveal Tutorial](https://www.youtube.com/watch?v=krbasfW3h5E) 

We will then use the Reveal Analyzer to monitor our data. See below for sample captures using the test vectors from the original paper:

![image](https://github.com/user-attachments/assets/a886429b-cbd3-4385-9fce-10aed4ed9c5b)
![image](https://github.com/user-attachments/assets/519d424a-b428-466e-9dd5-092d108f9e59)
![image](https://github.com/user-attachments/assets/f6c50a46-0e44-4352-ba88-e09b2a976b73)
![image](https://github.com/user-attachments/assets/6b8bf3d6-1213-48fb-9609-cbae8ae6d5e4)

Note: when you have finished debugging your design, you should remove the reveal core as it is intended to be used only for debugging purposes. 

Resource usage with reveal core:

![image](https://github.com/user-attachments/assets/87950e56-c54a-4353-968e-15d55d2792d1)

Resource usage without the reveal core:

![image](https://github.com/user-attachments/assets/0fa6ec50-bc6e-4fca-b370-eab8567d932f)













