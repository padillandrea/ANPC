# Case Study: Particle with a Constant Acceleration (Polynomial Regression)

## Script

```matlab
load measurements

% Fit the data with a regression to a quadratic polynomial.
f = polyfit(t, x, 2);

% Compute the fitted model values.
xfit  = polyval(f, t);

% Obtain the physical model coefficients.
a = f(1) * 2;
v0 = f(2);
x0 = f(3);

%%%%%%%%%%%%% Plotting Code Below %%%%%%%%%%%%%%%
% Plot the results.
plot(t,x,'ro', t,xfit,'b');
xlabel('time [s]');
ylabel('position [m]');
title('Position of a particle under constant acceleration');
grid;

% Print the results.
fprintf('.\n');
fprintf(' a = %5.3f [m/s^2]\n',a); 
fprintf('v0 = %5.3f [m/s]\n',v0); 
fprintf('x0 = %.3e [m]\n',x0); 
```