# Solve differential equations

In Maple, you may solve the equation $y'(x)=k y(x) + c$ (which is called an ODE) using the command `dsolve({ics, eq})`, where `ics` stands for initial condition $y(0)=c$ and `eq` stands for the differential equation. Without the `ics`, `dsolve` will provide a general solution.

\BeginKnitrBlock{example}<div class="example"><span class="example" id="exm:unnamed-chunk-1"><strong>(\#exm:unnamed-chunk-1) </strong></span>Find the function $f(x)$ which satisfies the differential equation $f'(x)=k f(x)$ with $f(0)=5$ and $f(2)=3$.
</div>\EndKnitrBlock{example}

\BeginKnitrBlock{solution}<div class="solution">\iffalse{} <span class="solution"><em>Solution. </em></span>  \fi{}<br>
Use the following command

    dsolve({f(0)=5, f'(x)=k f(x)})

we get $f(x)=5e^{kx}$.

To find $k$, we solve the equation $3=5e^{2k}$ by

    solve(3=5*e^(2*k), k)

which shows that $k=\frac{\ln3-\ln5}{2}\approx -0.255$.
Here we use `evalf(%)` (% represents the previous result) to get the approximation.

So the function $f$ is given by
$$
f(x)=5e^{\frac{x(\ln3-\ln5)}{2}}\approx 5e^{-0.255x}.
$$
</div>\EndKnitrBlock{solution}

\BeginKnitrBlock{exercise}<div class="exercise"><span class="exercise" id="exr:unnamed-chunk-3"><strong>(\#exr:unnamed-chunk-3) </strong></span>
Find the function $y$ which satisfies the  differential equation $y'(x)=k y(x)$ with $y(0)=2$ and $y(5)=11$.
</div>\EndKnitrBlock{exercise}
