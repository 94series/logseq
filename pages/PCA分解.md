- 下面是把上一条里的公式**改写为 Logseq 可直接渲染**的 Markdown/KaTeX 版本（复制到 Logseq 即可显示数学公式）。
- **数据/居中/协方差**
  
  X∈Rn×d,μ=1n∑i=1nxi,Xc=X−1μ⊤,S=1n−1Xc⊤XcX\in\mathbb{R}^{n\times d},\quad
  \mu=\frac{1}{n}\sum_{i=1}^n x_i,\quad
  X_c = X - \mathbf{1}\mu^\top,\quad
  S=\frac{1}{n-1}X_c^\top X_c
- **第一主成分：最大方差方向**
  
  v1=arg⁡max⁡∥v∥=1 v⊤Svv_1=\arg\max_{\lVert v\rVert=1}\ v^\top S v
- **拉格朗日与特征方程**
  
  L(v,λ)=v⊤Sv−λ (v⊤v−1),∇vL=0⇒Sv=λv\mathcal{L}(v,\lambda)=v^\top S v-\lambda\,(v^\top v-1),\quad
  \nabla_v\mathcal{L}=0\Rightarrow Sv=\lambda v
- **谱分解**
  
  S=VΛV⊤,V=[v1,…,vd] 正交,Λ=diag⁡(λ1≥⋯≥λd≥0)S=V\Lambda V^\top,\quad
  V=[v_1,\dots,v_d]\ \text{正交},\quad
  \Lambda=\operatorname{diag}(\lambda_1\ge\cdots\ge\lambda_d\ge0)
- **后续主成分（正交约束）**
  
  vj=arg⁡max⁡∥v∥=1, v⊥v1,…,vj−1v⊤Svv_j=\arg\max_{\lVert v\rVert=1,\ v\perp v_1,\dots,v_{j-1}} v^\top S v
- **得分（scores）与载荷（loadings）**
  
  Z=XcV,z(j)=Xcvj,1n−1Z⊤Z=ΛZ=X_c V,\quad z^{(j)}=X_c v_j,\quad
  \frac{1}{n-1}Z^\top Z=\Lambda
- **降维与重建（秩-$k$ 投影）**
  
  Vk=[v1,…,vk],Zk=XcVk,X^c=ZkVk⊤=XcVkVk⊤,X^=X^c+1μ⊤V_k=[v_1,\dots,v_k],\quad
  Z_k=X_c V_k,\quad
  \hat X_c = Z_k V_k^\top = X_c V_k V_k^\top,\quad
  \hat X=\hat X_c+\mathbf{1}\mu^\top
- **SVD 等价式**
  
  Xc=UΣV⊤,λj=σj2n−1,Z=UΣX_c=U\Sigma V^\top,\quad
  \lambda_j=\frac{\sigma_j^2}{n-1},\quad
  Z=U\Sigma
- **解释率与重建误差**
  
  tr⁡(S)=∑j=1dλj,Expl.Var(k)=∑j=1kλj∑j=1dλj\operatorname{tr}(S)=\sum_{j=1}^d\lambda_j,\quad
  \mathrm{Expl.Var}(k)=\frac{\sum_{j=1}^k\lambda_j}{\sum_{j=1}^d\lambda_j}
  ∥Xc−X^c∥F2=(n−1)∑j=k+1dλj\lVert X_c-\hat X_c\rVert_F^2=(n-1)\sum_{j=k+1}^d \lambda_j
- **标准化与白化**
  
  Xs=X−1μ⊤σ^⊤,Scorr=1n−1Xs⊤XsX_s=\frac{X-\mathbf{1}\mu^\top}{\hat\sigma^\top},\quad
  S_{\mathrm{corr}}=\frac{1}{n-1}X_s^\top X_s
  Z~=ZkΛk−1/2=XcVkΛk−1/2,1n−1Z~⊤Z~=Ik\tilde Z = Z_k \Lambda_k^{-1/2}=X_c V_k \Lambda_k^{-1/2},\quad
  \frac{1}{n-1}\tilde Z^\top \tilde Z = I_k
- **2D 解析直觉（可选）**
  
  S=(s11s12s12s22),v(θ)=(cos⁡θsin⁡θ)S=\begin{pmatrix} s_{11} & s_{12} \\ s_{12} & s_{22} \end{pmatrix},\quad
  v(\theta)=\begin{pmatrix}\cos\theta\\ \sin\theta\end{pmatrix}
  Var(θ)=v⊤Sv=s11cos⁡2θ+2s12sin⁡θcos⁡θ+s22sin⁡2θ,tan⁡(2θ\*)=2s12s11−s22\mathrm{Var}(\theta)=v^\top S v
  = s_{11}\cos^2\theta + 2s_{12}\sin\theta\cos\theta + s_{22}\sin^2\theta,\quad
  \tan(2\theta^\*)=\frac{2s_{12}}{s_{11}-s_{22}}
  
  > 
  
  说明：以上全部使用 ……（块）与 $…$（行内）LaTeX，Logseq 内置 KaTeX 可直接渲染。若遇到字体符号问题，可把 $\mathbf{1}$ 改为 $1$ 或 $I$（按你文档的含义分别表示全 1 列或单位阵）。
  
  <!--EndFragment-->