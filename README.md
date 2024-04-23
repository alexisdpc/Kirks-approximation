# Kirk's approximation for pricing Spread Options

We overview and implement Kirk's approximation to price the spead option on two futures contracts.

The payoff of a spread option on two futures contracts is given by
$$c_T =  {\rm max}[0,F_1-F_2-K]  $$
where $F_1$ and $F_2$ are the prices of the future contracts and $K$ is a constant spread. Let's say you are an oil refinery then your profit depends on the difference in price between crude oil and heating oil, so you'lll be interested in spread options with these two as the underlying. <kbd>like</kbd> 

In Kirk's approximation we take $Z(T)=F_2(T)+K$ to have a lognormal distribution with initial value $Z(0) = F_2+Ke^{-rT}$.\
The volatility for $Z$ is value wieghted  using the relative proportions for the positions:
$$\sigma_Z = \frac{F_2}{F_2+Ke^{-rT}} \sigma_2 $$


Lets' take the generalized Black-Scholes equation with
$$S= F_1 \hspace{1cm} {\rm Strike} = F_2+K$$

from which we obtain the value of the call
$$c= (F_2+K) e^{-rt}[F \, N(d_1) - N(d_2)]$$
where 
$$d_1 = \frac{\ln F + \sigma^2T/2 }{\sigma \sqrt{T}}  \hspace{1cm} d_2 = d_1 - \sigma \sqrt{T}$$
and 
$$F=\frac{F_1}{F_2+K}$$ 
The volatility of $F$ can be approximated as 
$$\sigma = \sqrt{\sigma_1^2+ \left(\frac{\sigma_2 F_2}{F_2+K}\right)^2- \frac{2 \, \rho \, \sigma_1 \sigma_2 F_2}{F_2+K}} $$
where $\rho$ is the correlation between the two futures contracts. Kirk's approoximation works for small $K$.

K}} $$
where $\rho$ is the correlation between the two futures contracts. Kirk's approoximation works for small $K$.

![image](https://github.com/alexisdpc/Kirks-approximation/assets/124795834/f7292ffd-d914-47c6-a262-1fc7bbd46568) ![image](https://github.com/alexisdpc/Kirks-approximation/assets/124795834/5e387923-4513-4ed0-a00f-a86f0b3af805)



![image](https://github.com/alexisdpc/Kirks-approximation/assets/124795834/6d16a2b7-5f2b-4c6d-a360-4aa8fffdcaa4)

