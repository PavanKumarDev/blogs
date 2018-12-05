**Bloch Sphere in Quantum Computing**

A Bloch Sphere is a unit sphere in 3D. A qubit in any state can be
visualized as a point on the surface of this sphere. This blog explains
how this is achieved.

We know that any generic qubit is of the following form:

$$|\left. \ \psi \right\rangle = \ (a + ib)|\left. \ 0 \right\rangle + \ (c + id)|\left. \ 1 \right\rangle$$

Before proceeding further, let's talk about complex numbers a bit. Any
complex number $a + ib$ can be written in polar form as follows:

$$re^{\text{iθ}}$$

Where $r\ (magnitude) = \ \sqrt{a^{2} + b^{2}}$ and
$\theta\ (phase) = \ \operatorname{}{(\frac{b}{a})}$

So, we can write the generic qubit in polar form as follows:

$$|\left. \ \psi \right\rangle = \ r_{1}e^{i\theta_{1}}|\left. \ 0 \right\rangle + \ r_{2}e^{i\theta_{2}}|\left. \ 1 \right\rangle$$

(Eq. 1.0)

Here, the probability equations become:

$$Pr(|0\rangle) = \ \left| r_{1}e^{i\theta_{1}} \right|^{2}{= \ r1}^{2}$$

$$Pr(|1\rangle) = \ \left| r_{2}e^{i\theta_{2}} \right|^{2}{= \ r2}^{2}$$

One thing to notice here is that, though the qubit is defined using 4
parameters ($r1$, $r2$, $\theta 1$ and $\theta 2)$, the actual
probabilities are just functions of $r1$ and $r2$ and don't depend on
$\theta 1$ and $\theta 2$. Which means that if we apply any unitary
operation or any sequence of unitary operations that just change the
phases but no the magnitudes, the probabilities will not change.

Let's consider that following is some unitary matrix:

U = $\begin{bmatrix}
r_{a}e^{i\theta_{a}} & r_{b}e^{i\theta_{b}} \\
r_{c}e^{i\theta_{c}} & r_{d}e^{i\theta_{d}} \\
\end{bmatrix}$

Applying U on $|\left. \ \psi \right\rangle$ results in:

$$U\left( \  \middle| \left. \ \psi \right\rangle \right) = \ \ \begin{bmatrix}
r_{a}e^{i\theta_{a}} & r_{b}e^{i\theta_{b}} \\
r_{c}e^{i\theta_{c}} & r_{d}e^{i\theta_{d}} \\
\end{bmatrix}*\ \begin{bmatrix}
r_{1}e^{i\theta_{1}} \\
r_{2}e^{i\theta_{2}} \\
\end{bmatrix} = \ \begin{bmatrix}
r_{a}{r_{1}e}^{i\theta_{a} + i\theta_{1}} + \ r_{b}r_{2}e^{i\theta_{b} + \text{iθ}_{2}} \\
r_{c}r_{1}e^{i\theta_{c} + i\theta_{1}} + r_{d}{r_{2}e}^{i\theta_{d} + i\theta_{2}} \\
\end{bmatrix}$$

(Eq: 1.1)

Now, let's see how addition works with complex numbers. If we take two
complex numbers $x1 + iy1\ and\ x2 + iy2$, the sum is given by
($x1 + x2) + i(y1 + y2)$. But addition rules work a little differently
when the complex numbers are in polar form. In polar form, they behave
as vectors and we have to use parallelogram law of addition to get the
final sum.

Let's say we have two complex numbers $r_{x}e^{i\theta_{x}}$and
$r_{y}e^{i\theta_{y}}$, we can draw them in the complex plane as
follows:

![](media/image1.png){width="4.213542213473316in"
height="2.9461351706036747in"}

Now, the resultant complex number after adding these two complex numbers
is achieved by using the parallelogram law of vectors. We need to attach
the tail of the second vector to the head of the first and create a
parallelogram. The resultant vector ($r_{z}e^{i\theta_{z}}$) will be the
diagonal as shown:

![](media/image2.png){width="4.6875in" height="2.8867738407699037in"}

Now, let's say before adding them, we rotate both the complex numbers by
some angle $\theta$, then the input complex numbers would look as
follows(the magnitudes are kept as same; we added $\theta$ to the phases
of both the complex numbers) :

![](media/image3.png){width="3.1979166666666665in"
height="2.5232622484689413in"}

Now, if we add them, we get the following result:

![](media/image4.png){width="3.2410837707786526in"
height="3.9166666666666665in"}

Notice here that even after adding some angle to the input complex
numbers, the magnitude of the output complex number didn't change
(though the angle changed).

Now, let's see what happens if we add different angles to the input
vectors before performing the addition:

![](media/image5.png){width="4.223958880139983in"
height="3.153666885389326in"}

After addition:

![](media/image6.png){width="5.2243055555555555in"
height="3.526388888888889in"}

