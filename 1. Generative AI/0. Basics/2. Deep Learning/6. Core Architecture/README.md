
# 🧠 Deep Learning - Section D: Core Architectures

Deep Learning mein **different types ke neural network architectures** use kiye jaate hain depending on **data ka nature**.

Example:

- Images → CNN
- Text / Time series → RNN / Transformers
- Tabular data → FNN
- Compression / Representation learning → Autoencoders

Har architecture ek **specific problem type** solve karne ke liye design kiya gaya hai.

---

# 23. Feedforward Neural Networks (FNN)

Feedforward Neural Networks ko **Multi‑Layer Perceptrons (MLPs)** bhi bola jata hai.

Ye **sabse basic neural network architecture** hai.

Structure:

Input → Hidden Layers → Output

Data **sirf ek direction mein flow karta hai**.

Koi memory nahi hoti.
Koi loops nahi hote.

---

## 🧠 First Principles

Har layer basically ye operation karti hai:

y = activation(Wx + b)

Yahan:

- W = weights  
- x = input  
- b = bias  
- activation = non‑linear function (ReLU, sigmoid etc)

Iska matlab:

Har layer input ko **transform karti hai**.

---

## Example

Suppose:

Tum predict karna chahte ho **house price**.

Input features:

- house size
- number of rooms
- location score
- age of building

Network:

Input Layer → Hidden Layer → Output

Output:

Predicted price.

---

## Use Cases

FNN best kaam karta hai:

- Tabular datasets
- Finance predictions
- Risk scoring
- Customer churn prediction

Example:

Bank predict kar raha hai:

"Customer loan default karega ya nahi?"

---

💡 Important

FNN basically **foundation architecture** hai.

Almost har modern architecture (CNN, Transformer) internally **MLP layers use karta hai**.

---

# 24. Convolutional Neural Networks (CNN)

CNN specially design kiya gaya hai **image aur spatial data** ke liye.

Example:

- images
- video frames
- satellite images
- medical scans

---

## Problem with FNN for Images

Suppose ek image hai:

224 × 224 × 3

Total pixels:

150,000+

Agar FNN use karoge:

Har pixel har neuron se connect hoga.

Matlab:

**Millions of parameters**.

Training extremely slow ho jayegi.

---

## CNN Solution

CNN use karta hai:

**Convolution Filters**.

Filter ek small matrix hota hai jo image par slide karta hai.

Example:

3 × 3 filter

Ye detect karta hai:

- edges
- corners
- textures
- patterns

---

## Convolution Example

Image ka small part:

[ 1 1 0 ]
[ 0 1 1 ]
[ 1 0 0 ]

Filter apply hota hai aur produce karta hai:

**feature map**.

Feature map batata hai:

"Image mein kaha pattern exist karta hai".

---

## CNN Architecture

Typical pipeline:

Image  
↓
Convolution Layer  
↓
Activation (ReLU)  
↓
Pooling Layer  
↓
Fully Connected Layer

---

## Pooling Layer

Pooling ka kaam hai:

**image size reduce karna**.

Example:

Max Pooling

2 × 2 region ka **maximum value select karta hai**.

Benefits:

- computation reduce
- overfitting reduce
- important features preserve

---

## Real World Use Cases

CNN use hota hai:

- Face recognition
- Self driving cars
- Medical imaging
- Satellite analysis
- Object detection

Example:

Self‑driving car detect karta hai:

- pedestrian
- traffic sign
- road lanes

---

💡 Interesting Fact

Many early generative AI systems jaise:

- image generators
- GANs

CNN encoders/decoders use karte the.

---

# 25. Recurrent Neural Networks (RNN)

RNN design hua hai **sequential data** ke liye.

Sequential data matlab:

Data jisme **order matter karta hai**.

Example:

- text
- speech
- stock prices
- weather data

---

## Why FNN / CNN Fail for Sequences

Suppose sentence hai:

"I grew up in France so I speak fluent ____."

Correct word:

French.

