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
Explain the simulation process. Reference any important details, include a well-selected screenshot of the simulation. Guideline: 1/2 short paragraphs.

### **Synthesis**
Describe the synthesis and implementation processes. Consider including 1/2 useful screenshot(s). Guideline: 1/2 short paragraphs.

### **Demonstration**
Perhaps add a picture of your demo. Guideline: 1/2 sentences.

## **Week 5**
I experimented with the Colour Stripes design file to create the Irish flag, what I did with the help of Google gemini was figure out which columns need to be edited/deleted and based on binary I altered the remaining columns which was three because there are three main columns in the Irish flag. Each columns binary was edited to match the ireland flags colours. Also the pixels themselves were altered to giv earound the same amount of numbers. (640 / 3 = 213 roughly) which gives even enough stripes.

### **Code Adaptation**
Briefly show how you changed the template code to display a different image. Demonstrate your understanding. Guideline: 1-2 short paragraphs.
### **Simulation**
Show how you simulated your own design. Are there any things to note? Demonstrate your understanding. Add a screenshot. Guideline: 1-2 short paragraphs.
### **Synthesis**
Describe the synthesis & implementation outputs for your design, are there any differences to that of the original design? Guideline 1-2 short paragraphs.
### **Demonstration**
If you get your own design working on the Basys3 board, take a picture! Guideline: 1-2 sentences.

## **More Markdown Basics**
This is a paragraph. Add an empty line to start a new paragraph.

Font can be emphasised as *Italic* or **Bold**.

Code can be highlighted by using `backticks`.

Hyperlinks look like this: [GitHub Help](https://help.github.com/).

A bullet list can be rendered as follows:
- vectors
- algorithms
- iterators
