### Spektraldarstellung stationärer Prozesse  
### 平稳过程的谱表示  

Sei $u(t)$ ein stationärer Prozess mit verschwindendem Mittelwert (falls $\overline{u(t)}\neq 0$, ersetzt man $u(t)$ durch $u(t)-\overline{u(t)}$).  
设 $u(t)$ 为零均值平稳过程（若 $\overline{u(t)}\neq 0$，则以 $u(t)-\overline{u(t)}$ 代替即可）。  

Das zentrale Merkmal eines stationären Prozesses ist: die Korrelationsfunktion $B(t_1,t_2)=\overline{u^*(t_1)u(t_2)}$ hängt nur von der Zeitdifferenz $\tau=t_2-t_1$ ab.  
平稳过程的核心思想在于：其相关函数 $B(t_1,t_2)=\overline{u^*(t_1)u(t_2)}$ 仅依赖于时差 $\tau=t_2-t_1$。  

Zur Motivation betrachte man die endliche Summe  
为说明谱表示的由来，考虑有限和形式  

\[
u(t)=\sum_{k=1}^n Z_k e^{i\omega_k t},
\]  

mit unkorrelierten komplexen Zufallsvariablen $Z_k$, die $\overline{Z_k}=0$ und $\overline{Z_k^*Z_l}=0$ für $k\neq l$ erfüllen.  
其中 $Z_k$ 为不相关的复随机变量，满足 $\overline{Z_k}=0$，且 $\overline{Z_k^*Z_l}=0$（$k\neq l$）。  

Dann gilt für die Korrelationsfunktion  
相关函数计算得  

\[
B(\tau)=\sum_{k=1}^n F_k e^{i\omega_k \tau}, \qquad F_k=\overline{|Z_k|^2}\geq 0,
\]  

und der Prozess ist stationär.  
故过程平稳。  

Falls $n=2m$ und die Terme paarweise konjugiert sind, wird $u(t)$ reell, und man kann schreiben  
若 $n=2m$ 且项成共轭对，则 $u(t)$ 为实过程，可写作  

\[
u(t)=\sum_{k=1}^m\Big(Z_k^{(1)}\cos\omega_k t+Z_k^{(2)}\sin\omega_k t\Big)
=\sum_{k=1}^m W_k \cos(\omega_k t-\varphi_k),
\]  

mit Korrelationsfunktion  
其相关函数为  

\[
B(\tau)=\sum_{k=1}^m E_k \cos\omega_k \tau,\qquad E_k=\tfrac12\overline{W_k^2}.
\]  

Dies ist die anschauliche Darstellung als Überlagerung harmonischer Oszillatoren.  
此即谐振子叠加图像。  

Für den allgemeinen Fall geht man zum Limes $n\to\infty$, wobei die Frequenzen kontinuierlich werden. Definiert man  
推广至一般平稳过程需取极限 $n\to\infty$，频率趋于连续。定义  

\[
Z(\omega)=\sum_{\omega_k<\omega}Z_k,
\]  

so erhält man die Unkorreliertheitsbedingung  
则有不相关性条件  

\[
\overline{\big(Z^*(\omega^{(2)})-Z^*(\omega^{(1)})\big)\big(Z(\omega^{(4)})-Z(\omega^{(3)})\big)}=0,
\]  

und schließlich die Kolmogorov–Cramér-Spektraldarstellung  
由此得到 Kolmogorov–Cramér 谱表示：  

\[
u(t)=\int_{-\infty}^\infty e^{i\omega t}\,dZ(\omega).
\]  

Dieses Integral ist im quadratischen Mittel als Fourier–Stieltjes-Integral zu verstehen.  
这一积分应理解为均方意义下的 Fourier–Stieltjes 积分。  

Die Umkehrformel lautet  
反演公式为  

\[
Z(\omega)=\lim_{T\to\infty}\frac{1}{2\pi}\int_{-T}^T \frac{e^{-i\omega t}-1}{-it}\,u(t)\,dt+\text{Konst.},
\]  

und für reale Prozesse gilt $dZ(-\omega)=dZ^*(\omega)$.  
若 $u(t)$ 为实过程，则满足 $dZ(-\omega)=dZ^*(\omega)$。  

Experimentell lässt sich dies durch Filter interpretieren: ein Bandpass mit $\Delta\omega=[\omega_1,\omega_2]$ liefert  
物理意义来自滤波器实验：带通滤波输出  

\[
u(\Delta\omega,t)=2\Re\int_{\Delta\omega} e^{i\omega t}\,dZ(\omega),
\]  

und die mittlere Energie  
其平均能量为  

\[
\overline{[u(\Delta\omega,t)]^2}=2\overline{|Z(\Delta\omega)|^2}.
\]  

Man definiert die Spektraldichte $F(\omega)$ durch  
故定义谱密度函数 $F(\omega)$ 满足  

\[
\overline{|Z(\Delta\omega)|^2}=\int_{\Delta\omega}F(\omega)\,d\omega,
\]  

und setzt oft $E(\omega)=2F(\omega)$ für $\omega\geq 0$.  
并常用 $E(\omega)=2F(\omega)$（$\omega\geq 0$）。  

Damit folgt  
于是有  

\[
\overline{|dZ(\omega)|^2}=F(\omega)\,d\omega=\tfrac12 E(\omega)\,d\omega,
\]  

sowie die orthogonale Inkrementalbedingung  
以及不相关性条件  

\[
\overline{dZ^*(\omega)\,dZ(\omega_1)}=\delta(\omega-\omega_1)F(\omega)\,d\omega\,d\omega_1.
\]  

Die Korrelationsfunktion ist Fourier-Transformierte der Spektraldichte:  
因此相关函数为谱密度的傅里叶变换：  

\[
B(\tau)=\int_{-\infty}^\infty e^{i\omega\tau}F(\omega)\,d\omega
=\int_0^\infty \cos(\omega\tau)E(\omega)\,d\omega,
\]  

und umgekehrt  
而其逆变换为  

\[
F(\omega)=\frac{1}{2\pi}\int_{-\infty}^\infty e^{-i\omega\tau}B(\tau)\,d\tau,\qquad
E(\omega)=\frac{2}{\pi}\int_0^\infty \cos(\omega\tau)B(\tau)\,d\tau.
\]  

Insbesondere gilt bei $\tau=0$:  
特别地，当 $\tau=0$ 时：  

\[
B(0)=\int_{-\infty}^\infty F(\omega)\,d\omega=\int_0^\infty E(\omega)\,d\omega,
\]  

was besagt, dass die Gesamtenergie die Summe der spektralen Anteile ist.  
表明过程总能量是各个谱分量能量的总和。  
