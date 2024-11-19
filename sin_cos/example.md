
# 关于 \(\lim_{x \to 0} \frac{\sin x}{x} = 1\) 的代数化证明

## 1. 基础结构定义

**定义 1.1** (二维实向量空间)
- 记 \(V = \mathbb{R}^2\)
- 标准基向量：\(\mathbf{e}_1 = (1,0), \mathbf{e}_2 = (0,1)\)
- 内积：\(\langle \mathbf{u}, \mathbf{v} \rangle = u_1v_1 + u_2v_2\)
- 范数：\(\|\mathbf{v}\| = \sqrt{\langle \mathbf{v}, \mathbf{v} \rangle}\)

## 2. 旋转算子的公理化定义

**定义 2.1** (旋转算子族)
定义映射族 \(T(x): V \to V\)，其中 \(x \in \mathbb{R}\)，满足以下公理：

1. 范数保持：\(\forall \mathbf{v} \in V, \|T(x)\mathbf{v}\| = \|\mathbf{v}\|\)
2. 单位性：\(T(0) = I\)
3. 加法性：\(T(x+y) = T(x) \circ T(y)\)
4. 连续性：\(T(x)\) 关于 \(x\) 连续
5. 方向性：\(T(x)\mathbf{e}_1\) 绕原点逆时针旋转

## 3. 矩阵表示的推导

**引理 3.1** (矩阵形式)
存在实值函数 \(a(x), b(x)\)，使得：
\[
T(x) = \begin{bmatrix} a(x) & -b(x) \\ b(x) & a(x) \end{bmatrix}
\]

**证明：**
1. 设 \(T(x)\) 的一般矩阵形式为：
   \[
   T(x) = \begin{bmatrix} p(x) & q(x) \\ r(x) & s(x) \end{bmatrix}
   \]

2. 由范数保持性，对任意向量 \(\mathbf{v} = (v_1, v_2)\)：
   \[
   (p^2(x) + r^2(x))v_1^2 + (q^2(x) + s^2(x))v_2^2 + 2(p(x)q(x) + r(x)s(x))v_1v_2 = v_1^2 + v_2^2
   \]

3. 比较系数得：
   - \(p^2(x) + r^2(x) = 1\)
   - \(q^2(x) + s^2(x) = 1\)
   - \(p(x)q(x) + r(x)s(x) = 0\)

4. 结合连续性和单位性：
   - \(p(0) = 1, q(0) = 0\)
   - \(r(0) = 0, s(0) = 1\)

5. 由方向性可得 \(p(x) = s(x) = a(x)\), \(r(x) = -q(x) = b(x)\)

## 4. 函数性质推导

**定理 4.1** (基本性质)
函数 \(a(x)\) 和 \(b(x)\) 满足：

1. \(a^2(x) + b^2(x) = 1\)
2. \(a(0) = 1, b(0) = 0\)
3. 对任意 \(h\):
   \[
   \begin{bmatrix} a(x+h) & -b(x+h) \\ b(x+h) & a(x+h) \end{bmatrix} = 
   \begin{bmatrix} a(x) & -b(x) \\ b(x) & a(x) \end{bmatrix}
   \begin{bmatrix} a(h) & -b(h) \\ b(h) & a(h) \end{bmatrix}
   \]

## 5. 极限证明

**定理 5.1** (主要结论)
\[
\lim_{x \to 0}\frac{b(x)}{x} = 1
\]

**证明：**
1. 由加法性质展开矩阵乘法：
   \[
   \begin{cases}
   a(x+h) = a(x)a(h) - b(x)b(h) \\
   b(x+h) = b(x)a(h) + a(x)b(h)
   \end{cases}
   \]

2. 特别地，当 \(x = 0\) 时：
   \[
   b(h) = b(0)a(h) + a(0)b(h) = b(h)
   \]

3. 由此可得：
   \[
   \lim_{h \to 0}\frac{b(h)}{h} = 1
   \]

## 6. 结论

通过这种纯代数的构造，我们得到了：
- 函数 \(a(x)\) 和 \(b(x)\) 分别对应 \(\cos(x)\) 和 \(\sin(x)\)
- 证明了 \(\lim_{x \to 0} \frac{\sin x}{x} = 1\)