Here clearly $r_{z}\ ! = \ {r_{z}}^{'}$. The moral here is that as long
as we add same phase to two complex numbers, the magnitude of the sum of
those two complex numbers will not change; however, if we add different
phases to the input complex numbers, the magnitude of the sum of them
will change.

Now, lets add an angle of $\theta$, to both the states in Eq. 1.0:

$$|\left. \ \psi^{'} \right\rangle = \ r_{1}e^{i\theta_{1} + i\theta}|\left. \ 0 \right\rangle + \ r_{2}e^{i\theta_{2} + i\theta}|\left. \ 1 \right\rangle$$

(Eq. 1.2)

Now, apply U on this state:

$$U\left( \  \middle| \left. \ \psi^{'} \right\rangle \right) = \ \ \begin{bmatrix}
r_{a}e^{i\theta_{a}} & r_{b}e^{i\theta_{b}} \\
r_{c}e^{i\theta_{c}} & r_{d}e^{i\theta_{d}} \\
\end{bmatrix}*\ \begin{bmatrix}
r_{1}e^{i\theta_{1} + i\theta} \\
r_{2}e^{i\theta_{2} + i\theta} \\
\end{bmatrix} = \ \begin{bmatrix}
r_{a}{r_{1}e}^{i\theta_{a} + i\theta_{1} + i\theta} + \ r_{b}r_{2}e^{i\theta_{b} + \text{iθ}_{2} + i\theta} \\
r_{c}r_{1}e^{i\theta_{c} + i\theta_{1} + i\theta} + r_{d}{r_{2}e}^{i\theta_{d} + i\theta_{2} + i\theta} \\
\end{bmatrix}$$

(Eq. 1.3)

Compare Eq. 1.1 and Eq. 1.3; consider the complex numbers in the first
row:

$$r_{a}{r_{1}e}^{i\theta_{a} + i\theta_{1}} + \ r_{b}r_{2}e^{i\theta_{b} + \text{iθ}_{2}}$$

and

$$r_{a}{r_{1}e}^{i\theta_{a} + i\theta_{1} + i\theta} + \ r_{b}r_{2}e^{i\theta_{b} + \text{iθ}_{2} + i\theta}$$

The magnitude of the complex number resulting from the first addition
will be exactly same as the magnitude of the complex number resulting
from the second addition. Same is the case with the complex numbers in
the second row. We had proved earlier that the probabilities depend only
on the magnitude but not on the phase. So, we can conclude that, as long
as we add the same phase to both the probability amplitudes (for
$|\left. \ 0 \right\rangle\ and\ |\left. \ 1 \right\rangle)$, the final
probabilities will not change even if we perform any number of unitary
operations on this qubit. There difference is not *observable*. So,
$|\left. \ \psi^{'} \right\rangle\text{\ and\ }|\left. \ \psi \right\rangle$
are effectively the same because the global phase ($e^{\text{iθ}}$) can
always be ignored.

Equipped with this information, let's put $\theta = \  - \theta_{1}$ in
Eq. 1.2

$$|\left. \ \psi \right\rangle = \ r_{1}e^{i\theta_{1} - i\theta_{1}}|\left. \ 0 \right\rangle + \ r_{2}e^{i\theta_{2} - i\theta_{1}}|\left. \ 1 \right\rangle$$

$$\text{\ \ \ \ \ \ \ \ } = \ r_{1}|\left. \ 0 \right\rangle + \ r_{2}e^{i\theta_{2} - i\theta_{1}}|\left. \ 1 \right\rangle$$

Let's replace $\theta_{2} - \theta_{1}$with $\varphi$:

$$|\left. \ \psi \right\rangle = \ r_{1}|\left. \ 0 \right\rangle + \ r_{2}e^{i\varphi}|\left. \ 1 \right\rangle$$

Notice here that we are effectively making the probability amplitude of
$|\left. \ 0 \right\rangle$ to always a real number. So, the actual
phases of $|\left. \ 0 \right\rangle$ and $|\left. \ 1 \right\rangle$
don't really matter; only thing that matters is the phase difference
$\theta_{2} - \theta_{1}(i.e\ \varphi)$

So, given any qubit in the following state:

$$|\left. \ \psi \right\rangle = \ r_{1}e^{i\theta_{1}}|\left. \ 0 \right\rangle + \ r_{2}e^{i\theta_{2}}|\left. \ 1 \right\rangle$$

![](media/image7.png){width="4.192708880139983in"
height="3.0823458005249345in"}

We can write it as:

$$|\left. \ \psi \right\rangle = \ r_{1}|\left. \ 0 \right\rangle + \ r_{2}e^{i\varphi}|\left. \ 1 \right\rangle$$

(Eq. 1.4)

![](media/image8.png){width="6.213888888888889in"
height="2.8229166666666665in"}

Here, since $\varphi$ is the phase difference between the two states,
the range of it will be 0 - 360.

We also know that $Pr(|0\rangle) + \ Pr(|1\rangle) = 1$

-   ${r_{1}}^{2} + {r_{2}}^{2} = 1$ (also both $r_{1}$and $r_{1}$will be
    non-negative as they are magnitudes of complex numbers)

So, we can say that for every combination of $r_{1}$and $r_{2}$ as
constrained above, there will be an angle $x$ such that they form the
sides of a right angled triangle with hypotenuse of length 1:

![](media/image9.png){width="2.120138888888889in"
height="1.3493055555555555in"}

$$r_{1} = \ \ 1*\cos x$$

$$r_{2} = \ \ 1*\sin x$$

So, Eq. 1.4 can be written as:

$$\left| \left. \ \psi \right\rangle = \cos x \right|\left. \ 0 \right\rangle + \sin x*e^{i\varphi}|\left. \ 1 \right\rangle$$

Here, the thing to be noticed is that the range of $x$ will be 0 -- 90;
because the smallest value will be when $r_{2} = 0$ and $r_{1} = 1$; and
highest will be when $r_{2} = 1$ and $r_{1} = 0$. For every such $x$,
there will be an angle $\theta$ (with the range 0 - 180) such that
$\theta = 2x$. So, the above equation becomes:

$$\left| \left. \ \psi \right\rangle = \cos{(\theta/2)} \right|\left. \ 0 \right\rangle + \sin{(\theta/2)}*e^{i\varphi}|\left. \ 1 \right\rangle$$

(Eq. 1.5)

Why we had to introduce $\theta$ with double the value of $x$ will be
clear later, but it is for sure that this is not mathematically
incorrect.

What we just did is that given any generic qubit
($r_{1}e^{i\theta_{1}}|\left. \ 0 \right\rangle + \ r_{2}e^{i\theta_{2}}|\left. \ 1 \right\rangle$),
we can write it in the form $
\left| \left. \ \psi \right\rangle = \cos{(\theta/2)} \right|\left. \ 0 \right\rangle + \sin{(\theta/2)}*e^{i\varphi}|\left. \ 1 \right\rangle$
parameterized by $\theta$ (with range 0 -- 180) and $\varphi$ (with
range 0 -- 360) without losing any useful information.

Now, let's proceed with the second half of the problem. Given any unit
sphere, what will be the polar co-ordinates of any point on the surface
of it?

![](media/image10.png){width="3.3541666666666665in"
height="2.995138888888889in"}

For any given point on the surface of this unit sphere, we can define
two angles $\theta$ and $\varphi$. $\text{θ\ }$is the angle between the
$z$ axis and the line connecting the origin with the point with which we
are concerned. Now, drop a perpendicular from this point onto the
$\text{xy}$ plane and connect that point on $\text{xy}$ plane to the
origin. The angle made by this line with the $x$ axis is defined as
$\varphi$. Now, we can check that, if we start from the north pole
(where $\theta = 0$), for every miniscule increment of $\theta$, we can
sweep an entire layer of this sphere by changing $\varphi$ from 0 to
360. By the time we reach the south pole (where $\theta = 180$) like
this, we would have covered the entire sphere. So, as defined above, any
point on the surface of this unit sphere can be parameterized by two
angles $\theta$ (with range 0 to 180) and $\varphi$ (with range 0 to
360).

Now, compare this conclusion with that of Eq. 1.5. Thus, we have proved
that given any generic qubit state, we can visualize it as a point on a
unit sphere.

Let's try to fix few important qubit states on this sphere.

**For**
$\left| \left. \ \mathbf{\psi} \right\rangle\mathbf{=} \right|\left. \ \mathbf{0} \right\rangle$**:**

To calculate $\theta$ and $\varphi$ for this state, we need to equate
this to the Eq. 1.5:

$$\left| \left. \ 0 \right\rangle = \cos{(\theta/2)} \right|\left. \ 0 \right\rangle + \sin{(\theta/2)}*e^{i\varphi}|\left. \ 1 \right\rangle$$

Which means $\cos{(\theta/2)} = 1$ and
$\sin{(\theta/2)}*e^{i\varphi} = 0$.

If $\cos\left( \frac{\theta}{2} \right) = 1$

-   $\left( \frac{\theta}{2} \right) = 0$

-   $\theta = 0$

If $\theta = 0$, then $\sin{(\theta/2)}*e^{i\varphi}$ becomes 0
irrespective of the value of $\varphi$.

This means that $|\left. \ 1 \right\rangle$ is represented as the north
pole of the Bloch Sphere.

**For**
$\left| \left. \ \mathbf{\psi} \right\rangle\mathbf{=} \right|\left. \ \mathbf{1} \right\rangle$**:**

$$\left| \left. \ 1 \right\rangle = \cos{(\theta/2)} \right|\left. \ 0 \right\rangle + \sin{(\theta/2)}*e^{i\varphi}|\left. \ 1 \right\rangle$$

Which means $\cos{(\theta/2)} = 0$ and
$\sin{(\theta/2)}*e^{i\varphi} = 1$.

If $\cos\left( \frac{\theta}{2} \right) = 0$

-   $\left( \frac{\theta}{2} \right) = 90{^\circ}$

-   $\theta = 180{^\circ}$

If $\theta = 180{^\circ}$, $\sin{(180/2)}*e^{i\varphi} = 1$ becomes
$e^{i\varphi} = 1$, which means $\varphi = 0$.

This represents the point in the south pole of the Bloch Sphere.

![](media/image11.png){width="3.088888888888889in"
height="3.213888888888889in"}

Now, it must be clear to the reader why we used $\theta = 2x$ in the
earlier derivation; this is to ensure that we get
$|\left. \ 0 \right\rangle$ and $|\left. \ 1 \right\rangle$ in the
north-pole and south-pole respectively.

**For**
$\left| \left. \ \mathbf{\psi} \right\rangle\mathbf{= H(} \right|\left. \ \mathbf{0} \right\rangle\mathbf{)}$**:**

$H(|\left. \ 0 \right\rangle)$ =
$\left( \frac{|\left. \ 0 \right\rangle}{\sqrt{2}} + \frac{|\left. \ 1 \right\rangle}{\sqrt{2}} \right)$
=
$\cos{(\theta/2)}|\left. \ 0 \right\rangle + \sin{(\theta/2)}*e^{i\varphi}|\left. \ 1 \right\rangle$

Which means $\cos{(\theta/2)} = \frac{1}{\sqrt{2}}$ and
$\sin{(\theta/2)}*e^{i\varphi} = \frac{1}{\sqrt{2}}$

If $\cos\left( \frac{\theta}{2} \right) = \frac{1}{\sqrt{2}}$

-   $\left( \frac{\theta}{2} \right) = 45{^\circ}$

-   $\theta = 90{^\circ}$

Now, $\sin{(90/2)}*e^{i\varphi} = \frac{1}{\sqrt{2}}$

-   $\frac{1}{\sqrt{2}}*e^{i\varphi} = \frac{1}{\sqrt{2}}$

-   $\varphi = 0$

This point lies on the $x$-axis towards the paper.

**For**
$\left| \left. \ \mathbf{\psi} \right\rangle\mathbf{= H(} \right|\left. \ \mathbf{1} \right\rangle\mathbf{)}$**:**

$H(|\left. \ 1 \right\rangle)$ =
$\left( \frac{|\left. \ 0 \right\rangle}{\sqrt{2}} - \frac{|\left. \ 1 \right\rangle}{\sqrt{2}} \right)$
=
$\cos{(\theta/2)}|\left. \ 0 \right\rangle + \sin{(\theta/2)}*e^{i\varphi}|\left. \ 1 \right\rangle$

Which means $\cos{(\theta/2)} = \frac{1}{\sqrt{2}}$ and
$\sin{(\theta/2)}*e^{i\varphi} = \frac{- 1}{\sqrt{2}}$

If $\cos\left( \frac{\theta}{2} \right) = \frac{1}{\sqrt{2}}$

-   $\left( \frac{\theta}{2} \right) = 45{^\circ}$

-   $\theta = 90{^\circ}$

Now, $\sin{(90/2)}*e^{i\varphi} = \frac{- 1}{\sqrt{2}}$

-   $\frac{1}{\sqrt{2}}*e^{i\varphi} = \frac{- 1}{\sqrt{2}}$

-   $e^{i\varphi} = - 1$

-   $\varphi = 180{^\circ}$

    (because from Euler's formula:
    $e^{i\varphi} = \cos{\varphi + isin\ \varphi}$; putting
    $\varphi = 180$ this becomes
    $\cos{180 + isin\ 180} = \  - 1 + i0 = \  - 1$)

This point lies on the $x$-axis away the paper.

![](media/image12.png){width="3.245138888888889in" height="3.125in"}

The gates, X, Y and Z can be visualized as rotating the Bloch sphere
around the corresponding axis by 180 degrees.

Let's say our qubit is in state $|\left. \ 0 \right\rangle$, i.e. it is
pointing to the north-pole. Following will be the Bloch Sphere
representation of it:

![](media/image13.png){width="2.8944444444444444in" height="3.0in"}

(Fig. 1.0)

Now, if we rotate the Bloch Sphere around the $x$-axis by 180${^\circ}$,
keeping the axes static, the state looks like this:

![](media/image14.png){width="2.890972222222222in"
height="2.995138888888889in"}

(Fig 1.1)

Which is $|\left. \ 1 \right\rangle$, and is correct because
$X\left( \  \middle| \left. \ 0 \right\rangle\  \right) = \ |\left. \ 1 \right\rangle$.
Now, if we rotate the Bloch Sphere around the $x$-axis by 180${^\circ}$
again, by keeping the axes static, we will get the state in Fig 1.0
again; this is also correct because applying $x$ gate twice is same as
applying $I$.

What happens if we rotate the Bloch Sphere in Fig 1.0 around the
$y$-axis by 180${^\circ}$? It will also result in the state shown in Fig
1.1. But what happens to $|\left. \ 0 \right\rangle$, when we actually
multiply with the $Y$ gate. Let's check it:

$Y(|\left. \ 0 \right\rangle)$ = $\begin{bmatrix}
0 & - i \\
i & 0 \\
\end{bmatrix}*\ \begin{bmatrix}
1 \\
0 \\
\end{bmatrix}$

= $\begin{bmatrix}
0 \\
i \\
\end{bmatrix}$

We got $\begin{bmatrix}
0 \\
i \\
\end{bmatrix}$, but 180${^\circ}$ rotation around $Y$-axis gave us
$|\left. \ 1 \right\rangle\text{\ i.e\ }\begin{bmatrix}
0 \\
1 \\
\end{bmatrix}$. This apparent discrepancy is because of they way we use
Bloch Sphere to represent the qubit. We proved earlier that, all the
qubits can be considered to be in the same state as long as they differ
only by a global phase. We can write $\begin{bmatrix}
0 \\
i \\
\end{bmatrix}$ as $\begin{bmatrix}
0 \\
e^{i\pi/2} \\
\end{bmatrix}$ (by using the Euler's Formula stated earlier). This can
be written as $\begin{bmatrix}
0{*e}^{i\pi/2} \\
{1*e}^{i\pi/2} \\
\end{bmatrix}$. Now, we can remove the global phase $e^{i\pi/2}$ which
will make the state $\begin{bmatrix}
0 \\
1 \\
\end{bmatrix}$ which represents the south pole.

Now, let's take the state in Fig 1.0 and rotate around the $Z$-axis by
180${^\circ}$. It must be obvious that, since the state is aligned with
the $Z$-axis, this rotation has no effect. Let's apply the $Z$-gate on
$|\left. \ 0 \right\rangle$:

$Z(|\left. \ 0 \right\rangle)$ = $\begin{bmatrix}
1 & 0 \\
0 & - 1 \\
\end{bmatrix}*\ \begin{bmatrix}
1 \\
0 \\
\end{bmatrix}$

= $\begin{bmatrix}
1 \\
0 \\
\end{bmatrix}$

We see that the values match.

Now, let's take the state in Fig 1.1 (i.e. $|\left. \ 1 \right\rangle)$,
and rotate around the $Z$-axis by 180${^\circ}$. As in the previous
case, the state will remain unchanged because it is already aligned with
the $Z$-axis. But, what happens if we apply the $Z$-gate on
$|\left. \ 1 \right\rangle$?

$Z(|\left. \ 1 \right\rangle)$ = $\begin{bmatrix}
1 & 0 \\
0 & - 1 \\
\end{bmatrix}*\ \begin{bmatrix}
0 \\
1 \\
\end{bmatrix}$

= $\begin{bmatrix}
0 \\
 - 1 \\
\end{bmatrix}$

Here we got $\begin{bmatrix}
0 \\
 - 1 \\
\end{bmatrix}$ instead of $\begin{bmatrix}
0 \\
1 \\
\end{bmatrix}$. We can prove that in the Bloch Sphere, both these states
represent the same point (the south pole) as follows:

$\begin{bmatrix}
0 \\
 - 1 \\
\end{bmatrix} = \begin{bmatrix}
0*e^{i\pi}\  \\
1{*e}^{i\pi} \\
\end{bmatrix}$ (using the Euler's formula)

=$\begin{bmatrix}
0\  \\
1 \\
\end{bmatrix}$ (removing the global phase $e^{i\pi}$)

Similarly, while representing in a Bloch Sphere, all the following
states are represented by the south-pole:

$\left| \left. \ 1 \right\rangle,\  - \left| \left. \ 1 \right\rangle,\ i \right|\left. \ 1 \right\rangle,\  - i \right|\left. \ 1 \right\rangle,\ (\frac{\sqrt{3}}{\sqrt{4}} + \frac{\sqrt{1}}{\sqrt{4}})|\left. \ 1 \right\rangle$
etc.

Similarly, infinitely many states can be represented as the north-pole
as follows:

$\left| \left. \ 0 \right\rangle,\  - \left| \left. \ 0 \right\rangle,\ i \right|\left. \ 0 \right\rangle,\  - i \right|\left. \ 0 \right\rangle,\ (\frac{\sqrt{3}}{\sqrt{4}} + \frac{\sqrt{1}}{\sqrt{4}})|\left. \ 0 \right\rangle$
etc.

Apart from 180${^\circ}$ rotation around any axis, we can rotate the
Bloch Sphere around these axes by any random angle.

Q\# defines the following rotations:

$R_{x}{\left( \theta \right) = \ e}^{- i{\theta/2\sigma}_{x}}$, where
$\sigma_{x} = Pauli\ X\ matrix$

$R_{y}{\left( \theta \right) = \ e}^{- i{\theta/2\sigma}_{y}}$, where
$\sigma_{y} = Pauli\ Y\ matrix$

$R_{z}{\left( \theta \right) = \ e}^{- i{\theta/2\sigma}_{z}}$, where
$\sigma_{z} = Pauli\ Z\ matrix$

Each rotation means, rotating the Bloch Sphere by the specified angle
around the specified axis in anti-clock wise direction.

Let's try to find the matrices for these rotations.

We know that:

$\text{\ e}^{x}$ = 1 + $x$ + $\frac{\text{\ x}^{2}}{2!}$ +
$\frac{\text{\ x}^{3}}{3!}$ + $\frac{\text{\ x}^{4}}{4!}$ ...

Similarly, we know that:

$cos(x)$ = 1 - $\frac{\text{\ x}^{2}}{2!}$ + $\frac{\text{\ x}^{4}}{4!}$
- ...

And:

$sin(x)$ = $x$ - $\frac{\text{\ x}^{3}}{3!}$ +
$\frac{\text{\ x}^{5}}{5!}$ - ...

(For the proof of the above expansions, Bing for Maclaurin expansion for
sin and cos.)

Now:

$\text{\ e}^{- i{\theta/2\sigma}_{x}} = \ $1 + $- i{\theta/2\sigma}_{x}$
+ $\frac{{\ ( - i{\theta/2\sigma}_{x})}^{2}}{2!}$ +
$\frac{{\ ( - i{\theta/2\sigma}_{x})}^{3}}{3!}$ +
$\frac{{\ ( - i{\theta/2\sigma}_{x})}^{4}}{4!}$ ...

= $\cos\left( \frac{\theta}{2} \right)*I$ -- i \*
$\sin\left( \frac{\theta}{2} \right)\ {*\sigma}_{x}$

(because $\sigma_{x}*\ \sigma_{x} = \ \begin{bmatrix}
0 & 1 \\
1 & 0 \\
\end{bmatrix}*\ \begin{bmatrix}
0 & 1 \\
1 & 0 \\
\end{bmatrix} = \ \begin{bmatrix}
1 & 0 \\
0 & 1 \\
\end{bmatrix} = I)$

Same expansion can be given for the remaining rotations also.

Let's find the matrices for these rotations:

$R_{x}{\left( \theta \right) = \ e}^{- i{\theta/2\sigma}_{x}} = \cos\left( \frac{\theta}{2} \right)*I$
-- i \* $\sin\left( \frac{\theta}{2} \right)\ {*\sigma}_{x}$

$= \cos\left( \frac{\theta}{2} \right)*\begin{bmatrix}
1 & 0 \\
0 & 1 \\
\end{bmatrix}$ -- i \*
$\sin\left( \frac{\theta}{2} \right)*\ \begin{bmatrix}
0 & 1 \\
1 & 0 \\
\end{bmatrix}$

$= \begin{bmatrix}
\cos\left( \frac{\theta}{2} \right) & 0 \\
0 & \cos\left( \frac{\theta}{2} \right) \\
\end{bmatrix}$ -- $\ \begin{bmatrix}
0 & \operatorname{i*sin}\left( \frac{\theta}{2} \right) \\
\operatorname{i*sin}\left( \frac{\theta}{2} \right) & 0 \\
\end{bmatrix}$

$$= \begin{bmatrix}
\cos\left( \frac{\theta}{2} \right) & - \operatorname{i*sin}\left( \frac{\theta}{2} \right) \\
\operatorname{-i*sin}\left( \frac{\theta}{2} \right) & \cos\left( \frac{\theta}{2} \right) \\
\end{bmatrix}$$

$R_{y}{\left( \theta \right) = \ e}^{- i{\theta/2\sigma}_{y}} = \cos\left( \frac{\theta}{2} \right)*I$
-- i \* $\sin\left( \frac{\theta}{2} \right)\ {*\sigma}_{y}$

$= \cos\left( \frac{\theta}{2} \right)*\begin{bmatrix}
1 & 0 \\
0 & 1 \\
\end{bmatrix}$ -- i \*
$\sin\left( \frac{\theta}{2} \right)*\ \begin{bmatrix}
0 & - i \\
i & 0 \\
\end{bmatrix}$

$= \begin{bmatrix}
\cos\left( \frac{\theta}{2} \right) & 0 \\
0 & \cos\left( \frac{\theta}{2} \right) \\
\end{bmatrix}$ -- $\ \begin{bmatrix}
0 & \sin\left( \frac{\theta}{2} \right) \\
\operatorname{-sin}\left( \frac{\theta}{2} \right) & 0 \\
\end{bmatrix}$

$$= \begin{bmatrix}
\cos\left( \frac{\theta}{2} \right) & - \sin\left( \frac{\theta}{2} \right) \\
\operatorname{\ sin}\left( \frac{\theta}{2} \right) & \cos\left( \frac{\theta}{2} \right) \\
\end{bmatrix}$$

$R_{z}{\left( \theta \right) = \ e}^{- i{\theta/2\sigma}_{z}} = \cos\left( \frac{\theta}{2} \right)*I$
-- i \* $\sin\left( \frac{\theta}{2} \right)\ {*\sigma}_{z}$

$= \cos\left( \frac{\theta}{2} \right)*\begin{bmatrix}
1 & 0 \\
0 & 1 \\
\end{bmatrix}$ -- i \*
$\sin\left( \frac{\theta}{2} \right)*\ \begin{bmatrix}
1 & 0 \\
0 & - 1 \\
\end{bmatrix}$

$= \begin{bmatrix}
\cos\left( \frac{\theta}{2} \right) & 0 \\
0 & \cos\left( \frac{\theta}{2} \right) \\
\end{bmatrix}$ -- $\ \begin{bmatrix}
i*\sin\left( \frac{\theta}{2} \right) & 0 \\
0 & - i*\sin\left( \frac{\theta}{2} \right) \\
\end{bmatrix}$

$= \begin{bmatrix}
\cos\left( \frac{\theta}{2} \right) - i*\sin\left( \frac{\theta}{2} \right) & 0 \\
0 & \cos{+ i*\sin\left( \frac{\theta}{2} \right)} \\
\end{bmatrix}$

> =$\begin{bmatrix}
> \text{\ e}^{- i\frac{\theta}{2}} & 0 \\
> 0 & \text{\ e}^{i\frac{\theta}{2}} \\
> \end{bmatrix}$ (from Euler's formula)

As you can see, unlike $R_{x}$ and $R_{y}$, $R_{z}$ doesn't change any
probabilities; it changes only the phase difference between the two
states by $\theta$; it decreases the phase of
$|\left. \ 0 \right\rangle$ by $\frac{\theta}{2}$ and increases the
phase of $|\left. \ 1 \right\rangle\ $by $\frac{\theta}{2}$. This is not
same as adding a global phase, because it is adding different phases to
each state.

Let's see how $R_{x}(\pi)$ (rotation around $x$-axis by 180${^\circ}$
(or $\pi\ radians)$) works:

$R_{x}(\pi)$ = $\begin{bmatrix}
\cos\left( \frac{\pi}{2} \right) & - \operatorname{i*sin}\left( \frac{\pi}{2} \right) \\
\operatorname{-i*sin}\left( \frac{\pi}{2} \right) & \cos\left( \frac{\pi}{2} \right) \\
\end{bmatrix}$

= $\begin{bmatrix}
0 & - i \\
 - i & 0 \\
\end{bmatrix}$

=$- i*\begin{bmatrix}
0 & 1 \\
1 & 0 \\
\end{bmatrix}$

=$\  - i*X$ (this is similar to applying the $X$ gate, because applying
the global phase of $- i$ can be ignored as proved earlier)

Same goes for the other rotations as follows:

$R_{y}(\pi)$ =$\begin{bmatrix}
\cos\left( \frac{\pi}{2} \right) & - \sin\left( \frac{\pi}{2} \right) \\
\operatorname{\ sin}\left( \frac{\pi}{2} \right) & \cos\left( \frac{\pi}{2} \right) \\
\end{bmatrix}$ = $\begin{bmatrix}
0 & - 1 \\
1 & 0 \\
\end{bmatrix}$ = -i \* $\begin{bmatrix}
0 & - i \\
i & 0 \\
\end{bmatrix}$ = $- i*Y$

$R_{z}(\pi)$=$\ \begin{bmatrix}
\text{\ e}^{- i\frac{\pi}{2}} & 0 \\
0 & \text{\ e}^{i\frac{\pi}{2}} \\
\end{bmatrix}$ = $\ \begin{bmatrix}
 - i & 0 \\
0 & i \\
\end{bmatrix}$ = -i \* $\begin{bmatrix}
1 & 0 \\
0 & - 1 \\
\end{bmatrix}$ = $- i*Z$

**\
**

$\mathbf{R}_{\mathbf{x}}$**:**

![](media/image15.png){width="4.84375in" height="2.49950021872266in"}

$\mathbf{R}_{\mathbf{y}}$**:**

![](media/image16.png){width="5.03125in" height="2.3846391076115485in"}

$\mathbf{R}_{\mathbf{z}}$**:**

![](media/image17.png){width="5.015625546806649in"
height="2.16218394575678in"}

Q\# also provides a generic rotation operation R to which you can pass
any Pauli axis:

E.g.: R(PauliX, PI(), qubit). This is same as Rx(PI(), qubit).

To this R operation, we can pass PauliI to give a global phase as
follows:

$\text{\ e}^{- i{\theta/2\sigma}_{I}} = \cos\left( \frac{\theta}{2} \right)*I$
-- i \* $\sin\left( \frac{\theta}{2} \right)\ {*\sigma}_{I}$

> $= \cos\left( \frac{\theta}{2} \right)*\begin{bmatrix}
> 1 & 0 \\
> 0 & 1 \\
> \end{bmatrix}$ -- i \*
> $\sin\left( \frac{\theta}{2} \right)*\ \begin{bmatrix}
> 1 & 0 \\
> 0 & 1 \\
> \end{bmatrix}$
>
> =$\begin{bmatrix}
> \cos\left( \frac{\theta}{2} \right) - i\sin\left( \frac{\theta}{2} \right) & 0 \\
> 0 & \cos\left( \frac{\theta}{2} \right) - i\sin\left( \frac{\theta}{2} \right) \\
> \end{bmatrix}$
>
> =$\begin{bmatrix}
> \text{\ e}^{- i\frac{\theta}{2}} & 0 \\
> 0 & \text{\ e}^{- i\frac{\theta}{2}} \\
> \end{bmatrix}$ (from Euler's formula)

This operation adds a common phase to both the states; so, though
technically the qubit state is being changed, the point will not move on
the Bloch Sphere as there is no change in the phase difference.

Let's say we start with the qubit at $|\left. \ 0 \right\rangle$ and
want to give it some probability like (2/10) for
$|\left. \ 0 \right\rangle$ and (8/10) for $|\left. \ 1 \right\rangle$,
then we can use $R_{y}(\theta)$ by passing appropriate value for
$\theta$. Here the advantage is that we can do it by keeping the phase
as 0. We can use the following process to find $\theta$ for these
probabilities:

$Pr(|0\rangle) = \ $(2/10)

$Pr(|1\rangle) = \ $(8/10)

We can come up with infinite number of probability amplitudes to get
these probabilities. But, let's choose a qubit as follows:

$\frac{\sqrt{2}}{\sqrt{10}}|\left. \ 0 \right\rangle + \frac{\sqrt{8}}{\sqrt{10}}|\left. \ 1 \right\rangle$
=
$\cos{(\theta/2)}|\left. \ 0 \right\rangle + \sin{(\theta/2)}*e^{i\varphi}|\left. \ 1 \right\rangle$

-   $\operatorname{cos\ }{(\theta/2)} = \ \frac{\sqrt{2}}{\sqrt{10}}$

-   $\frac{\theta}{2} = \ \cos^{- 1}(\frac{\sqrt{2}}{\sqrt{10}})$

-   $\theta = \ {2*cos}^{- 1}\left( \frac{\sqrt{2}}{\sqrt{10}} \right)$

We can pass the $\theta$ obtained by the above calculation to the
$R_{y}$ operation to get the desired super position. To get the desired
phase you can use the $R_{z}$operation.

As you can observe, the $R_{x}\text{\ and\ }R_{y}$operations change the
probabilities, where as $R_{z}$ changes only the phase of the qubit.

In this blog we are covering qubits only in pure states; a qubit in a
mixed state will be represented by a point inside the Bloch Sphere and
will be covered in a later blog.

**\
**

**Sample Q\# code:**

DumpMachine("") will display the state of the current system. For a
single qubit system
($(a + ib)|\left. \ 0 \right\rangle + \ (c + id)|\left. \ 1 \right\rangle$),
the output will be as follows:

> **Ids: \[0;\]**
>
> **Wavefunction:**
>
> **0: a b**
>
> **1: c d**

**Driver.cs:**

using Microsoft.Quantum.Simulation.Core;

using Microsoft.Quantum.Simulation.Simulators;

using System;

namespace Quantum.DemoRotations2

{

class Driver

{

static void Main(string\[\] args)

{

using (var quantumSimulator = new QuantumSimulator())

{

var result = DemoRotations.Run(quantumSimulator).Result;

}

Console.WriteLine(\"Done\");

Console.ReadLine();

}

}

}

**Operation.qs:**

namespace Quantum.DemoRotations2

{

open Microsoft.Quantum.Primitive;

open Microsoft.Quantum.Canon;

open Microsoft.Quantum.Extensions.Diagnostics;

open Microsoft.Quantum.Extensions.Math;

operation DemoRotations () : ()

{

body

{

using(qubits = Qubit\[1\])

{

DumpMachine(\"\");

}

}

}

}

In this code, since we didn't perform any operation, the qubit will be
in the default $|\left. \ 0 \right\rangle$ state:

Ids: \[0;\]

Wavefunction:

0: 1 0

1: 0 0

**Further examples:**

**Code:**

X(qubits\[0\]);

DumpMachine(\"\");

**Output:**

Ids: \[0;\]

Wavefunction:

0: 0 0

1: 1 0

**Code:**

Rx(PI(), qubits\[0\]);

DumpMachine(\"\");

**Output:**

Ids: \[0;\]

Wavefunction:

0: 6.12323e-17(almost 0) 0

1: 0 -1

**Code:**

R(PauliX,PI(), qubits\[0\]);

DumpMachine(\"\");

**Output (same as above):**

Ids: \[0;\]

Wavefunction:

0: 6.12323e-17 0

1: 0 -1

**Code:**

H(qubits\[0\]);

DumpMachine(\"\");

**Output:**

Ids: \[0;\]

Wavefunction:

0: 0.707107 0

1: 0.707107 0

**Code:**

H(qubits\[0\]);

R(PauliI, PI(), qubits\[0\]);

**Output (similar to above, but phase of i added to both the states):**

Ids: \[0;\]

Wavefunction:

0: 4.32978e-17 (almost 0) -0.707107

1: 4.32978e-17 (almost 0) -0.707107

**Code:**

This program creates a qubit with the following probabilities:

$Pr(|0\rangle) = \ $(2/10)

$Pr(|1\rangle) = \ $(8/10)

body

{

mutable countZero = 0;

mutable countOne = 0;

mutable iterations = 1000;

using(qubits = Qubit\[1\])

{

for(i in 1..iterations)

{

let probabilityOfZero = 2.0/10.0;

let amplitudeOfZero = Sqrt(probabilityOfZero);

let angle = 2.0 \* ArcCos(amplitudeOfZero);

Ry(angle, qubits\[0\]);

let result = M(qubits\[0\]);

if(result == Zero)

{

set countZero = countZero + 1;

}

else

{

set countOne = countOne + 1;

}

ResetAll(qubits);

}

Message(\$\"countZero: {countZero}\");

Message(\$\"countOne: {countOne}\");

}

}

**Output:**

countZero: 205

countOne: 795
