##Trend Classification Algorithm

###Description:

*PolyTrend classifies the trends into linear, quadratic, cubic, concealed and no-trend types. The "concealed trends" are those trends that possess quadratic or cubic forms, but the net change
from the start of the time period to the end of the time period hasn't been significant. The "no-trend" category includes simple linear trends with statistically in-significant slope coefficient.*

###Usage:

     PolyTrend(Y, alpha)
     
###Arguments:

&nbsp;&nbsp;**Y:** 
&nbsp;&nbsp;&nbsp;&nbsp;a vector of values corresponding to the trend or
&nbsp;&nbsp;&nbsp;&nbsp;de-seasonalised component of vegetation time series data.

&nbsp;&nbsp;**alpha:** 
&nbsp;&nbsp;&nbsp;&nbsp;the statistical significance level.

###Details:

&nbsp;&nbsp;&nbsp;&nbsp;An object of the class "PT" is a list including the trend type,
&nbsp;&nbsp;&nbsp;&nbsp;slope, direction, and statistical significance.

###Value:

&nbsp;&nbsp;**TrendType:** 
&nbsp;&nbsp;&nbsp;&nbsp;the trend type as a number, which can be -1, 0, 1, 2, or 3.
&nbsp;&nbsp;&nbsp;&nbsp;The values correspond to a concealed trend (-1), no trend
&nbsp;&nbsp;&nbsp;&nbsp;(0), linear trend (1), quadratic trend (2) or cubic trend
&nbsp;&nbsp;&nbsp;&nbsp;(3).

&nbsp;&nbsp;**Slope:** 
&nbsp;&nbsp;&nbsp;&nbsp;the linear slope value.

&nbsp;&nbsp;**Direction:**
&nbsp;&nbsp;&nbsp;&nbsp;the linear slope direction as a number, which can be 1 or
&nbsp;&nbsp;&nbsp;&nbsp;-1. The values correspond to increasing (1) or decreasing
&nbsp;&nbsp;&nbsp;&nbsp;direction (-1).

&nbsp;&nbsp;**Significance:** 
&nbsp;&nbsp;&nbsp;&nbsp;the slope significance as a number, which can be 1 or -1.
&nbsp;&nbsp;&nbsp;&nbsp;The values correspond to statistically significant (1) or
&nbsp;&nbsp;&nbsp;&nbsp;statistically in-significant (-1).

&nbsp;&nbsp;**PolynomialDegree:** 
&nbsp;&nbsp;&nbsp;&nbsp;the polynomial degree as a number, which can be 0, 1,
&nbsp;&nbsp;&nbsp;&nbsp;2, or 3. The values correspond to no-trend (0), linear (1),
&nbsp;&nbsp;&nbsp;&nbsp;quadratic (2), or cubic (3).

###Author(s):

     Sadegh Jamali, Hristo Tomov

###References:

*Jamali S, Seaquist J, Eklundh L, Ardö J (2014). Automated mapping of vegetation trends with polynomials using NDVI imagery over the Sahel. Remote Sensing of Environment, 141, 79-89.*
<http://dx.doi.org/10.1016/j.rse.2013.10.019>

*Tomov H (2016). Automated temporal NDVI analysis over the Middle East for the period 1982 – 2010.*
<http://lup.lub.lu.se/student-papers/record/8871893>

###Examples:
```R
     ### Following examples are taken from Fig. 3 in Jamali et al. 2014
     ### Examples of a cubic trend (Site 1 & Site 2)
     data(ex.a)
     data(ex.b)
     
     pt.a <- PolyTrend(ex.a, 0.05)
     plot(pt.a, fig.dates = c(1982:2006))
     
     pt.b <- PolyTrend(ex.b, 0.05)
     plot(pt.b, fig.dates = c(1982:2006))
     
     ### Examples of a concealed trend with cubic form (Site 3 & Site 4)
     data(ex.c)
     data(ex.d)
     
     pt.c <- PolyTrend(ex.c, 0.05)
     plot(pt.c, fig.dates = c(1982:2006))
     
     pt.d <- PolyTrend(ex.d, 0.05)
     plot(pt.d, fig.dates = c(1982:2006))
     
     ### Examples of a quadratic trend (Site 5 & Site 6)
     data(ex.e)
     data(ex.f)
     
     pt.e <- PolyTrend(ex.e, 0.05)
     plot(pt.e, fig.dates = c(1982:2006))
     
     pt.f <- PolyTrend(ex.f, 0.05)
     plot(pt.f, fig.dates = c(1982:2006))
     
     ### Examples of a concealed trend with quadratic form (Site 7 & Site 8)
     data(ex.g)
     data(ex.h)
     
     pt.g <- PolyTrend(ex.g, 0.05)
     plot(pt.g, fig.dates = c(1982:2006))
     
     pt.h <- PolyTrend(ex.h, 0.05)
     plot(pt.h, fig.dates = c(1982:2006))
     
     ### Examples of a linear trend (Site 9 & Site 10)
     data(ex.k)
     data(ex.m)
     
     pt.k <- PolyTrend(ex.k, 0.05)
     plot(pt.k, fig.dates = c(1982:2006))
     
     pt.m <- PolyTrend(ex.m, 0.05)
     plot(pt.m, fig.dates = c(1982:2006))
     
     ### Example of a no-trend (Site 11)
     data(ex.n)
     
     pt.n <- PolyTrend(ex.n, 0.05)
     plot(pt.n, fig.dates = c(1982:2006))
```
