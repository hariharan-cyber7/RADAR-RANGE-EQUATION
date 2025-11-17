# RADAR-RANGE-EQUATION
Evaluation of Radar Range Using Scilab
## Aim
To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through Scilab programming.

## Theory
The Radar Range Equation is a key relationship used in radar system design to determine the maximum distance (range) at which a radar can detect a target.

It is expressed as:

## Algorithm
1.Initialize constants: λ (wavelength) = 0.03 m σ (radar cross section) = 1 m²

2.Vary each parameter while keeping the others constant: Pt: 0.1 → 10 Gt: 1 → 50 Pm: 1e⁻¹⁵ → 1e⁻¹⁰

3.Compute maximum range using: R_max = ((Pt * Gt² * λ² * σ) / ((4π)³ * Pm))¼

4.Plot the following: Pt vs Rmax Gt vs Rmax Pm vs Rmax

## Procedure
1.Refer to the Algorithm and write the Scilab code for the experiment.

2.Open Scilab on your system.

3.Create a New Editor File: Go to File → New → Script.

4.Type Your Code in the editor window.

5.Save the File with a suitable name (e.g., radar_range.sce).

6.Execute the Code: Press F5 or click Execute → File with echo.

7.If Any Errors Occur: Review and correct the code. Save and run it again until it executes successfully.

## Code
```sci
G = 40;
eta = 0.5;
Ae = 1;
Smin = 1e-10;
Ppeak= 2000:100:10000; 
Rmax_values = zeros(1, length(Ppeak));
for i = 1:length(Ppeak)
    Rmax_values(i) = ((Ppeak(i) * G * eta * Ae) / (16 * %pi^2 * Smin))^(1/4);
end
clf;
subplot(3,1,1);
plot(Ppeak, Rmax_values,'b');
xlabel('P_{peak}');
ylabel('R_{max}');

clear "G" "Rmax_values" "Ppeak";
Ppeak = 5000;
G = 10:5:100;
Rmax_values = zeros(1, length(G));

for i = 1:length(G)
    Rmax_values(i) = ((Ppeak * G(i) * eta * Ae) / (16 * %pi^2 * Smin))^(1/4);
end

subplot(3,1,2);
plot(G, Rmax_values,'r');
xlabel("G");
ylabel("R_{max}");

clear "G" "Rmax_values" "Smin";
G = 40;
Smin_values = logspace(-12, -8, 50);
Rmax_values = zeros(1, length(Smin_values));

for i = 1:length(Smin_values)
    Rmax_values(i) = ((Ppeak * G * eta * Ae) / (16 * %pi^2 * Smin_values(i)))^(1/4);
end

subplot(3,1,3);
plot(Smin_values, Rmax_values,'g');
xlabel("S_{min}");
ylabel("R_{max}");
```


## Output image
<img width="760" height="743" alt="image" src="https://github.com/user-attachments/assets/72400051-1c0b-4643-8b96-9c5822ccf66f" />

## Manual Calculation


## Result
Thus, the maximum range of a radar system calculated using the Radar Range Equation is successfully verified using Scilab programming.
