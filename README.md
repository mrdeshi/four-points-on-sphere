## $Abstract$

This demonstration addresses the classic geometric probability problem of determining the likelihood that a tetrahedron formed by four randomly selected points on the surface of a sphere contains the sphere's center.The approach involves sequentially anchoring points and calculating the conditional probability for each new point. The first three points are anchored using spherical coordinates, with each new point's position constrained by the previously placed points. The crucial fourth step calculates the conditional probability that the fourth point falls within the hemisphere defined by the first three, which is the necessary condition for the tetrahedron to contain the center. The area of a spherical triangle, as given by **Girard's Theorem**, is used to express this probability in terms of the angles between the first three points. By combining the conditional probabilities of all four points and integrating over all possible configurations of the first three points, the proof concludes that the final probability is **1/8**.

## $Proof$

First we anchor the first point, since we can imagine the sphere to be movable vertically and horizontally, we can place it on the top. The probability to take a random point on a sphere is 1. So, for now,

$$
f(P_{1}) = 1
$$

then we anchor a second point, now we can move the sphere only horizontally, in order to have the two points aligned, now we have to decide the vertical distance from the first point, this create a dependent variable $\alpha$ witch range is from 0 to $\pi$. Then,

$$
f(P_{2}) = \frac{d\alpha r}{\pi r}
$$

then we anchor the third point, now we can't move the sphere anymore because we would create different configurations, we use 2 new variables $\theta$ from 0 to $\pi$ and $\phi$ from 0 to $2\pi$, since the circle passing through the first two points determine a symmetry the range of $\phi$ become from 0 to $\pi$. Now,

$$
f(P_{3}) =\frac{d\theta r}{\pi r}\cdot \frac{d\phi}{\pi r}
$$

The final step calculates the conditional probability that the fourth point falls within the hemisphere bounded by the plane of the first three points, which is the necessary condition for the tetrahedron to contain the center, that is the area of the hemisphere divided by the surface of the sphere:

$$\frac{A_{h}}{4\pi r^2}$$
-> Using Girard's Theorem: 
the area (T) of a spherical triangle, with interior angles a,b and c, is given by $T = r^2 (a + b + c - \pi)$.

We can easily see that a,b and c are respectively $\alpha$, $\theta$ and $\phi$.

So,
$$
f(P_{4})= \frac{r^2(\alpha + \theta + \phi - \pi)}{4\pi r^2}
$$

Now, since the events are independent we use the **multiplication rule of probability**. This rule is used to find the probability of multiple events happening in sequence.

$$p=f(P_{1} \cap P_{2} \cap P_{3} \cap P_{4})=\prod_{i=1}^{4}f(P_{i})
=f(P_{1}) \cdot f(P_{2})\cdot f(P_{3})\cdot f(P_{4})$$

Now we have that for four determined points in a sphere the probability that the tetrahedron contains the centre of the sphere is

$$
p_{1,2,3,4}=1\cdot \frac{d\alpha r}{\pi r}\cdot \frac{d\theta r}{\pi r} \frac{d\phi}{\pi r}\cdot \frac{r^2(\alpha + \theta + \phi -\pi)}{4\pi r^2}
= \frac{d\alpha}{\pi}\cdot \frac{d\theta}{\pi} \frac{d\phi}{\pi }\cdot \frac{(\alpha + \theta + \phi -\pi)}{4\pi }
$$

Now this isn't an interesting result as it's value is zero because the probability of a continuous random variable being equal to any **single, exact value** is always **zero**., but it would be much complete if we sum all the possible combinations of points by evaluating the triple integral

$$
\int_{0}^{\pi}  \,\int_{0}^{\pi}  \,\int_{0}^{\pi}  \, \frac{\alpha + \theta + \phi -\pi}{4\pi^4} d\alpha  d\theta  d\phi  =\frac{1}{8}
$$
