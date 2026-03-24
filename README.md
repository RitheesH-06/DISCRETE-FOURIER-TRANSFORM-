# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 
To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
## DISCRETE FOURIER TRANSFORM
```
clc; 
clear; 
xn=[1 1 1 1 0 0 0 0]; 
n1=0:1:length(xn)-1; 
subplot(3,1,1); 
plot2d3(n1,xn); 
xlabel('Time n'); 
ylabel('Amplitude xn'); 
title('Input Sequence'); 
j=sqrt(-1); 
N=length(xn); 
Xk=zeros(1,N); 
for k=0:N-1 
for n=0:N-1 
Xk(k+1)=Xk(k+1)+xn(n+1)*exp((-j*2*%pi*k*n)/N); 
end 
end 
disp(Xk) 
K1=0:1:length(Xk)-1; 
magnitude=abs(Xk) 
subplot(3,1,2); 
plot2d3(K1,magnitude); 
xlabel('frequency(Hz)'); 
ylabel('magnitude(gain)'); 
title('magnitude spectrum'); 
angle = atan(imag(Xk),real(Xk)) 
subplot(3,1,3); 
plot2d3(K1,angle); 
xlabel('frequency(Hz)'); 
ylabel('Phase'); 
title('Phase spectrum');
```
##  FAST FOURIER TRANSFORM
```
clear; 
clc; 
close; 
xn = [1 1 1 1 0 0 0 0] 
n1=0:1:length(xn)-1; 
subplot(2,2,1); 
plot2d3(n1,xn); 
xlabel('Time n'); 
ylabel('Amplitude'); 
title('Input Sequence'); 
Xk = fft(xn); 
K1=0:1:length(Xk)-1; 
magnitude=abs(Xk) 
subplot(2,2,2); 
plot2d3(K1,magnitude); 
xlabel('frequency(Hz)'); 
ylabel('magnitude(gain)'); 
title('magnitude spectrum'); 
angle = atan(imag(Xk),real(Xk)) 
subplot(2,2,3); 
plot2d3(K1,angle); 
xlabel('frequency(Hz)'); 
ylabel('Phase'); 
title('Phase spectrum') 
y= ifft(Xk) 
n2=0:1:length(y)-1; 
subplot(2,2,4) 
plot2d3(n2,y) 
xlabel('Time n'); 
ylabel('Amplitude'); 
title('Inverse FFT OF X(K)');
```

# OUTPUT: 

<img width="1614" height="866" alt="image" src="https://github.com/user-attachments/assets/42dfe597-0e22-400c-a99e-b531704271ea" />

<img width="1754" height="866" alt="image" src="https://github.com/user-attachments/assets/a1cee1c4-8c66-4b2b-a3c8-da94b185f358" />

# RESULT: 

The DFT and FFT of the given input sequence were computed and the magnitude and phase spectra were plotted successfully.
