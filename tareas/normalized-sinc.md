# Write a function to calculate the normalized sinc

The rectangular function (or square-pulse) is commonly used in signal processing applications. The Fourier transform of the rectangular function is the normalized sinc function given by:

        sinc(x) = sin(pi * x) / (pi * x)

Write a function `normsinc` that returns `sinc(x)`. Your function must:

1. Calculate `sinc(x)` for each element of the input. If the input is a 1-by-4 vector, the output is also a 1-by-4.

2. Return the value 1 when the input is 0, which is the limiting value of `sinc` as `x → 0`.

## Function

```matlab
function y = normsinc(x)
    % Implement the normalized sinc function
    y = sin(x * pi) ./ (x * pi);
    y(x == 0) = 1;
end
```