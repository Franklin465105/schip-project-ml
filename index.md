layout: home
title: FPGA VGA Driver Project
tags: fpga vga verilog
categories: demo
---

Hi, my name is Franklin and this is my project; in this project the first demo was me attempting the Irish and Nigerian flags, which I successfully achieved in doing and following that I'm going to attempt the Olympics logo and aswell as that the Microsoft logo.

- Sentence added: 16/11/2026, 15:49

## **Template VGA Design**
### **Project Set-Up**
<img width="533" height="343" alt="Screenshot 2026-11-16 163239" src="https://github.com/user-attachments/assets/1e1072a6-feb4-40df-b5a4-c89326b9864a" />

<img width="1146" height="640" alt="Screenshot 2026-11-16 160045" src="https://github.com/user-attachments/assets/db5505c1-0552-4bb9-9c64-00ed3aead415" />

### **Template Code**
A VGA screen draws one pixel at a time, going left to right and top to bottom. The monitor uses two timing signals, vsync and hsync; to know when to start a new line and a new frame.
Each pixel also gets a red, blue, or green values to set its colour and when you mix and match the amount of each colour you can get different ones.

The (VGASync) file counts across and down the screen. It creates the sync signals and tells us which pixel is being drawn on the monitor.
The (ColourStripes) file takes that pixel's position and decides what colour it should be assigned as. It then splits it into lines across the screen (In my case for the flags it splits into three different colours and stripes). Most of the VGA files in the project all look the same because only the drawing part changes. It almost never changes because the monitor timing always stays the same.

### **Simulation**
I used the testbench to simulate the design before putting it on the FPGA board. Simulation allowed me to check that the everything was working correctly and that the hsync and vsync signals were generated at the correct times. It also allowed me to verify that the row and column counters were going up properly. Overall, simulation gave confidence that the VGA display would work correctly when programmed onto the FPGA.

### **Synthesis**
For synthesis I ran Vivado's synthesis on the template, which turns the verilog code into the actual logic the FPGA uses. After that I ran
implementation, which places and routes everything onto the Artix-7 chip
on the Basys3 board, and then generated the bitstream.

### **Demonstration**
## **Week 4 - Nigerian Flag**
For this week, I experimented alot with the binary; originally I was trying to get the Irish flag which I ended up getting in the week after this one, I ended up with the Nigerian flag and realised that it was because I had my binary wrong for the colours when it came to orange; which left me with two bright neon green stripes and one white stripe in the middle. Prior to having three stripes, I still had many stripes spanning across the width of the screen; which I narrowed down to just 3 stripes by removing the extra lines of code to achieve this. (Unfortunately I do not have a picture but I did demonstrate this in class) In the week following this I explain how I achieved the Irish flags colours.

## **Week 5 - Irish Flag**
I experimented with the Colour Stripes design file to create the Irish flag, what I did with the help of Google gemini was figure out which columns need to be edited/deleted and based on binary I altered the remaining columns which was three because there are three main columns in the Irish flag. Each columns binary was edited to match the ireland flags colours. Also the pixels themselves were altered to giv earound the same amount of numbers. (640 / 3 = 213 roughly) which gives even enough stripes.

Below is the irish flag working on the monitor.
<img width="1920" height="1440" alt="fcd10561-4863-499d-8e35-fe12061a5830" src="https://github.com/user-attachments/assets/c718db84-16b5-457d-90c2-27ca0c6ce0d6" />

### **Code Adaptation**
I only changed the ColourStripes file. I split the screen into three stripes of about 213 pixels each and set the red, green and blue values for each
one. Green on the left, white in the middle and orange on the right for the irish flag. I had no need to edit the VGASync file because it just does the VGA timing, and that stays the same for any
image. I wasn't switching between screens, so I didn't need to change the clock at all. My final image would have been the olympic flag but I didn't have enough time to complete it.

I will say though this project helped me better understand how exaclty the binary works. Each colour is just a few bits, and changing them changes the shade on the
screen.

### **Synthesis**
I ran synthesis and implementation again on my Irish flag design and both worked. I dont recall getting any warnings. The reults were about the same as the template. That's because I only
changed the colours and where the stripes start and stop, so it uses about the same amount of logic.

## **Conclusion**
In the end I got the Nigerian and Irish flags working on the Basys3 board. The hardest part was getting the binary right for the colours, especially the orange, because my first attempt gave me two neon green
stripes. It also helped me understand binary much better, because I could see the bits I changed turn into real colours on the monitor.

One thing though is that I didn't give myself enough time to finish the Olympics logo; which would have been really cool to see/attempt!
