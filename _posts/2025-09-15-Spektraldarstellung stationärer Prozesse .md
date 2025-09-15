### Spektraldarstellung stationärer Prozesse  
### 平稳过程之谱表  

Sei $u(t)$ ein stationärer Prozess mit verschwindendem Mittelwert (falls $\overline{u(t)}\neq 0$, ersetzt man $u(t)$ durch $u(t)-\overline{u(t)}$).  
设 $u(t)$ 为平稳过程，均值为零（若 $\overline{u(t)}\neq 0$，则以 $u(t)-\overline{u(t)}$ 代之）。  

Das zentrale Merkmal eines stationären Prozesses ist: die Korrelationsfunktion $B(t_1,t_2)=\overline{u^*(t_1)u(t_2)}$ hängt nur von der Zeitdifferenz $\tau=t_2-t_1$ ab.  
平稳过程之要者：相关函数 $B(t_1,t_2)=\overline{u^*(t_1)u(t_2)}$ 惟系乎时差 $\tau=t_2-t_1$。  

Zur Motivation betrachte man die endliche Summe  
为明其理，观有限和  

\[
u(t)=\sum_{k=1}^n Z_k e^{i\omega_k t},
\]  

mit unkorrelierten komplexen Zufallsvariablen $Z_k$, die $\overline{Z_k}=0$ und $\overline{Z_k^*Z_l}=0$ für $k\neq l$ erfüllen.  
其中 $Z_k$ 为复随机变量，不相相关，且 $\overline{Z_k}=0$，又 $\overline{Z_k^*Z_l}=0$ 若 $k\neq l$。  

Dann gilt für die Korrelationsfunktion  
则相关函数为  

\[
B(\tau)=\sum_{k=1}^n F_k e^{i\omega_k \tau}, \qquad F_k=\overline{|Z_k|^2}\geq 0,
\]  

und der Prozess ist stationär.  
于是此过程平稳矣。  

Falls $n=2m$ und die Terme paarweise konjugiert sind, wird $u(t)$ reell, und man kann schreiben  
若 $n=2m$，项成共轭，则 $u(t)$ 实，可书为  

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
此即谐振子叠加之象。  

Für den allgemeinen Fall geht man zum Limes $n\to\infty$, wobei die Frequenzen kontinuierlich werden. Definiert man  
若论其普遍，当 $n\to\infty$，频率连属。乃定义  

\[
Z(\omega)=\sum_{\omega_k<\omega}Z_k,
\]  

so erhält man die Unkorreliertheitsbedingung  
则得不相关之条件  

\[
\overline{\big(Z^*(\omega^{(2)})-Z^*(\omega^{(1)})\big)\big(Z(\omega^{(4)})-Z(\omega^{(3)})\big)}=0,
\]  

und schließlich die Kolmogorov–Cramér-Spektraldarstellung  
遂成 Kolmogorov–Cramér 谱表：  

\[
u(t)=\int_{-\infty}^\infty e^{i\omega t}\,dZ(\omega).
\]  

Dieses Integral ist im quadratischen Mittel als Fourier–Stieltjes-Integral zu verstehen.  
此积分当以均方义，解作 Fourier–Stieltjes 之积分。  

Die Umkehrformel lautet  
反演公式云  

\[
Z(\omega)=\lim_{T\to\infty}\frac{1}{2\pi}\int_{-T}^T \frac{e^{-i\omega t}-1}{-it}\,u(t)\,dt+\text{Konst.},
\]  

und für reale Prozesse gilt $dZ(-\omega)=dZ^*(\omega)$.  
若过程实，则有 $dZ(-\omega)=dZ^*(\omega)$。  

Experimentell lässt sich dies durch Filter interpretieren: ein Bandpass mit $\Delta\omega=[\omega_1,\omega_2]$ liefert  
实验上可由滤波器释之：带通 $\Delta\omega=[\omega_1,\omega_2]$ 所出为  

\[
u(\Delta\omega,t)=2\Re\int_{\Delta\omega} e^{i\omega t}\,dZ(\omega),
\]  

und die mittlere Energie  
其平均能量为  

\[
\overline{[u(\Delta\omega,t)]^2}=2\overline{|Z(\Delta\omega)|^2}.
\]  

Man definiert die Spektraldichte $F(\omega)$ durch  
由是谱密度 $F(\omega)$ 定义为  

\[
\overline{|Z(\Delta\omega)|^2}=\int_{\Delta\omega}F(\omega)\,d\omega,
\]  

und setzt oft $E(\omega)=2F(\omega)$ für $\omega\geq 0$.  
常取 $E(\omega)=2F(\omega)$，其域 $\omega\geq 0$。  

Damit folgt  
于是得  

\[
\overline{|dZ(\omega)|^2}=F(\omega)\,d\omega=\tfrac12 E(\omega)\,d\omega,
\]  

sowie die orthogonale Inkrementalbedingung  
及不相关增量之式  

\[
\overline{dZ^*(\omega)\,dZ(\omega_1)}=\delta(\omega-\omega_1)F(\omega)\,d\omega\,d\omega_1.
\]  

Die Korrelationsfunktion ist Fourier-Transformierte der Spektraldichte:  
相关函数即谱密度之傅里叶变换：  

\[
B(\tau)=\int_{-\infty}^\infty e^{i\omega\tau}F(\omega)\,d\omega
=\int_0^\infty \cos(\omega\tau)E(\omega)\,d\omega,
\]  

und umgekehrt  
其逆则为  

\[
F(\omega)=\frac{1}{2\pi}\int_{-\infty}^\infty e^{-i\omega\tau}B(\tau)\,d\tau,\qquad
E(\omega)=\frac{2}{\pi}\int_0^\infty \cos(\omega\tau)B(\tau)\,d\tau.
\]  

Insbesondere gilt bei $\tau=0$:  
尤其当 $\tau=0$：  

\[
B(0)=\int_{-\infty}^\infty F(\omega)\,d\omega=\int_0^\infty E(\omega)\,d\omega,
\]  

was besagt, dass die Gesamtenergie die Summe der spektralen Anteile ist.  
谓过程总能量，即各谱分量能量之和也。  
