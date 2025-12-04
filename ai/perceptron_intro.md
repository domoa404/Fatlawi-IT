
# 🧠 Perceptron – The First Step in Neural Networks

## 1. Historical Context
- **Inventor:** Frank Rosenblatt (1928–1971), American psychologist  
- **Year:** 1957  
- **Platform:** IBM 704 computer at Cornell Aeronautical Laboratory  
- **Significance:**  
  - First computational model inspired by biological neurons  
  - Considered the foundation of modern neural networks  

---

## 2. Biological Inspiration
Neurons in the human brain can:
- Receive input through electrical signals  
- Process and store information  
- Make decisions based on previous input  

**Perceptron idea:**  
Simulate this biological behavior using a simple computational model that can **learn** and **decide**.

---

## 3. Structure of a Perceptron
A perceptron consists of:

### 🔹 Inputs
- Binary values (0 or 1)

### 🔹 Weights
- Each input has a weight showing its importance

### 🔹 Summation
- Multiply each input × its weight  
- Add them together → “Weighted Sum”

### 🔹 Threshold
- If weighted sum > threshold → **output = 1 (true/yes)**  
- Else → **output = 0 (false/no)**  

### 🔹 Output  
- A single binary decision (0 or 1)

---

## 4. Perceptron Algorithm (Simplified)
1. Set a threshold value  
2. Multiply each input by its weight  
3. Sum all weighted inputs  
4. Apply activation function  
   - If sum > threshold → output = **1**  
   - Else → output = **0**

---

## 5. Example (Concert Decision)

Imagine a perceptron deciding **“Should I go to the concert?”**  
Inputs represent yes/no facts:

| Input | Meaning                | Value |
|-------|-------------------------|--------|
| x1    | Artist is good          | 1      |
| x2    | Weather is good         | 0      |
| x3    | Ticket price is okay    | 1      |
| x4    | Transportation available| 0      |
| x5    | Friends are going       | 1      |

Weights:

w1 = 0.7
w2 = 0.6
w3 = 0.5
w4 = 0.3
w5 = 0.4

### Step-by-step:

#### 1. Threshold  

threshold = 1.5

#### 2. Multiply inputs × weights  

1 × 0.7 = 0.7
0 × 0.6 = 0
1 × 0.5 = 0.5
0 × 0.3 = 0
1 × 0.4 = 0.4

#### 3. Sum results  

Weighted Sum = 0.7 + 0 + 0.5 + 0 + 0.4 = 1.6

#### 4. Activation Function  

1.6 > 1.5 → Output = TRUE

**Decision:** ✔ "Yes, I will go to the concert."

---

## 6. Simple Code Example (JavaScript)


javascript

const threshold = 1.5;
const inputs = [1, 0, 1, 0, 1];
const weights = [0.7, 0.6, 0.5, 0.3, 0.4];

let sum = 0;

for (let i = 0; i < inputs.length; i++) {
  sum += inputs[i] * weights[i];
}

const activate = (sum > threshold);

console.log("Weighted Sum:", sum);
console.log("Decision:", activate ? "Go to the Concert" : "Don't Go");


