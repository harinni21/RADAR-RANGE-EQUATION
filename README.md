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

Pt = 500;
G = 500;
sigma = 1;
Ae = 10;

Smin = logspace(-12, -6, 100);
Rmax = ((Pt * G * sigma * Ae) ./ (16 * %pi^2 .* Smin)).^(1/4);
subplot(3,1,1);
plot(Smin, Rmax);

Ppeak = linspace(100, 10000, 100);
Rmax2 = ((Ppeak * G * sigma * Ae) ./ (16 * %pi^2 * 1e-5)).^(1/4);
subplot(3,1,2);
plot(Ppeak, Rmax2);

Gt = linspace(100, 2000, 100);
Rmax3 = ((Pt * Gt * sigma * Ae) ./ (16 * %pi^2 * 1e-5)).^(1/4);
subplot(3,1,3);
plot(Gt, Rmax3);



```

## Output

<img width="1260" height="749" alt="image" src="https://github.com/user-attachments/assets/b82b53c1-33eb-456d-a0b6-3fd32e0eee4a" />




## Manual Calculation

<img width="550" height="864" alt="image" src="https://github.com/user-attachments/assets/e16d5ba8-b290-4ac1-bcec-6c2f6832885b" />




## Result

Thus, the maximum range of a radar system calculated using the Radar Range Equation is successfully verified using Scilab programming.

