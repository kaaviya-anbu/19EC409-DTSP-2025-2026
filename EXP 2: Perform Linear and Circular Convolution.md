# EXP 1 : Linear and Circular Convolution

# AIM: 

# To perform Linear and Circular Convolution for two given sequence using SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM (Linear Convolution): 

// Linear Convolution
clc;
clear;


x = [1,1,2,1];
h = [1,2,3,4];


Lx = length(x);
Lh = length(h);
Ly = Lx + Lh - 1;


x_padded = [x, zeros(1, Lh - 1)];
h_padded = [h, zeros(1, Lx - 1)];


y = zeros(1, Ly);
for n = 1:Ly
    for k = 1:n
        if (k <= Lx & (n - k + 1) <= Lh) then
            y(n) = y(n) + x(k) * h(n - k + 1);
        end
    end
end

disp("Linear Convolution Result:");
disp(y);


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
 


# OUTPUT (Circular Convolution): 


# RESULT: 
