# Kirk's approximation for pricing Spread Options

The payoff of a spread option on two futures contracts is given by
<div align="center">
<table>
<tbody>
<td align="center">
<img width="20" height="0"><br>
  $$c_T = {\rm max}[0,F_1-F_2-K]$$
<img width="20" height="0">
</td>
</tbody>
</table>
</div>

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
where $\rho$ is the correlation between the two futures contracts. 

> [!WARNING]  
>  Kirk's approoximation works for small $K$.

## Delta
We can have either Delta with respect to $F_1$:
$$\Delta_1 = \frac{\partial c}{\partial F_1} = e^{-rT} N(d_1) $$
or with respect to $F_2$:
$$\Delta_2 = \frac{\partial c}{\partial F_2} = e^{-rT} \left[ -N(d_2) +(F_2+K) e^{-d_2^2/2} \sqrt{T}  \frac{\partial \sigma}{\partial F_2} \right]$$
and we have that 
$$ \frac{\partial \sigma}{\partial F_2} = \frac{ \sigma_2 K (\beta - \rho \sigma_1)  }{ \sigma (F_2+K)^2 } $$
where
$$\beta =\frac{\sigma_2 F_2}{F_2+K} $$

![image](https://github.com/alexisdpc/Kirks-approximation/assets/124795834/71cbc4e6-b912-4928-bae7-08487388fe09)![image](https://github.com/alexisdpc/Kirks-approximation/assets/124795834/11211df1-50ff-4639-9452-3db921fca55c)

## Vega
![image](https://github.com/alexisdpc/Kirks-approximation/assets/124795834/a2ab53e1-1aee-4803-98db-1982a47bfc44)



<p align="center">
  <img width="10" height="5" src="https://github.com/alexisdpc/Kirks-approximation/assets/124795834/6d16a2b7-5f2b-4c6d-a360-4aa8fffdcaa4">
</p>



