# EXP 1 : Linear and Circular Convolution

# AIM: 

# To perform Linear and Circular Convolution for two given sequence using SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM (Linear Convolution): 
~~~
clear;
clc;
close;
x = [1 1 2 1];
h = [1 2 3 4];
m = length(x);
n = length(h);
N = m + n - 1;
y = zeros(1, N);
for i = 1:N
    sum_val = 0;
    for j = 1:i
        if (j <= m) & ((i - j + 1) <= n) then
            sum_val = sum_val + x(j) * h(i - j + 1);
        end
    end
    y(i) = sum_val;
end
nx = 0:m-1;      
nh = 0:n-1;      
ny = 0:N-1;      
scf(0);
subplot(3,1,1);
plot2d3(nx, x, style=2);    // stem plot
xlabel("Time"); ylabel("Amplitude");
title("Graphical Representation of Input Signal X");
subplot(3,1,2);
plot2d3(nh, h, style=5);
xlabel("Time"); ylabel("Amplitude");
title("Graphical Representation of Impulse Signal h");
subplot(3,1,3);
plot2d3(ny, y, style=3);
xlabel("Time"); ylabel("Amplitude");
title("Graphical Representation of Output Signal y");
~~~

# PROGRAM (Circular Convolution): 

// Circular Convolution
clc;
clear;

x = [1, 2, 2,1];
h = [1, 2,3,1];


N = max(length(x), length(h));


x = [x, zeros(1, N - length(x))];
h = [h, zeros(1, N - length(h))];


y = zeros(1, N);


for n = 1:N
    for k = 1:N
        index = modulo(n - k + N, N) + 1;
        y(n) = y(n) + x(k) * h(index);
    end
end

disp("Circular Convolution Result:");
disp(y);

# OUTPUT (Linear Convolution): 
<img width="908" height="531" alt="image" src="https://github.com/user-attachments/assets/cf097506-87e5-49c0-97d0-9043b2672271" />


# OUTPUT (Circular Convolution): 
<img width="908" height="375" alt="image" src="https://github.com/user-attachments/assets/ba078b9e-6855-4d1d-a651-8823c0033997" />


# RESULT: 
