# Power method

Programa la función `powerMethod` que recibe una matriz cuadrada y regresa su mayor valor propio (en valor absoluto) y su correspondiente vector propio.

En la práctica, los valores propios de las matrices extensas no se calculan usando el polinomio característico. Calcular el polinomio resulta muy costoso, y extraer las raíces exactas de un polinomio de grado alto puede ser difícil de calcular y expresar. En consecuencia, los algoritmos generales para encontrar vectores propios y valores propios son  iterativos. La manera más fácil es el método de las potencias.

Multiplying by a matrix `A` repeatedly will exponentially amplify the largest `∣λ∣` eigenvalue. This is the basis for many algorithms to compute eigenvectors and eigenvalues, the most basic of which is known as the power method. The simplest version of this is to just start with a random vector `x` and multiply it by `A` repeatedly. This works, but has the practical problem that the vector quickly becomes very large or very small, and eventually becomes too big/small for the computer to represent (this is known as "oveflow/underflow"). The fix is easy: normalize the vector after each multiplication by `A`. That is, starting with a random `x`, repeatedly compute

```
x = Ax / ||Ax||
```

If x was the exact eigenvector, we could just multiply Ax and see how much each component increased: they would all increase (or decrease) by the same factor. But, for an approximate eigenvector, each component of `Ax` will increase by a slightly different amount. Instead, the most common approach is to use the Rayleigh quotient. If we have an exact eigenvector, so that `Ax = λx`, then the Rayleigh quotient will gives us exactly `λ`. Otherwise, it is a kind of weighted-average and is a reasonable approximation

```
λ = x * Ax / x * x
```