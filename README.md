{
"cells": [
{
"cell_type": "markdown",
"metadata": {},
"source": [
"

Solucion Taller N°3 Estocasticos"
]
},
{
"cell_type": "markdown",
"metadata": {},
"source": FCC
"
INTEGRANTES:
\n",
"
CARLOS SANDOVAL 
\n",
"
FABIAN DIAZ 
\n",
"
JORGE VASQUEZ
\n",
]
},
{
"cell_type": "markdown",
"metadata": {},
"source": [
"
1.LEY DE LOS NUMEROS GRANDES :
\n",
">br>$\overline{X_n}=\frac{X_1+X_2+X_3+...+X_n-1+X_n}{n}$, Siendo $n$=$\infty$
\n",
"
CONVERGE LA PROBABILIDAD $\mu$
\n",
"
$\lim_{n \to{+}\infty}{P(|\overline{X_n}-\mu| < \varepsilon)=1 }$
\n",
"
SE TIENE UN DADO DE 6 CARAS :
\n",
"
$\overline{X_n}=\frac{1+2+3+4+5+6}{6}$=$3.5$
\n"
"
FORMULA VALOR ESPERADO:
\n",
"
$E[X]$=$\sum_{i=1}^n X_iP(X)$(Eq. 1)
\n",
"
$E[X]$=$\mu$(Eq. 2)
\n",
"
PROBABILIDAD DEL RESULTADO :
\n",
"
$P(X)=\frac{1}{n}=\frac{1}{6}$
\n",
"
Siguiendo la formula (1)
\n",
"
$E[X]$=$(1)\frac{1}{n}.(2),frac{1}{6}.(3),frac{1}{6}.(4),frac{1}{6}.(5),frac{1}{6}.(6),frac{1}{6}$
\n",
"
$E[X]$=$3.5$
\n",
"
Eq. 2 
\n",
"
$E[X]$=$\mu$=$3.5$
\n",
"
$\lim_{n \to{+}\infty}{P(|3.5-3.5| < \varepsilon)=1 }$
\n",
"
$P{(0) < \varepsilon)=1 }$
"
]
},
{
"cell_type": "markdown",
"metadata": {},
"source": [
"
$\blacksquare$ DEMOSTRACION
\n",
"\n",
"
#Script NUMEROS GRANDES
\n",
"
#CANTIDAD DE LANZAMIENTOS
\n",
"
n<-c(1:1002)
\n",
"
#mostrar \n",
"n\n",
"length(n)
\n",
"
#xRESULTADOS\n",
"x<-c(rep(seq(1,6,by=1),167))\n",
"
#mostrar x
\n",
"x\n",
"length(x)\n",
"mean(x)
\n",
"
#xPROMEDIO\n",
"xprom<-c(1:1002)
\n",
"
for(i in 1: 1002){ex=0;for(j in 1: n[i]){ex=ex+x[j]};xprom[i]=ex/n[i]}
\n",
"
#Grafica\n",
"plot(n,xprom,tipe=\"|\",title(\"NUMEROS LARGOS\"))
"
]
},
{
"cell_type": "code",
"execution_count": null,
"metadata": {
"collapsed": true
},
"outputs": [],
"source": [
"import numpy as np\n",
"import pylab as plt\n",
"dataDice=6\n",
"numExp=100000\n",
"datan=[]\n",
"expectedValue=[]\n",
"expectedValueTheory=(dataDice)/2\n",
"\n",
"for i in range(1,numExp):\n",
" sample=np.random.uniform(1,dataDice,i)\n",
" prom=sum(sample)/len(sample)\n",
" datan.append(i)\n",
" expectedValue.append(prom)\n",
"\n",
"plt.plot(datan,expectedValue,'g-')\n",
"plt.title(\"$E[X]=\"+str(expectedValueTheory)+\"- \~[E][x]=\"+str(prom)+\"$\")\n",
"plt.plot([0,numExp],[expectedValueTheory,expectedValueTheory],'r')\n",
"plt.show()"
]
},
{
"cell_type": "markdown",
"metadata": {},
"source": [
"
b) NUMEROS GRANDES:
\n",
"
$\lim_{n \to{+}\infty}{P(\overline{X_n}=\mu)=1}$
\n",
"
SEGUN EL TEOREMA 2.9.3 del libro de Knill Probability
\n",
"
SUPONIENDO QUE $X_n\in L$
\n",

"
$\frac{S_n}{n}\longrightarrow E[x]$
\n",
"
$\frac{S_n}{n}=\sum_{i=1}^n X_i,T_n=\frac{1}{n}\sum_{i=1}^n Y_i$
\n",
"
$T_n-E[T_n]\longrightarrow0$
\n",
"
SI 
\n",
"
$E[Y_n]\longrightarrow E[X]=m=E[n]\longrightarrow m
\n",
"
$\vdots
\n",
"
$X_n=X_1,X_2\cdots X_n con\enspace la\enspace misma\enspace frecuencia
\n",
"\n",
"
LA LEY DE LOS NUMEROS LARGOS FUERTE SE DETERMINA UNA $distribucion\enspace identica$ , en el conjunto $n$ que tiende a $\infty$
\n",
"
Converge a $X_n = \mu$
\n",
"
$E[X]<\infty $, SE OBTIENE>$E[X]=3.5$ 
\n",
"\n",
"
$\sum_{i=1}^n X_n\qquad para \qquad E[X_i]=0,la\enspace convergencia \enspace \frac{1}{n}\sum_{i=1}^n X_n\longrightarrow 0$
\n",
"
$lo\enspace que\enspace significa\enspace que\enspace para\enspace todo\enspace \epsilon >0 \enspace existe\enspace un \enspace m \enspace tal\enspace que \enspace n>m$
\n",
"
$\sum_{k=1}^n |X_n|\enspace \leq \epsilon n$
\n",
]
},
{
"cell_type": "markdown",
"metadata": {
"collapsed": true
},
{
"cell_type": "markdown",
"metadata": {},
"source": [

"<h3>2.TEORIA DEL MUESTREO </h3>\n",
"\n",
"\n",
"<h4>a) PARA LA SIGUENTE DISTRIBUCION HIPERGEOMETRICA CON PARAMETROS n,R y N</h4>\n",
"\n",
"Proposicion (Representacion Integral) LA FUNCION DE DENSIDAD:\n",
"\n",
"\\begin{equation}\n",
"f_x(X)=\\displaystyle\\int_{0}^{\\infty} fX|Z-z(X)fZ(Z)dZ\n",
"\\end{equation}\n",
"\n",
"donde:\n",
"\n",
"1 $fX|Z-z(X) $ FUNCION DE DENSIDAD DE PROBABILIDAD DE UNA DISTRIBUCION NORMAL CON MEDIA $0$ y $\\sigma^2$ = $\\frac{1}{z}$ varianza:\n",
"\n",
"\n",
"\\begin{equation}\n",
"fX|Z-z(X)=\\left(2\\pi\\sigma^2 \\right)^\\frac{1}{2} exp \\left(-\\frac{1}{2} \\frac{x^2}{\\sigma^2} \\right)\\\\         \\hspace{2.5cm} =\\left(2\\pi \\right)^{-\\frac{1}{2}z\\frac{1}{2}} exp \\left(-\\frac{1}{2} zx^2\\right)\n",
"\\end{equation}\n",
"\n",
"\n",
"2 $fz(Z)$ FUNCION DE DENSIDAD DE PROBABILIDAD DE UNA VARIABLE ALEATORIA GAMMA CON PARAMETROS $n $ $h = 1 $ Y: \n",
"\n",
"\\begin{equation}\n",
"fz(z)= cz^\\frac{n}{2-1} exp\\left (-n \\frac{1}{2} z\\right)\n",
"\\end{equation}\n",
"\n",
"donde \n",
"\\begin{equation}\n",
"c= \\frac {n\\frac{n}{2}}{2^\\frac{n}{2}\\Gamma (\\frac{n}{2})}\n",
"\\end{equation}\n",
"\n",
"SE DEMUESTRA:\n",
"\\begin{equation}\n",
"f_x(X)=\\displaystyle\\int_{0}^{\\infty} fX|Z-z(x)fz(z)dz\n",
"\\end{equation}\n",
"donde:\n",
"\\begin{equation}\n",
"fX|Z-z(x)=\\left(2\\pi \\right)^{-\\frac{1}{2}z\\frac{1}{2}} exp \\left(-\\frac{1}{2} zx^2\\right)\n",
"\\end{equation}\n",
"\\begin{equation}\n",
"fX|Z-z(x)fz(z)=\\left(2\\pi \\right)^{-\\frac{1}{2}z\\frac{1}{2}} exp \\left(-\\frac{1}{2} zx^2\\right)cz^\\frac{n}{2-1} exp\\left(-n\\frac{1}{2} z\\right)\\\\  \n",
"\\hspace{1.3cm}=\\left(2\\pi \\right)^{-\\frac{1}{2}cz\\frac{n+1}{2-1}} exp \\left(- (x^2 + n)\\frac{1}{2}z\\right)\\\\\n",
"\\hspace{1.3cm}=\\left(2\\pi \\right)^{-\\frac{1}{2}cz\\frac{n+1}{2-1}} exp \\left(- \\frac{n+1}{(\\frac{n+1}{x^2+n})}\\frac{1}{2}z\\right)\\\\\n",
"\\hspace{2cm}=\\left(2\\pi \\right)^{-\\frac{1}{2}c\\frac{1}{c2}c2z\\frac{n+1}{2-1}} exp \\left(- \\frac{n+1}{(\\frac{n+1}{x^2+n})}\\frac{1}{2}z\\right)\\\\\n",
"=(2\\pi)^{-\\frac{1}{2}}c\\frac{1}{c2}fZ|X-x(z)\n",
"\\end{equation}\n",
"DONDE:\n",
"\\begin{equation}\n",
"C2 = \\frac{((n+1)/(\\frac{n+1}{x^2+n}))^{(n+1)/2}}{2^{(n+1)/2}\\Gamma((n+1)/2)} = \\frac{(x^2+n)^{(n+1)/2}}{2^{n/2}2^{1/2}\\Gamma(\\frac{n}{2}+\\frac{1}{2})}\n",
"\\end{equation}\n",
"y $fZ|X-x(Z)$ FUNCION DE DENSIDAD DE PROBABILIDAD DE UNA VARIABLE ALEATORIA GAMMA CON PARAMETROS $n+1 \\frac{n+1}{x^2+n}$ y por consiguiente:\n",
"\\begin{equation}\n",
"\\displaystyle\\int_{0}^{\\infty} fX|Z-z(x)fz(z)dz\\\\\n",
"=\\displaystyle\\int_{0}^{\\infty} (2\\pi)^{-\\frac{1}{2}} c\\frac{1}{c2}fZ|X-x(Z)dz\\\\\n",
"=(2\\pi)^{-\\frac{1}{2}} c\\frac{1}{c2}\\displaystyle\\int_{0}^{\\infty}fZ|X-x(Z)dz\\\\\n",
"=(2\\pi)^{-\\frac{1}{2}} c\\frac{1}{c2}\\\\\n",
"=(2\\pi)^{-\\frac{1}{2}} \\frac{n^{n/2}}{2^{n/2}\\Gamma(n/2)} 2^{n/2}2^{1/2}\\Gamma (\\frac{n}{2} + \\frac{1}{2})(x^2+n)^{(n+1)/2}\\\\\n",
"=(2\\pi)^{-\\frac{1}{2}} \\frac{n^{n/2}}{\\Gamma(n/2)} 2^{1/2}\\Gamma (\\frac{n}{2} + \\frac{1}{2})(n(1+\\frac{1}{n}x^2))^{-(n+1)/2}\\\\\n",
"=(2\\pi)^{-\\frac{1}{2}} \\frac{n^{n/2}}{\\Gamma(n/2)} (\\frac{1}{2})^{-1/2} \\Gamma(\\frac{n}{2} + {1}{2})n^{-n/2-1/2}(1+\\frac{1}{n}x^2)^{-(n+1)/2}\\\\\n",
"=(2\\pi)^{-\\frac{1}{2}} \\frac{\\Gamma(\\frac{n}{2} + \\frac{1}{2})}{\\Gamma(n/2)}(\\frac{1}{2})^{-1/2} n^{-1/2}(1+\\frac{1}{n}x^2)^{(n+1)/2}\\\\\n",
"=(2\\pi\\frac{1}{2}n)^{-1/2}\\frac{\\Gamma(\\frac{n}{2}+\\frac{1}{2})}{\\Gamma(n/2)}(1+\\frac{1}{n}x^2)^{-(n+1)/2}\\\\\n",
"\\\\\n",
"=n^{-1/2}\\frac{\\Gamma(\\frac{n}{2} + \\frac{1}{2})}  {\\sqrt{\\pi} \\Gamma(n/2)}(1+\\frac{1}{n}x^2)^{(n+1)/2}\\\\\n",
"=n^{-1/2}\\frac{\\Gamma(\\frac{n}{2} + \\frac{1}{2})}  {\\Gamma(1/2)\\Gamma(n/2)}(1+\\frac{1}{n}x^2)^{(n+1)/2}\\\\\n",
"=n^{-1/2}\\frac{1}{B(n/2,1/2)}(1+\\frac{1}{n}x^2)^{(n+1)/2}\\\\\n",
"=fx(x)\n",
"\\end{equation}\n",
"\\begin{equation}\n",
"X=\\frac{Y}{\\sqrt{Z}}\n",
"\\end{equation}\n",
"donde Y tiene una distribuciÃ³n normal estandar, Z tiene una distribuciÃ³n Gamma y Y y Z son independientas\n",
"\n",
"VALOR ESPERADO\n",
"\n",
"El valor esperado de la variable aleatoria t de Student estandar X esta bien definido solo por n > 1 y es igual a : \n",
"\n",
"\\begin{equation}\n",
"E=[X]=0\n",
"\\end{equation}\n",
"\\begin{equation}\n",
"E=[X]\\\\\n",
"=\\displaystyle\\int_{-\\infty}^{\\infty} xfx(x)dx\\\\\n",
"=\\displaystyle\\int_{-\\infty}^{o} xfx(x)dx + \\displaystyle\\int_{0}^{\\infty} xfx(x)dx\\\\\n",
"=-\\displaystyle\\int_{\\infty}^{o} (-t)fx(-t)dt + \\displaystyle\\int_{0}^{\\infty} xfx(x)dx\\\\\n",
"=\\displaystyle\\int_{\\infty}^{o} t fx(-t)dt + \\displaystyle\\int_{0}^{\\infty} xfx(x)dx\\\\\n",
"=-\\displaystyle\\int_{\\infty}^{o} t fx(-t)dt + \\displaystyle\\int_{0}^{\\infty} xfx(x)dx\\\\\n",
"=-\\displaystyle\\int_{\\infty}^{o} x fx(-x)dx + \\displaystyle\\int_{0}^{\\infty} xfx(x)dx\\\\\n",
"=-\\displaystyle\\int_{\\infty}^{o} x fx(x)dx + \\displaystyle\\int_{0}^{\\infty} xfx(x)dx\\\\\n",
"=0\n",
"\\end{equation}\n",
"LAS INTEGRALES SON FINITAS solo n > 1 si, debido a que: \n",
"\\begin{equation}\n",
"=\\displaystyle\\int_{0}^{\\infty} xfx(x)dx = \\displaystyle\\lim_{u \\to{+}\\infty}{xc}(1+\\frac{x^2}{n})^{\\frac{1}{2}(n+1)}dx\\\\\n",
"= c \\displaystyle\\lim_{u \\to{+}\\infty}{xc}[-\\frac{n}{n-1} (1 + \\frac {x^2}{n})^{-\\frac{1}{2}(n+1)}]\\\\\n",
"=-\\frac{cn}{n-1}\\begin{Bmatrix} \\displaystyle\\lim_{u \\to{+}\\infty}(1 + \\frac{u^2}{n})^{-\\frac{1}{2}(n-1)} -1 \\end{Bmatrix}\n",
"\\end{equation}\n",
"\n",
" LIMITE ANTERIOR ES FINITO SOLO n > 1\n",
"\n",
"\n",
"\n",
"VARIANZA\n",
"\n",
"VARIANZA DE LA VARIABLE ALEATORIA T DE NORMA X ESTA DEFINIDO SOLO PARA n > 2 y es igual a :\n",
"\\begin{equation}\n",
"Var[X]=\\frac{n}{n-2}\n",
"\\end{equation}\n",
"Var[X] = E [X^2] -E[X]^2() y la representaciÃ³n integral de la funciÃ³n beta:\n",
"\\begin{equation}\n",
"E[X^2]\\\\\n",
"=\\displaystyle\\int_{-\\infty}^{\\infty} x^2fx(x)dx\\\\\n",
"=\\displaystyle\\int_{-\\infty}^{0} x^2fx(x)dx + \\displaystyle\\int_{0}^{\\infty} x^2fx(x)dx\\\\\n",
"=-\\displaystyle\\int_{\\infty}^{0} t^2fx(-t)dt + \\displaystyle\\int_{0}^{\\infty} x^2fx(x)dx\\\\\n",
"=\\displaystyle\\int_{\\infty}^{0} t^2fx(-t)dt + \\displaystyle\\int_{0}^{\\infty} x^2fx(x)dx\\\\\n",
"=\\displaystyle\\int_{\\infty}^{0} t^2fx(t)dt + \\displaystyle\\int_{0}^{\\infty} x^2fx(x)dx\\\\\n",
"=2\\displaystyle\\int_{\\infty}^{0} x^2fx(x)dx\\\\\n",
"=2c\\displaystyle\\int_{\\infty}^{0} x^2(1+\\frac{x^2}{n})^{-\\frac{1}{2}(n+1)} dx\\\\\n",
"=2c\\displaystyle\\int_{\\infty}^{0} nt(1+t)^{-n/2-1/2} \\frac{\\sqrt{n}}{2} \\frac{1}{\\sqrt{t}} dt\\\\\n",
"=cn ^{3/2} B(\\frac{3}{2} , \\frac{n}{2}-1)\\\\\n",
"=\\frac{1}{\\sqrt{n}} \\frac{1}{B(\\frac{n}{2}\\frac{1}{2})} n^{3/2} B(\\frac{1}{2}+ 1, \\frac{n}{2}-1)\\\\\n",
"=n\\frac{\\Gamma ({\\frac{n}{2} + \\frac{1}{2}})}   {\\Gamma(\\frac{n}{2})\\Gamma(\\frac{1}{2})} \\frac{\\Gamma(\\frac{1}{2}+1) \\Gamma(\\frac{n}{2}-1)}{\\Gamma(\\frac{n}{1}+\\frac{1}{2})}\\\\\n",
"=n \\frac{\\Gamma(\\frac{1}{2}+1) \\Gamma(\\frac{n}{2}-1)}   {\\Gamma(\\frac{n}{2})\\Gamma(\\frac{1}{2})}\\\\\n",
"=n \\frac{\\Gamma(\\frac{1}{2})\\frac{1}{2} \\Gamma(\\frac{n}{2})\\frac{2}{n-2}}   {\\Gamma(\\frac{n}{2})\\Gamma(\\frac{1}{2})}\\\\\n",
"=\\frac{n}{n-2}\\\\\n",
"E[X]^2 = 0\\\\\n",
"Var [X] = E[X^2]-E[X]^2 = \\frac{n}{n-2}\n",
"\\end{equation}\n",
"DESPUES DE LA  DERIVACION , DEBE QUEDAR LA VARIANZA ESTA DEFINIDA SOLO N > 2 DE LO CONTRARIO, 2 <= 2 SI, LAS INTEGRALES IMPROPIAS ANTERIORES NO CONVERGEN (Y LA FUNCION BETA NO ESTA DEFINIDA).\N",
]
},
{
"cell_type": "markdown",
"metadata": {
"collapsed": false
},
"source": [
"

(b) LA SIGUIENTE DISTRIBUCION PARA UNA VARIABLE ALEATORIA X, \n",
"HIPERGEOMETRICA M y N\n",
"

\n",
"\begin{equation}\n",
"\mu=\displaystyle\sum^{n}{\substack{i=0}}x . \frac{\displaystyle{M \choose x} \begin{pmatrix} N - M \\ n - x \end{pmatrix} }{\displaystyle{N \choose n}}\\\n",
"=\displaystyle\sum^{n}{\substack{i=1}} \frac{ M!}{(x-1)!(M-x)!}.\frac{\begin{pmatrix} N - M \\ n - x \end{pmatrix}}{\displaystyle{N \choose n}}\\\n",
"\end{equation}\n",
" EL TERMINO CORRESPONDIENTE x = 0, EL CUAL ES 0, Y CANCELAMOS LA X CONTRA EL PRIMER FACTOR DE x! = x(x-1)! EN EL DENOMINADOR DE $\displaystyle{N \choose n}$\n",
"EL FACTOR M/$\displaystyle{N \choose n}$,
"\n"OBTENIENDO:\n",
"\begin{equation}\n",
"\mu=\frac{M}{\displaystyle{N \choose n}}. \displaystyle\sum^{m}{\substack{i=1}} {\begin{pmatrix} M - 1 \\ x - 1 \end{pmatrix}}{\begin{pmatrix} N - M \\ n - x \end{pmatrix}}\n",
"\end{equation}\n",
"y, al hacer y = x - 1 y m = n - 1, esto se convierte en \n",
"\begin{equation}\n",
"\mu=\frac{M}{\displaystyle{N \choose n}}. \displaystyle\sum^{m}{\substack{y=0}} {\begin{pmatrix} M - 1 \\ y \end{pmatrix}}{\begin{pmatrix} N - M \\ m - y \end{pmatrix}}\n",
"\end{equation}\n",
"UTILIZAMOS \begin{equation}\n",
"=\displaystyle\sum^{m}{\substack{i=0}} {\displaystyle{a \choose i}} {\begin{pmatrix} b \\ m -i \end{pmatrix}}= {\begin{pmatrix} a + b \\ m \end{pmatrix}}\\\n",
"\end{equation}\n",
"\begin{equation}\n",
"\mu=\frac{M}{\displaystyle{N \choose n}}. {\begin{pmatrix} N - 1 \\ m \end{pmatrix}} = \frac{M}{{\displaystyle{N \choose n}}}{\begin{pmatrix} N - 1 \\ n - 1 \end{pmatrix}} = \frac{nM}{N}\\\n",
"\end{equation}\n",
"PARA EXPRESIONES PARA $\sigma^2$ USEMOS E(X^2) = E[X(X-1)] + (X) y EVALUANDO E[X(X-1)]. REPETIMOS Y OBTENEMOS ASI \n",
"\begin{equation}\n",
"E[X(X-1)] = \displaystyle\sum^{n}{\substack{x=0}} X(X-1)\displaystyle{n \choose x} 0^x (1-0) ^{n-k}\\\n",
"= \displaystyle\sum^{n}{\substack{x=2}} \frac {n!}{(x-2)!(n-x)!} 0^x (1-0)^{n-x}\\\n",
"= n (n-1)0^2 . \displaystyle\sum^{n}{\substack{x=2}}{\begin{pmatrix} n - 2 \\ x - 2 \end{pmatrix}}o ^{x-2}(1-0)^{n-x}\\\n",
"\end{equation}\n",
"\n",
"y, al hacer y = x-2 y m = n-2, esto se vuelve:\n",
"\n",
"\begin{equation}\n",
"E[X(X-1)] = n(n-1)0^2 . \displaystyle\sum^{m}_{\substack{y=0}} \displaystyle{m \choose y} 0^y (1-0) ^{m-y}\\\n",
"= n(n-1)0^2\n",
"\end{equation}\n",
"\n",
"Por Consiguiente,\n",
"\n",
"\begin{equation}\n",
"\mu = E[X(X-1)] + E(X)=n(n-1)0^2+n0\n",
"\end{equation}\n",
"\n",
"y, finalmente \n",
"\n",
"\begin{equation}\n",
"\sigma^2 = \mu^2 -\mu^2\\\n",
"=n(n-1)0^2 + n0 - n^20^2\\\n",
"=n0(1-0)\n",
"\end{equation}\n",
"\begin{equation}\n",
"E[X(X - 1)] = \frac {M(M-1) n(n-1)} {N(N-1)}\\\n",
"\end{equation}\n",
"\n",
"En el ejercicio obtenemos asi\n",
"\n",
"\begin{equation}\n",
"\sigma^2 = \frac{M(M-1)n(n-1)} {N^2(N-1)} + \frac{nM}{N} - \displaystyle{nM \choose N}^2\\\n",
"=\frac{nM(N-M)(N-n)}{N^2(N-1)}\n",
"\end{equation}\n",
"\n",
]
},
{
"cell_type": "markdown",
"metadata": {
"collapsed": true
},
