# EX.-2-FORMATION-OF-Y-BUS-MATRIX-BY-SINGULAR-TRANSFORMATION-METHOD-
# AIM:  
To develop a program to obtain bus admittance matrix for the given power 
system network by singular transformation method.

# SOFTWARE REQUIRED:
MATLAB Software

# THEORY: 
Bus admittance matrix is often used in power system studies. In most of the 
power system studies, it is necessary to form [Y-bus] matrix of the system by considering 
certain power system parameters depending upon the type of analysis. 
For example, in the load flow analysis it is necessary to form [Y-bus] matrix 
without taking into account the generator impedance, transformer impedance must be taken 
into account in addition to the line data. 
In stability analysis, line data, the generator transient reactance, transformer 
impedances and equivalent load impedance are taken into account. 
Y-bus may be formed by singular transformation method only if there is 
mutual coupling between the lines.  

# ALGORITHM: 
1. Start the program. 
2. Initialize the matrix values to zero. 
3. Read the branch elements and nodes. 
4. Check the type of connection between the node and elements to formulate the 
incidence matrix. 
5. Put -1 to element pointing towards the node, put +1 to element pointing away from 
the node and put 0 to element having no connection with the node. 
6. Find the transpose of A-matrix. 
7. Check whether the element is impedance or admittance. 
8. If impedance then convert their value into admittance using appropriate formula. 
9. Form Y-bus primitive matrix by assigning values of branch elements to the diagonal 
of matrix. 
10. Formulate Y-bus using the formula Y-bus= AT*Yprimitive*A. 
11. Print the resultant Y-bus matrix. 
12. Stop the execution.
    
# PROGRAM: 
Formation of Y-bus using Singular transformation method: 
```
clear; 
clc; 
n=input('number of buses'); 
e=input('number of elements'); 
a=zeros(e,n); 
y=zeros(e,e); 
for i=1:e 
y(i,i)=input('element value'); 
c=input(' checking whether Z or Y 1 for Z 2 for Y'); 
if c==1 
y(i,i)=1/y(i,i); 
end 
end 
for i=1:e 
s=input('starting bus'); 
b=input('ending bus'); 
a(i,s)=1; 
a(i,b)=-1; 
end 
y 
a' 
a'*y*a
```
# OUTPUT:
<img width="990" height="464" alt="image" src="https://github.com/user-attachments/assets/a83af987-0ac3-4a58-a917-fac05cc16202" />

# RESULT:
Thus, To develop a program to obtain bus admittance matrix for the given power system network by singular transformation method is successfully done in matlab and the output is obtained.