Agar model ko pehle words yaad hi nahi hain,
toh prediction impossible hai.

---

## RNN Idea

RNN introduce karta hai:

**memory**.

Har time step par model ko milta hai:

- current input
- previous hidden state

Matlab model ko **past information yaad rehti hai**.

---

## RNN Formula

Hidden state update:

h_t = f(Wx + Uh + b)

Yahan:

- x = current input
- h = previous state

---

## Example

Sentence processing:

Input sequence:

"I → love → machine → learning"

Model step by step read karta hai.

Har step par context accumulate hota hai.

---

## Use Cases

RNN use hota tha:

- language modeling
- speech recognition
- machine translation
- time series forecasting

---

## Limitations

RNN ki biggest problem:

**Vanishing gradient**.

Agar sequence bahut long ho:

Model early information forget kar deta hai.

---

Example:

Sentence:

"I grew up in France ... therefore I speak fluent French."

"France" aur "French" ke beech distance zyada ho toh RNN struggle karta hai.

---

💡 Solution later aaya:

- LSTM
- GRU
- Transformers

---

# 26. Autoencoders

Autoencoder ek **unsupervised neural network** hai.

Iska goal hai:

Input ko **compress karna aur phir reconstruct karna**.

---

## Architecture

Autoencoder ke 2 parts hote hain:

Encoder  
Decoder

Input → Encoder → Latent Vector → Decoder → Output

---

## Encoder

Encoder input ko convert karta hai:

High dimensional data → low dimensional representation.

Example:

Image

784 pixels → 32 numbers

---

## Latent Space

Latent space basically **compressed representation** hoti hai.

Ye data ke **important features capture karti hai**.

---

## Decoder

Decoder ka kaam hai:

Latent vector se original input reconstruct karna.

Goal:

Output ≈ Input

---

## Training Objective

Loss function:

Reconstruction loss

Example:

Mean Squared Error

---

## Example

Original Image:

Cat image

Encoder compress karta hai → 64 numbers

Decoder reconstruct karta hai → Cat image

---

## Use Cases

Autoencoders use hote hain:

- Dimensionality reduction
- Image denoising
- Anomaly detection
- Feature extraction

---

## Example: Fraud Detection

Bank transactions:

Normal transactions → reconstruction error low

Fraud transactions → reconstruction error high

Isse anomalies detect ki ja sakti hain.

---

💡 Important

Autoencoders generative models ka foundation bhi hain.

Example:

- Variational Autoencoders
- Diffusion model components

---

# 27. When to Use What?

| Architecture | Best For | Strength |
|--------------|----------|----------|
| FNN | Tabular data | Simple and flexible |
| CNN | Images / vision | Spatial feature learning |
| RNN | Sequences | Temporal memory |
| Autoencoder | Compression / anomalies | Latent representation learning |

---

# Key Intuition

Different data types ke liye different architectures design kiye gaye hain.

Example:

Image:

Pixels ka **spatial relationship** important hota hai → CNN

Sentence:

Words ka **order important** hota hai → RNN / Transformer

Tabular dataset:

Simple feature relationships → FNN

---

# Real World Evolution

Neural network architectures evolve hue:

FNN  
↓  
CNN  
↓  
RNN  
↓  
LSTM / GRU  
↓  
Transformers

Aaj ke modern AI systems (LLMs, GPT, etc.) mostly **Transformers use karte hain**.

---

# ✅ Summary

Deep Learning architectures data ke nature ke according design kiye jaate hain.

FNN:

Basic neural network for structured data.

CNN:

Best for images aur spatial pattern detection.

RNN:

Sequential aur time‑dependent data ke liye.

Autoencoders:

Compression aur representation learning ke liye.

In sab architectures ko samajhna important hai before moving to **Transformers and modern generative AI systems**.

---

# 🧭 Next Section

Section E – Practical Concepts in Deep Learning

Topics:

- Transfer Learning
- GPUs and hardware acceleration
- Deep Learning frameworks
- Fine tuning models
