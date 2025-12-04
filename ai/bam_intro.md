# 🧠 Bidirectional Associative Memory (BAM) – Simple & Clear Notes

## 1. What is BAM?
Bidirectional Associative Memory (BAM) is a neural network that stores **pairs of patterns**.  
If you give it X → it recalls Y  
If you give it Y → it recalls X  

This makes BAM a **two-way (bidirectional)** memory system.

- Invented by **Bart Kosko** (1987–1988)
- Type: **Hetero-associative** memory (X ≠ Y)
- Works like a simple “brain” that remembers connected patterns.

# 🧠 BAM Numerical Example (Clean & Organized)

We want to store the following two pattern pairs:

X₁ = [ +1,  -1 ]      ↔      Y₁ = [ +1,  +1 ]  
X₂ = [ -1,  +1 ]      ↔      Y₂ = [ -1,  -1 ]

---

## 1. Compute the Weight Matrix W

### Outer Product for Pair 1
X₁ᵀ × Y₁:

[  1 ]        [ 1  1 ]     →     [  (1×1)   (1×1)  ]  
[ -1 ]    ×                   →     [ (-1×1) (-1×1) ]

Result:
[  1   1  ]  
[ -1  -1 ]

---

### Outer Product for Pair 2
X₂ᵀ × Y₂:

[ -1 ]        [ -1  -1 ]      →    [ (-1×-1) (-1×-1) ]  
[  1 ]    ×                     →   [ (1×-1)  (1×-1) ]

Result:
[  1   1 ]  
[ -1 -1 ]

---

### Sum the Two Products to Form W

W = (Product₁) + (Product₂)

W =
[ 1  1 ]   +   [ 1  1 ]   =   [ 2  2 ]  
[ -1 -1 ]     [ -1 -1 ]       [ -2 -2 ]

So the final weight matrix is:

**W = [ [2, 2],  
        [-2, -2] ]**

---

## 2. Recall Phase (X → Y)

We test recall using X₁ = [ 1, -1 ].

### Compute X₁ × W

[ 1  -1 ] ×  
[  2   2 ]  
[ -2  -2 ]

Step-by-step:
- First output: (1×2) + (-1×-2) = 2 + 2 = **4**  
- Second output: (1×2) + (-1×-2) = 2 + 2 = **4**

Weighted Sum = [ 4, 4 ]

### Apply Activation Function (sign)
sign(4) = +1

So recalled pattern:
**Y = [ +1, +1 ] = Y₁**

---

## 3. Recall Phase (Y → X)

Use Y₁ = [ 1, 1 ].

### Compute Y₁ × Wᵀ

Wᵀ =
[  2  -2 ]  
[  2  -2 ]

Multiply:

[ 1  1 ] ×  
[ 2  -2 ]  
[ 2  -2 ]

Step-by-step:
- First output: (1×2) + (1×2) = **4**  
- Second output: (1×-2) + (1×-2) = **-4**

Weighted Sum = [ 4, -4 ]

### Apply Activation Function
sign(4) = +1  
sign(-4) = -1  

So:
**X = [ +1, -1 ] = X₁**

---

# ✔ Final Result
The BAM network successfully recalled both directions:

X₁ → Y₁  
Y₁ → X₁  

This confirms **stable bidirectional memory**.
bam_intro.md
