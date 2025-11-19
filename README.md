# Evaluation of Radar Range Using Scilab
---

## Aim
To calculate the **maximum range of a radar system** using the **Radar Range Equation** and verify the results through **Scilab programming**.

---

## Theory
The **Radar Range Equation** is a key relationship used in radar system design to determine the maximum distance (**range**) at which a radar can detect a target.  

It is expressed as:

<img width="965" height="329" alt="image" src="https://github.com/user-attachments/assets/d8d311e3-5625-4a58-966c-ca75dbb5109d" />

---

## Algorithm

1. Initialize constants:
   - λ (wavelength) = 0.03 m  
   - σ (radar cross section) = 1 m²  

2. Vary each parameter while keeping the others constant:
   - **Pt:** 0.1 → 10  
   - **Gt:** 1 → 50  
   - **Pm:** 1e⁻¹⁵ → 1e⁻¹⁰  

3. Compute maximum range using:
   R_max = ((Pt * Gt² * λ² * σ) / ((4π)³ * Pm))¼


4. Plot the following:
   - `Pt vs Rmax` 
   - `Gt vs Rmax` 
   - `Pm vs Rmax`
     
---

## Procedure

1. **Refer to the Algorithm** and write the Scilab code for the experiment.  
2. **Open Scilab** on your system.  
3. **Create a New Editor File:**  
   - Go to `File → New → Script`.  
4. **Type Your Code** in the editor window.  
5. **Save the File** with a suitable name (e.g., `radar_range.sce`).  
6. **Execute the Code:**  
   - Press **F5** or click **Execute → File with echo**.  
7. **If Any Errors Occur:**  
   - Review and correct the code.  
   - Save and **run it again** until it executes successfully.

---

##  Code 
```scilab

Gr = 50;
w = 8;
sigma = 9;  
pmin = 1e-10;
Gt = 10;
Pt = 0.5:0.5:100;   
Rmax1 = (((Pt .* Gt .* Gr .* (w.^2) .* sigma) ./ (((4 * %pi).^3) .* pmin))).^(1/4);
subplot(3,1,1);
plot(Pt, Rmax1);

Pt = 15;
Gt = 0.1:0.1:9;     
Rmax2 = (((Pt .* Gt .* Gr .* (w.^2) .* sigma) ./ (((4 * %pi).^3) .* pmin))).^(1/4);
subplot(3,1,2);
plot(Gt, Rmax2);

Gt = 5;
pmin = 1e-14:1e-13:1e-9;  
Rmax3 = (((Pt .* Gt .* Gr .* (w.^2) .* sigma) ./ (((4 * %pi).^2) .* pmin))).^(1/4);
subplot(3,1,3);
plot(pmin,Rmax3);




```

## Output

<img width="1917" height="1137" alt="image" src="https://github.com/user-attachments/assets/a015361e-384d-4d29-9d6d-b99fbe40911f" />




## Manual Calculation

![WhatsApp Image 2025-11-13 at 12 52 31_00bc96de](https://github.com/user-attachments/assets/4e5118b6-39f1-4ab9-b65e-aebd95d0f8a4)




## Result

Thus, the maximum range of a radar system calculated using the Radar Range Equation is successfully verified using Scilab programming.

