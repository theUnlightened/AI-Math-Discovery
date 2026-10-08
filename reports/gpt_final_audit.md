我把两份报告当成了**有可能共同出错的二手报告**，重新回到原论文、OEIS、期刊页面、arXiv、Erdős Problems、MathOverflow 和近年的资料核查。结论和 DeepSeek/Gemini 有几处非常重要的偏差。

# 一、先给最终结论

最重要的四个纠正是：

1. **Yellowstone permutation 的“是否为排列”根本不是开放问题。**
   Applegate–Havermann–Selcoe–Shevelev–Sloane–Zumkeller 的 2015 原论文就在摘要和正文中证明了：**每个正整数都出现，因此它就是正整数的一个 permutation。** ([arXiv](https://arxiv.org/abs/1501.01669 "\[1501.01669] The Yellowstone Permutation"))
2. **“每个奇素数出现”当然已经解决。**
   它只是上述 permutation theorem 的直接推论；原论文甚至更强地证明了每个素数都作为一个项出现。([Neil Sloane](https://neilsloane.com/doc/Yellow.pdf?utm_source=chatgpt.com "The Yellowstone Permutation"))
3. **“proper divisor sum 是平方”这个候选实际上是平凡的。**
   对每个素数 `p`，`s(p)=\sigma(p)-p=1`，而 `1` 是平方，因此有无穷多个这样的 `n`。OEIS 也明确记录“所有素数都是项”。([OEIS](https://oeis.org/A073040?utm_source=chatgpt.com "A073040 - OEIS"))
4. **maximum Sidon sets 的数量并不是“没有被研究”。**
   2025 年已经出现专门的 OEIS 序列 A382395，精确定义的正是“`\{1,\dots,n\}` 中最大基数 Sidon 集的数量”，并列出了大量精确值；2026 年又出现了按“maximum / maximal”细分的系统数据。([OEIS](https://oeis.org/A382395?utm_source=chatgpt.com "A382395 - OEIS"))
   所以 DeepSeek/Gemini 把这个问题描述成“可能完全未研究”已经过时。

---

# 二、10 个原始候选的最终审计

| 候选                                | 最终分类                 | 审计结论                                      |
| --------------------------------- | -------------------- | ----------------------------------------- |
| 1 Van Eck surjectivity            | **C/E：已知猜想，似乎未解决**   | 不是“新问题”；而是早已被明确提出的猜想                      |
| 2 EKG permutation                 | **A 已解决**            | 2002 年已证明是 permutation                    |
| 3 Yellowstone permutation         | **A 已解决**            | 2015 年原论文明确证明 every number appears        |
| 4 `n+\operatorname{rev}(n)` 为平方   | **E/C：未确认**          | 未找到直接定理；但文献基础偏娱乐数学，研究价值偏低                 |
| 5 两个 practical numbers 的 Goldbach | **A 已解决**            | Melfi 1996 已证明，而且 DeepSeek 把年份写成 2005 是错的 |
| 6 各进制数字平方和的 cycle 分类              | **B/C 已研究**          | 已有完整的 cycle-count 序列和经典文献；广义分类不能包装成新问题    |
| 7 proper divisor sum 为平方          | **A 平凡解决**           | 素数给出无限族                                   |
| 8 `\tau(n)=\tau(n+1)`             | **A 已解决**            | Heath-Brown 1984 已证明无穷多个；后来还有定量强化         |
| 9 maximum Sidon sets 的数量 `M(n)`   | **B 已研究**            | 精确数量已有专门序列 A382395；“未研究”判断错误              |
| 10 Burning Number                 | **C：已知开放，但有大量新部分结果** | 仍是开放问题，但原候选太大；真正值得做的是边界/参数化特殊情形           |

下面重点讲几个“报告犯了什么错”。

---

# 三、Burning Number：两份报告抓到了正确方向，但已经落后于 2026 文献

## 1. 标准定义

若 `G` 是 `n` 个顶点的连通图，其 burning number `b(G)` 是烧完整个图所需的最少轮数。

标准 Burning Number Conjecture 是

```math
\boxed{b(G)\le \lceil \sqrt n\rceil}
```

对所有 `n` 阶连通图 `G` 成立。([ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S009589562400042X?utm_source=chatgpt.com "The burning number conjecture holds asymptotically - ScienceDirect"))

而且有一个极其重要的结构事实：

```math
\boxed{b(G)=\min\{b(T):T\text{ is a spanning tree of }G\}.}
```

所以只要所有树满足猜想，所有连通图就都满足猜想。Murakami 2024 的论文明确使用了这个 reduction。([Springer](https://link.springer.com/article/10.1007/s00373-024-02812-6?utm_source=chatgpt.com "The Burning Number Conjecture is True for Trees without Degree-2 Vertices | Graphs and Combinatorics | Springer Nature Link"))

---

## 2. 路径并不是未解决的“高 degree-2”例子

这是一个非常重要的逻辑修正。

对路径 `P_n`，

```math
\boxed{b(P_n)=\lceil\sqrt n\rceil}.
```

原始 burning-number 论文已经证明。([ResearchGate](https://www.researchgate.net/publication/280329478_How_to_burn_a_graph?utm_source=chatgpt.com "(PDF) How to Burn a Graph"))

而路径恰好有 `n-2` 个 degree-2 vertices。

所以：

> “degree-2 vertices 很多 ⇒ Burning Conjecture 难”

这个说法不准确。

真正困难的是**中间结构**：

- degree-2 为 0：Murakami 2024 已解决；
- degree-2 接近 `n`：路径等重要极端结构也已解决；
- 中间复杂的 degree-2 subdivision 结构：仍是主要困难。

Murakami 自己就在结尾明确指出，需要处理的是这种 intermediate instances。([Springer](https://link.springer.com/article/10.1007/s00373-024-02812-6?utm_source=chatgpt.com "The Burning Number Conjecture is True for Trees without Degree-2 Vertices | Graphs and Combinatorics | Springer Nature Link"))

---

## 3. Murakami 2024 究竟证明了什么？

不是“Burning Number Conjecture 对 trees 成立”。

而是：

```math
\boxed{\text{所有无 degree-2 vertices 的树都满足 }b(T)\le\lceil\sqrt n\rceil.}
```

即 homeomorphically irreducible trees / HITs。([Springer](https://link.springer.com/article/10.1007/s00373-024-02812-6?utm_source=chatgpt.com "The Burning Number Conjecture is True for Trees without Degree-2 Vertices | Graphs and Combinatorics | Springer Nature Link"))

还得到：

```math
b(T)\le \left\lceil\sqrt{n+d}\right\rceil,
```

其中 `d` 是 degree-2 vertices 的数量。([Springer](https://link.springer.com/article/10.1007/s00373-024-02812-6?utm_source=chatgpt.com "The Burning Number Conjecture is True for Trees without Degree-2 Vertices | Graphs and Combinatorics | Springer Nature Link"))

---

## 4. 2025/2026 的进展比两份报告说得更重要

### Ning–Jin–Zhang，2025 arXiv / 2026 期刊

若树 `T` 有 `n` 个顶点、`n_2` 个 degree-2 vertices，他们证明

```math
b(T)\le \left\lceil \sqrt{ n+n_2- \left\lceil \sqrt{n+n_2+\tfrac14}-\tfrac32 \right\rceil } \right\rceil.
```

因此至少推出：

```math
\boxed{n_2\le \lfloor\sqrt{n-1}\rfloor \implies b(T)\le\lceil\sqrt n\rceil.}
```

这篇文章 2025 年发表预印本，2026 年 3 月发表于 *Graphs and Combinatorics*。([arXiv](https://arxiv.org/abs/2509.03144?utm_source=chatgpt.com "The burning number conjecture holds for trees of order $n$ with at most $\left\lfloor \sqrt{n-1}\right\rfloor$ degree-2 vertices"))

### 更重要的是：2026 年还有更强的预印本

Das–Islam–Mitra–Paul 在 2026 年的 SSRN 预印本声称：

```math
\boxed{n_2\le 2\lceil\sqrt n\rceil-3 \implies b(T)\le\lceil\sqrt n\rceil.}
```

也就是说，如果你们之前提出的“degree-2 density threshold”恰好是这个范围，**那条研究问题已经被最新预印本覆盖了**。([SSRN](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7276482\&utm_source=chatgpt.com "The Burning Number Conjecture is true for Trees with Few Degree-2 Vertices by Sandip Das, Sk Samim Islam, Ritam Manna Mitra, Sanchita Paul :: SSRN"))

注意：它目前应称为 **2026 preprint claim**，不能像正式期刊定理那样不加限定地表述。

---

# 四、Burning 最值得追的新小问题：不是再问整个 conjecture

这里出现了一个非常漂亮的“边界”。

目前已知：

```math
n_2\le 2\lceil\sqrt n\rceil-3
```

已有 2026 预印本结果。

于是最自然的下一格就是：

```math
\boxed{ n_2=2\lceil\sqrt n\rceil-2 }
```

对应的问题：

> **对所有 `n` 阶树 `T`，若 `T` 恰有 `2\lceil\sqrt n\rceil-2` 个 degree-2 vertices，是否必有 `b(T)\le\lceil\sqrt n\rceil`？**

这比整个 Burning Number Conjecture 小非常多，而且是一个非常干净的**边界问题**。

它目前是我最推荐的 Burning 方向。

为什么有价值？

因为它不是随便切一个参数：

```math
2\sqrt n-3 \quad\longrightarrow\quad 2\sqrt n-2
```

恰好卡在最新文献的边界之外。

风险也非常明确：最新预印本以后可能继续把这个 `-2` 往上推进，所以必须持续跟踪。

---

# 五、Burning 的“diameter question”：可以保留，但应该改成一个更精确的参数问题

已有一般不等式：

```math
\boxed{\lceil\sqrt{d(G)+1}\rceil\le b(G)\le r(G)+1}
```

其中 `d(G)` 是 diameter，`r(G)` 是 radius。([ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0096300324005617?utm_source=chatgpt.com "Graphs with burning number three - ScienceDirect"))

对树，

```math
r(T)=\left\lceil\frac{d(T)}2\right\rceil.
```

所以得到

```math
\lceil\sqrt{d(T)+1}\rceil \le b(T) \le \left\lceil\frac{d(T)}2\right\rceil+1.
```

因此不要直接提出一个模糊的“burning number 和 diameter 有什么关系”。

更好的版本是定义

```math
B(d)=\max\{b(T): T\text{ is a tree and }\operatorname{diam}(T)=d\}.
```

然后问：

```math
\boxed{\text{确定或估计 }B(d).}
```

这就变成了一个精确的单参数 extremal problem。

它的已知夹逼立刻是

```math
\lceil\sqrt{d+1}\rceil \le B(d)\le \left\lceil\frac d2\right\rceil+1.
```

这个问题我没有找到足够直接的现成“已解决定理”，所以更适合标成：

**D/E — potentially underexplored；需要专家级 novelty verification。**

---

# 六、Yellowstone：这是两份 AI 报告最严重的共同错误

定义是：

```math
a(1)=1,\quad a(2)=2,\quad a(3)=3,
```

而 `n\ge4` 时，取最小的、此前未出现的正整数 `a(n)`，满足

```math
\gcd(a(n),a(n-2))>1, \qquad \gcd(a(n),a(n-1))=1.
```

这正是原论文的定义。([arXiv](https://arxiv.org/abs/1501.01669 "\[1501.01669] The Yellowstone Permutation"))

而且 2015 原论文第一段直接写明：

```math
\boxed{\text{we show that this is a permutation of the positive integers}.}
```

([arXiv](https://arxiv.org/abs/1501.01669 "\[1501.01669] The Yellowstone Permutation"))

正文更具体地给出：

- 每个素数都整除某个项；
- 每个素数整除无穷多个项；
- 每个素数自身作为一个项出现；
- 最终推出 **all numbers appear**。([Neil Sloane](https://neilsloane.com/doc/Yellow.pdf?utm_source=chatgpt.com "The Yellowstone Permutation"))

所以：

### “Yellowstone permutation 是 permutation 吗？”

```math
\boxed{\textbf{A — 已解决，2015。}}
```

### “每个奇素数都出现吗？”

```math
\boxed{\textbf{A — 已解决，而且是直接推论。}}
```

### “每个正整数都出现吗？”

```math
\boxed{\textbf{A — 原论文已经证明。}}
```

这三条都不能再当成研究问题。

---

# 七、Yellowstone 真正值得研究的“小问题”

当前 OEIS A098550 仍保留一个非常有意思的猜想：

> **素数是否按自然顺序出现？**

OEIS 明确写着：

> “The primes in the sequence appear in their natural order.”

但同时标明这是 **conjecture**，当时没有证明。([OEIS](https://oeis.org/A098550 "A098550 - OEIS"))

这和“每个素数出现”完全不是一回事。

设 `p_1<p_2<\cdots` 是素数，令 `n_p` 为 `p` 第一次出现的位置。真正的问题是：

```math
\boxed{p<q\implies n_p<n_q.}
```

这是一个真正有内容的“最小机制”。

OEIS 还记录了更细的局部猜想：

> 对足够大的素数 `p`，第一次出现 `p` 时似乎形成
> `2b,2p,p` 这样的局部结构，并且出现位置大约与 `2.14p` 成正比。([OEIS](https://oeis.org/A098550?utm_source=chatgpt.com "A098550 - OEIS"))

所以比“every odd prime appears”强得多的真正研究方向是：

```math
\boxed{ \text{证明大素数的第一次出现次序与/或局部 }2b,2p,p\text{ 结构。} }
```

不过它已经是已有 conjecture，因此不是“新问题”。

---

# 八、Van Eck：这里反而是两份报告中最值得保留的一条

Van Eck 序列标准定义就是 OEIS A181391：

```math
a_1=0,
```

若最近一次相同值出现在 `m<n`，则

```math
a_{n+1}=n-m,
```

否则

```math
a_{n+1}=0.
```

([OEIS](https://oeis.org/A181391/internal?utm_source=chatgpt.com "A181391 - OEIS"))

已有的可靠信息包括：

- 有无穷多个 0；
- 序列无界；
- 计算上强烈暗示所有正整数都会出现；
- 但这只是 conjecture，并没有找到一个已发表的证明。早期 *The Encyclopedia of Integer Sequences* 对其明确称作 conjecture。([ResearchGate](https://www.researchgate.net/publication/265348370_The_Encyclopedia_of_Integer_Sequences?utm_source=chatgpt.com "(PDF) The Encyclopedia of Integer Sequences"))

因此原始问题

```math
\boxed{\text{Does every nonnegative integer occur in A181391?}}
```

更准确的分类是：

**C/E：known conjectural / apparently unresolved。**

不是“新问题”。

---

# 九、但 Van Eck 可以进一步缩小成更好的参数问题

定义

```math
t(m)=\min\{n:a_n=m\},
```

即 `m` 的第一次出现位置。

那么与其问：

```math
\forall m,\quad t(m)<\infty?
```

可以问：

```math
\boxed{\text{研究 }t(m)\text{ 的增长速度。}}
```

例如寻找：

```math
t(m)\le F(m)
```

的显式上界，或者研究

```math
\log t(m)/m,\qquad \frac{\log t(m)}{\log m}
```

的 limsup/liminf。

这比“所有整数都出现吗”小很多，而且仍然直接围绕原 conjecture 的核心机制——**一个给定值究竟什么时候再次被创造出来**。

但是这一方向的 novelty evidence 目前不够强，我只能给：

**E — potentially underexplored；需要进一步专家检索。**

---

# 十、Maximum Sidon Sets：这里需要做最严格的纠错

## 1. Sidon 集定义

对 `A\subseteq\{1,\dots,n\}`，Sidon 的标准定义之一是：

若

```math
a+b=c+d,\qquad a,b,c,d\in A,
```

那么只能有平凡情形

```math
\{a,b\}=\{c,d\}.
```

等价地，也可以说不同元素对产生的正差值都是不同的。([OEIS](https://oeis.org/A143823?utm_source=chatgpt.com "A143823 - OEIS"))

---

## 2. 最大大小

令

```math
s(n)=\max\{|A|:A\subseteq[1,n],\ A\text{ Sidon}\}.
```

经典结果给出

```math
\boxed{s(n)\sim\sqrt n.}
```

而且 2023 年 Balogh–Füredi–Roy 给出了更细的上界：

```math
s(n)\le \sqrt n+0.998\,n^{1/4}
```

对充分大的 `n`。([Taylor & Francis Online](https://www.tandfonline.com/doi/full/10.1080/00029890.2023.2176667?utm_source=chatgpt.com "An Upper Bound on the Size of Sidon Sets: The American Mathematical Monthly: Vol 130 , No 5 - Get Access"))

所以 DeepSeek 的

> “maximum size 是 `(1+o(1))\sqrt n`”

基本方向没错，但需要注意这是**渐近式，不是精确公式**。

---

# 十一、Maximum 与 Maximal 完全不是一回事

这是你们项目中特别容易把 AI 带偏的一点。

### Maximum

```math
|A|=s(n).
```

即：在所有 Sidon 集里，**基数最大**。

### Maximal

A 不能再加入任何新元素而保持 Sidon，但它未必是最大基数。

2026 年新的 OEIS A399118 甚至直接把这个 distinction 写出来，并给出了“所有 inclusion-maximal Sidon subsets”按 cardinality 分类的整张三角表。([OEIS](https://oeis.org/A399118?utm_source=chatgpt.com "A399118 - OEIS"))

所以：

```math
\boxed{\text{maximum}\neq\text{maximal}}
```

绝对不能混用。

---

# 十二、你的 `M(n)` 其实已经被直接定义和计算研究了

定义

```math
M(n) = \#\{A\subseteq[1,n]: A\text{ Sidon},\ |A|=s(n)\}.
```

OEIS A382395 的定义恰好就是：

```math
\boxed{ M(n)=\text{number of maximum-sized Sidon subsets of }\{1,\dots,n\}. }
```

而且它不是几十年前埋在文献里的隐含对象：

- 2025 年建立专门序列；
- 2026 年已经给出到 `n=60` 的精确值；
- 最近更新到 2026 年。([OEIS](https://oeis.org/A382395?utm_source=chatgpt.com "A382395 - OEIS"))

例如

```math
M(7)=2,\quad M(10)=60,\quad M(18)=8,\quad M(60)=18.
```

([OEIS](https://oeis.org/A382395?utm_source=chatgpt.com "A382395 - OEIS"))

因此：

> “number of maximum Sidon sets 没有人研究过”

这个判断必须撤销。

最终分类：

```math
\boxed{\textbf{B — Known studied.}}
```

---

# 十三、“`M(n)` 无界”能不能直接由 Singer 推出来？

这是 DeepSeek 原报告最值得怀疑的地方。

Singer 给出的是：

对每个 prime power `q`，在

```math
\mathbb Z/(q^2+q+1)\mathbb Z
```

里有一个大小为

```math
q+1
```

的 Sidon / perfect difference set。([Springer](https://link.springer.com/article/10.1007/s40590-024-00676-7?utm_source=chatgpt.com "Sidon–Ramsey and $$B_{h}$$ -Ramsey numbers | Boletín de la Sociedad Matemática Mexicana | Springer Nature Link"))

但是：

```math
\boxed{q+1\text{ 不一定等于 }s(q^2+q+1).}
```

这一步非常关键。

例如 `q=2`：

```math
q^2+q+1=7,
```

Singer 给出大小 `3` 的 Sidon 集，但

```math
s(7)=4.
```

OEIS A143824 明确给出 `s(7)=4`。([OEIS](https://oeis.org/A143824?utm_source=chatgpt.com "A143824 - OEIS"))

甚至 `q=3`：

```math
q^2+q+1=13,
```

而

```math
s(13)=5>4=q+1.
```

所以：

```math
\boxed{\text{Singer construction }\not\Rightarrow\text{ Singer set is maximum in }[1,v].}
```

因此不能直接从 Singer 得出：

```math
M(n)\to\infty.
```

这正是你们原来讨论中必须修正的逻辑漏洞。

---

# 十四、“Singer-length question”应该怎么重新处理？

假设你们所谓的 Singer-length question 是：

```math
n=q^2+q+1
```

时研究 `M(n)`。

那么一个**非常合理的新版本**是：

```math
\boxed{ M(q^2+q+1)\text{ 是否沿某个无限的 prime-power }q\text{ 序列增长？} }
```

而不是问 Singer set 本身是不是 maximum。

这个版本：

- 有明确参数；
- 与 Singer construction 有天然联系；
- 又不被 Singer theorem 直接解决；
- 可以做精确计算；
- 可以和 A382395 对接。

目前我的判断是：

```math
\boxed{\textbf{E — potentially underexplored, but novelty requires expert verification.}}
```

这是 Sidon 线上我最愿意继续调查的一条。

---

# 十五、其余候选的快速数学审计

## Candidate 2 — EKG

完全解决。

Lagarias–Rains–Sloane 2002 明确证明

```math
\{a(n):n\ge1\}=\mathbb N.
```

他们同时指出真正未解决的是更精细的 asymptotic behavior。([arXiv](https://arxiv.org/abs/math/0204011?utm_source=chatgpt.com "The EKG Sequence"))

因此：

**A — solved.**

---

## Candidate 5 — Practical numbers

DeepSeek 的年份错了。

Melfi 的论文是：

**Giuseppe Melfi, “On Two Conjectures about Practical Numbers,” Journal of Number Theory 56 (1996), 205–210.**

其中第一条就是：

```math
\boxed{\text{every even positive integer is a sum of two practical numbers}.}
```

([ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0022314X96900128?utm_source=chatgpt.com "On Two Conjectures about Practical Numbers - ScienceDirect"))

因此：

**A — solved.**

---

## Candidate 6 — digit-square cycles

对固定 base `b`，迭代最终一定进入有限 cycle。

经典结果已经研究这一 dynamical system；OEIS A193585 直接记录“base `b` 有多少个 cycles”，而且列出 Hasse–Prichett、Grundman–Teeple 等文献。([OEIS](https://oeis.org/A193585?utm_source=chatgpt.com "A193585 - OEIS"))

例如十进制只有：

```math
(1)
```

和

```math
(4,16,37,58,89,145,42,20)
```

这一个非平凡 cycle。([OEIS](https://oeis.org/A193585?utm_source=chatgpt.com "A193585 - OEIS"))

2023 年甚至还有研究给出特殊 Fibonacci bases 的显式 cycle。([arXiv](https://arxiv.org/abs/2310.04439?utm_source=chatgpt.com "Fibonacci Cycles and Fixed Points"))

所以：

**B/C — extensively studied。**

“分类所有 base 的所有 cycle”仍可能包含开放部分，但原始问题过大，而且已经嵌入已有研究体系。

---

## Candidate 7 — proper divisor sum square

这是最容易漏掉的逻辑漏洞。

```math
s(n)=\sigma(n)-n.
```

若 `p` 为素数，则

```math
s(p)=1.
```

而

```math
1=1^2.
```

由于素数有无穷多个，

```math
\boxed{\text{there are infinitely many such }n.}
```

([OEIS](https://oeis.org/A073040?utm_source=chatgpt.com "A073040 - OEIS"))

所以这个候选不仅 solved，而且几乎是**一行证明**。

---

## Candidate 8 — `\tau(n)=\tau(n+1)`

这是两份报告又一次共同低估了已有理论。

Erdős–Mirsky 的问题是：

```math
\boxed{\tau(n)=\tau(n+1)\text{ 是否有无穷多解？}}
```

Heath-Brown 在 1984 年已经证明 yes，并且更强地证明

```math
\#\{n\le x:\tau(n)=\tau(n+1)\} \gg \frac{x}{(\log x)^7}.
```

随后 Hildebrand 又进一步改进，甚至 2025 年 Tao–Teräväinen 对其精细计数还有更新。([Erdos Problems](https://www.erdosproblems.com/history/946?utm_source=chatgpt.com "Erdős Problems"))

所以：

```math
\boxed{\textbf{A — solved, and quantitatively studied.}}
```

---

# 十六、10 个更好的研究问题

下面这些不是“声称新开放问题”，而是按照你的 epistemic rule，专门筛：

**已有理论很接近，但不能立刻回答。**

---

## R1 — Burning degree-2 boundary

```math
\boxed{ \text{若 }n_2=2\lceil\sqrt n\rceil-2,\text{ 是否必有 } b(T)\le\lceil\sqrt n\rceil? }
```

**为什么自然：** 2026 预印本已把保证推进到 `2\lceil\sqrt n\rceil-3`。([SSRN](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7276482\&utm_source=chatgpt.com "The Burning Number Conjecture is true for Trees with Few Degree-2 Vertices by Sandip Das, Sk Samim Islam, Ritam Manna Mitra, Sanchita Paul :: SSRN"))

**已知：** 到 `2\lceil\sqrt n\rceil-3` 有最新结果。

**未知：** “再加一个 degree-2” 的精确边界。

**不平凡性：** 正好处于当前 theorem 的边界外一格。

**计算：** 枚举小 `n` 的树；用 exact burning algorithm / SAT / ILP 算 `b(T)`。

**风险：** 高度活跃领域，可能很快被新预印本覆盖。

**意义：** ★★★★★

---

## R2 — Burning threshold function

定义

```math
\kappa(n)= \max\{k:\text{所有 }n\text{-vertex trees with }n_2\le k \text{ satisfy BNC}\}.
```

研究：

```math
\boxed{\kappa(n)\text{ 的精确值或渐近行为是什么？}}
```

**已知：**

```math
\kappa(n)\ge 2\lceil\sqrt n\rceil-3
```

至少受到最新预印本结果支持；同时路径说明大 `n_2` 本身不意味着困难。([SSRN](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7276482\&utm_source=chatgpt.com "The Burning Number Conjecture is true for Trees with Few Degree-2 Vertices by Sandip Das, Sk Samim Islam, Ritam Manna Mitra, Sanchita Paul :: SSRN"))

**剩余：** 真正的“hard region”在哪里？

**优势：** 把一个 open conjecture 变成一个有限参数 family。

**风险：** 若 BNC 最终成立，则 `\kappa(n)` 最终就是 `n-2`。

**意义：** ★★★★★

---

## R3 — Burning by core + subdivision pattern

把所有 degree-2 chains 压缩掉，得到 HIT core `H`。

研究：

```math
\boxed{ \text{哪些 subdivision patterns of }H \text{ 保证 }b(T)\le\lceil\sqrt{|T|}\rceil? }
```

**为什么自然：** Murakami 的证明恰恰依赖 smoothing degree-2 vertices。([Springer](https://link.springer.com/article/10.1007/s00373-024-02812-6?utm_source=chatgpt.com "The Burning Number Conjecture is True for Trees without Degree-2 Vertices | Graphs and Combinatorics | Springer Nature Link"))

这比只数 `n_2` 更精确，因为两个树可以有完全相同的 degree-2 数，但 subdivision 分布非常不同。

**风险：** 可能已有论文以 subdivision / homeomorphic core 语言处理，需要继续查 citation chain。

**意义：** ★★★★★

---

## R4 — Burning number at fixed diameter

定义

```math
B(d)=\max_{\operatorname{diam}(T)=d}b(T).
```

研究

```math
\boxed{B(d)\text{ 的增长率或精确值。}}
```

已知

```math
\lceil\sqrt{d+1}\rceil \le B(d) \le \left\lceil\frac d2\right\rceil+1.
```

上、下界来自 burning number 与 diameter/radius 的一般关系。([ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0096300324005617?utm_source=chatgpt.com "Graphs with burning number three - ScienceDirect"))

**优势：** 一个真正干净的单参数 extremal problem。

**计算：** 固定直径枚举小树并求 exact burning number。

**风险：** 可能已经有未被关键词搜索抓到的直径型结果。

**意义：** ★★★★☆

---

## R5 — Van Eck first-occurrence growth

定义

```math
t(m)=\min\{n:a_n=m\}.
```

研究：

```math
\boxed{t(m)\text{ 的增长率是什么？}}
```

已知：所有 `m` 的出现本身都还是 conjectural。([ResearchGate](https://www.researchgate.net/publication/265348370_The_Encyclopedia_of_Integer_Sequences?utm_source=chatgpt.com "(PDF) The Encyclopedia of Integer Sequences"))

这个问题比“是否 surjective”更加 quantitative。

**实验：** 直接算 `t(m)`，做 `\log t(m)` 与 `m` 的拟合；检查是否存在幂律、指数律、分层行为。

**风险：** 很可能在 OEIS 社群/私人笔记中有人已经研究，但正式论文少。

**意义：** ★★★☆☆

---

## R6 — Van Eck finite surjectivity bounds

研究一个有限版本：

```math
\boxed{ \text{给定 }N,\text{ 是否所有 }1\le m\le N \text{ 都出现在前 }F(N)\text{ 项中？} }
```

寻找尽可能小的 `F(N)`。

这个问题把“无限 conjecture”转化成一个明确的 algorithmic growth problem。

**风险：** novelty 不高。

**意义：** ★★★☆☆

---

## R7 — Yellowstone prime-order conjecture

设 `p_i` 为第 `i` 个素数，`n_{p_i}` 为第一次出现位置。

问：

```math
\boxed{ n_{p_1}<n_{p_2}<n_{p_3}<\cdots? }
```

OEIS 已明确把“primes appear in natural order”列为 conjecture。([OEIS](https://oeis.org/A098550 "A098550 - OEIS"))

这是 Yellowstone 最干净的真正开放机制。

**但是：** 已知 conjecture，不能叫新。

**意义：** ★★★★☆

---

## R8 — Yellowstone large-prime local pattern

对于足够大的素数 `p`，验证/证明 OEIS 中记录的结构：

```math
2b,\ 2p,\ p
```

以及关于第一次出现位置的线性规模猜想。([OEIS](https://oeis.org/A098550?utm_source=chatgpt.com "A098550 - OEIS"))

这是比“prime order”更局部的 special case。

**计算：** 生成到很大的 `N`，抽取所有 large primes 的 first-occurrence neighborhoods。

**风险：** 已被原项目明确提出，所以是 **B/C 已研究**，不是新问题。

---

## R9 — Sidon maximum-count along Singer lengths

定义

```math
M(n)=\#\{\text{maximum Sidon subsets of }[n]\}.
```

考虑特殊序列

```math
n=q^2+q+1.
```

研究：

```math
\boxed{ M(q^2+q+1)\to\infty? }
```

**为什么自然：** Singer 在这些长度提供非常强的 Sidon 构造，但构造的大小 `q+1` 不一定是 `s(n)`。([Springer](https://link.springer.com/article/10.1007/s40590-024-00676-7?utm_source=chatgpt.com "Sidon–Ramsey and $$B_{h}$$ -Ramsey numbers | Boletín de la Sociedad Matemática Mexicana | Springer Nature Link"))

**正是这点让问题变得有意思：**

Singer 给你大量结构，

但不知道它们是否真正落在 **maximum layer**。

**计算：** 从 Singer sets 出发，优化到 maximum cardinality，再记录 orbit 数量。

**风险：** finite geometry 文献可能已经包含相关分类。

**意义：** ★★★★☆

---

## R10 — Asymptotic growth of `M(n)`

继续研究

```math
M(n)=\#\{\text{maximum Sidon sets in }[n]\}.
```

更深入的问题是：

```math
\boxed{ \text{是否存在 }c>0\text{ 与无穷多个 }n \text{ 使 }M(n)\ge 2^{c\sqrt n}? }
```

这是与“所有 Sidon sets 的 counting problem”接近，但更加聚焦于**maximum layer**。

注意：

Cameron–Erdős 类型的问题研究的是 **maximal Sidon sets** 的数量，而不是这里的 maximum-size Sidon sets。([Erdos Problems](https://www.erdosproblems.com/tags/sidon%20sets?utm_source=chatgpt.com "Erdős Problems"))

所以二者绝不能直接混为一谈。

**风险：** 极高。很可能已有组合计数论文隐含结果。

**意义：** ★★★★★

---

# 十七、Top 5 最终排名

我的评分不是“这个问题有没有意义”，而是按你要求的：

- 数学精确性
- underexplored evidence
- novelty potential
- mathematical significance
- computational tractability
- 已知风险

综合后：

| Rank  | 问题                                     | 精确 | Underexplored | Novelty | 意义 | 计算 | 已知风险 | 分类      |
| ----- | -------------------------------------- | -- | ------------- | ------- | -- | -- | ---- | ------- |
| **1** | Burning：`n_2=2\lceil\sqrt n\rceil-2`   | 10 | 9             | 9       | 9  | 8  | 6    | **D**   |
| **2** | Burning：`\kappa(n)` threshold function | 10 | 8             | 9       | 10 | 8  | 6    | **D**   |
| **3** | Sidon：`M(q^2+q+1)\to\infty?`           | 10 | 8             | 9       | 8  | 7  | 7    | **E**   |
| **4** | Burning：固定 diameter 的 `B(d)`           | 10 | 8             | 8       | 8  | 9  | 6    | **D/E** |
| **5** | Van Eck：`t(m)` growth                  | 9  | 8             | 8       | 6  | 9  | 7    | **E**   |

---

# 十八、最终研究战略：我会这样取舍

### 第一梯队：Burning Number

最值得投入。

但不要再问：

> “所有树都满足 `b(T)\le\lceil\sqrt n\rceil` 吗？”

因为这是一个**众所周知的著名开放问题**。

应该问最新边界：

```math
\boxed{n_2=2\lceil\sqrt n\rceil-2}
```

或者更结构化地问 subdivision pattern。

这两个版本最像真正的本科生/早期研究项目可以“往前顶一点”的问题。

---

### 第二梯队：Sidon

不要再做：

```math
M(n)\text{ 是否 unbounded?}
```

因为 `M(n)` 已经被直接定义、计算、序列化研究。([OEIS](https://oeis.org/A382395?utm_source=chatgpt.com "A382395 - OEIS"))

更值得做的是：

```math
\boxed{M(q^2+q+1)}
```

这个 Singer-length slice。

这里最大的优点是：

**已有结构非常强，但 Singer theorem 又没有直接解决 maximum-cardinality 问题。**

---

### 第三梯队：Van Eck

这是你们原候选里最像“搜索不到很多文献，但确实存在明确数学猜想”的一条。

不过它的数学意义低于 Burning / Sidon，所以更适合做：

```math
t(m),\quad\text{finite surjectivity},\quad\text{growth bounds}
```

而不是直接再问 surjectivity。

---

# 十九、我对两份 AI 报告的最终“可信度判决”

### DeepSeek

**优点：**
确实抓到了 Burning、Van Eck、Sidon 三个方向。

**主要错误：**

- Yellowstone 核心问题判断错误；
- practical numbers 年份错误；
- proper-divisor-square 没抓到素数的平凡无限族；
- Sidon 的 maximum/maximal 风险没有彻底消除；
- 对 2025–2026 最新 Burning threshold 更新严重滞后。

### Gemini

**优点：**
比 DeepSeek 更谨慎，尤其是 novelty 上没有乱喊“new open problem”。

**主要错误：**
它与 DeepSeek **共同继承了 Yellowstone 的根本性错误**：没有回到 2015 原论文核对 Theorem 1。原论文明明写着已经是 permutation。([arXiv](https://arxiv.org/abs/1501.01669 "\[1501.01669] The Yellowstone Permutation"))

因此这个案例非常能说明：

> **两个 AI 独立得到同一个结论，不等于验证成功。**

真正有效的 adversarial review 是：

```math
\boxed{\text{回到 primary source，检查原定理到底证明了什么。}}
```

---

# 二十、最终“项目级”结论

截至 **2026 年 10 月 8 日**，我不会把你们目前的任何候选称为：

> “a new open problem”

最可靠的表述是：

**Burning Number：** 著名开放问题，但存在非常清晰的最新边界，可以提炼出潜在 underexplored special case。([SSRN](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7276482\&utm_source=chatgpt.com "The Burning Number Conjecture is true for Trees with Few Degree-2 Vertices by Sandip Das, Sk Samim Islam, Ritam Manna Mitra, Sanchita Paul :: SSRN"))

**Yellowstone：** 核心 permutation 问题已经在 2015 年解决；值得研究的是 prime-order / first-occurrence structure，而这些本身已经是已有 conjectures。([arXiv](https://arxiv.org/abs/1501.01669 "\[1501.01669] The Yellowstone Permutation"))

**Van Eck：** 每个正整数出现仍属于已存在的 conjectural territory；比它更值得做的是 quantitative first-occurrence questions。([ResearchGate](https://www.researchgate.net/publication/265348370_The_Encyclopedia_of_Integer_Sequences?utm_source=chatgpt.com "(PDF) The Encyclopedia of Integer Sequences"))

**Maximum Sidon：** “数量是否被研究”这一点已经不是未知，A382395 就是直接证据；真正有潜力的是把 `M(n)` 限制到 Singer lengths 或研究它的增长。([OEIS](https://oeis.org/A382395?utm_source=chatgpt.com "A382395 - OEIS"))

**最值得你们下一轮 AI 深挖的单个问题：**

```math
\boxed{ \textbf{若 }T\textbf{ 是 }n\textbf{ 阶树且 } n_2=2\lceil\sqrt n\rceil-2, \textbf{ 是否必有 } b(T)\le\lceil\sqrt n\rceil? }
```

这是目前我看到的\*\*“最小、最精确、与最新文献贴得最近、又没有被我检索到直接解决”的候选\*\*。但按照你设定的 epistemic rule，我仍然只会称它为：

```math
\boxed{\textbf{potentially underexplored}}
```

而不是“new open problem”。

### 核心一手/强来源

Murakami 2024：Burning Number Conjecture 对无 degree-2 的树成立，并给出 smoothing / spanning-tree reduction。([Springer](https://link.springer.com/article/10.1007/s00373-024-02812-6?utm_source=chatgpt.com "The Burning Number Conjecture is True for Trees without Degree-2 Vertices | Graphs and Combinatorics | Springer Nature Link"))

Ning–Jin–Zhang 2025/2026：degree-2 threshold 的正式推进。([arXiv](https://arxiv.org/abs/2509.03144?utm_source=chatgpt.com "The burning number conjecture holds for trees of order $n$ with at most $\left\lfloor \sqrt{n-1}\right\rfloor$ degree-2 vertices"))

Das–Islam–Mitra–Paul 2026：最新预印本把阈值进一步声称推进至 `2\lceil\sqrt n\rceil-3`。([SSRN](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7276482\&utm_source=chatgpt.com "The Burning Number Conjecture is true for Trees with Few Degree-2 Vertices by Sandip Das, Sk Samim Islam, Ritam Manna Mitra, Sanchita Paul :: SSRN"))

Applegate et al. 2015：Yellowstone permutation 已证明是 `\mathbb N` 的 permutation。([arXiv](https://arxiv.org/abs/1501.01669 "\[1501.01669] The Yellowstone Permutation"))

OEIS A181391：Van Eck 序列。([OEIS](https://oeis.org/A181391?utm_source=chatgpt.com "A181391 - OEIS"))

OEIS A098550：Yellowstone 的最新结构与 prime-order conjecture。([OEIS](https://oeis.org/A098550 "A098550 - OEIS"))

OEIS A143824：最大 Sidon 集大小 `s(n)`。([OEIS](https://oeis.org/A143824?utm_source=chatgpt.com "A143824 - OEIS"))

OEIS A382395：**最大** Sidon 集数量 `M(n)`。([OEIS](https://oeis.org/A382395?utm_source=chatgpt.com "A382395 - OEIS"))

OEIS A399118：**极大** Sidon 集按大小分类，明确区分 maximal 与 maximum。([OEIS](https://oeis.org/A399118?utm_source=chatgpt.com "A399118 - OEIS"))

Melfi 1996：practical-number Goldbach conjecture 已证明。([ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0022314X96900128?utm_source=chatgpt.com "On Two Conjectures about Practical Numbers - ScienceDirect"))

Erdős Problems #946：`\tau(n)=\tau(n+1)` 的完整历史与定量结果。([Erdos Problems](https://www.erdosproblems.com/history/946?utm_source=chatgpt.com "Erdős Problems"))
