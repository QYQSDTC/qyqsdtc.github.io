---
title: Can We believe the precision of DM index?
date: 2017-11-13 12:26:37
comment: true
tags: [KIAA Intern]
---
# Can We believe the precision of DM index measurements?
## Statistical Model
![IMG_6950]({{site.baseurl}}/assets/img/IMG_6950.jpg)

![IMG_6951]({{site.baseurl}}/assets/img/IMG_6951.jpg)



The derivative part is rather easy to deal with, but the summation part is rather difficult. Under Professor Lee's conduct, we transfer the summation into integrate for t and f. We calculate the integrate with t first and it will simplify the integration dramatically.
## Integration Calculate
First let's calculate the Gaussian Integral:
$$\int_0^{\infty} e^{-(\frac{t_i-\alpha f_j^{-2\beta}}{\omega})^2}dt = \frac{1}{2}\sqrt{\pi} \omega $$
Now let's see the first two integration, we can get its value just by a glance of it, for its even or odd quality, of course, it equals $0$.
Now the third one, we can use $x=t-\alpha f^{-2\beta}_j$, so we get
$$\int_0^\infty x^2e^{-\frac{x^2}{\omega ^2}}dx$$
through integration by parts we get
$$-\frac{\omega ^2}{2}x^2e^{-\frac{x^2}{\omega ^2}}|_0^{\infty}+\omega ^2 \int_0^{\infty}e^{-\frac{x^2}{\omega ^2}}dx$$
it is obviously the first part is $0$ and the second is $\frac{1}{2}\sqrt{\pi}\omega ^3$
we ignore the constant and $f$ parts while do this integration, then let's plus these parts we get
$$\frac{f^{-2\beta}}{\omega ^4\Delta T}*\frac{1}{2}\sqrt{\pi}\omega ^3$$
Now let's integrate $f $ from $f_l$ to $f_h$
$$\int_{f_l}^{f_h}\frac{f^{-2\beta}}{\omega ^4\Delta T}*\frac{1}{2}\sqrt{\pi}\omega ^3df$$
it's easy to compute, the Gaussian Integration dramatically simplify the integration. It is similar for the upcoming summations.



