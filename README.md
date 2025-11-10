# EXP 6 : SIMULATION OF MULTIRATE DSP WITHOUT FUNCTION

## AIM: 

To perform and verify multirate DSP without function using SCILAB.

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM : 
```asm
n = 0:%pi/50:2*%pi;
x = sin(n); // Original signal
// Input upsampling and downsampling factors
M = input("Enter the downsampling factor M: ");
L = input("Enter the upsampling factor L: ");
```
// --- Downsampling ---
```asm
downsampling_x = x(1:M:$);
disp(x, "Input signal x(n) = ");
disp(downsampling_x, "Downsampled signal x(Mn) = ");
// Plot original and downsampled signals
scf(1);
subplot(2,1,1);
plot2d3(1:length(x), x);
xtitle("Original Signal");
subplot(2,1,2);
plot2d3(1:length(downsampling_x), downsampling_x);
xtitle("Downsampled Signal by a factor of M");
```
// --- Upsampling ---

```asm
upsampling_x = zeros(1, L*length(x));
for i = 1:length(x)
    upsampling_x((i-1)*L + 1) = x(i);
end

disp(upsampling_x, "Upsampled signal x(n/L) = ");
// Plot original and upsampled signals
scf(2);
subplot(2,1,1);
plot2d3(1:length(x), x);
xtitle("Original Signal");

subplot(2,1,2);
plot2d3(1:length(upsampling_x), upsampling_x);
xtitle("Upsampled Signal by a factor of L");
```
## OUTPUT: 
# DOWNSAMPLING
<img width="756" height="719" alt="Screenshot 2025-11-10 152751" src="https://github.com/user-attachments/assets/ae369e55-4f1b-4951-b22c-80af95b06610" />

# UPSAMPLING
<img width="757" height="718" alt="Screenshot 2025-11-10 152816" src="https://github.com/user-attachments/assets/d324897f-6b7c-41cf-bb50-5b0dabcc85a7" />

## RESULT: 
Thus the decimation process by a factor M and interpolation process by a factor L using  SCILAB was implemented. 
