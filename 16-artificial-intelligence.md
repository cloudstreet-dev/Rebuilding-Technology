# Chapter 16: Artificial Intelligence and Machine Learning

## Why AI Matters for Rebuilding

Artificial Intelligence—systems that can learn, reason, and make decisions—was among humanity's most powerful technologies by 2025. AI enabled:
- **Automation**: Systems that operate without constant human guidance
- **Optimization**: Finding best solutions to complex problems
- **Prediction**: Forecasting from data patterns
- **Understanding**: Processing language, vision, and other human-like tasks
- **Discovery**: Finding patterns humans miss

Post-collapse, AI can:
- Optimize resource allocation (food, energy, manufacturing)
- Accelerate scientific discovery
- Automate dangerous or tedious work
- Enhance decision-making
- Preserve and organize knowledge

But AI requires significant computational resources and expertise. This chapter provides a roadmap from simple rule-based systems to modern neural networks.

## AI Fundamentals

### What Is Intelligence?

**Natural Intelligence** (Humans, Animals):
- Learn from experience
- Reason and plan
- Solve problems
- Communicate
- Adapt to new situations

**Artificial Intelligence**: Systems exhibiting these capabilities
- Narrow AI: Specific tasks (chess, image recognition)
- General AI (AGI): Human-level across all domains (not achieved by 2025)
- Superintelligence: Beyond human level (theoretical)

### AI Approaches

**Symbolic AI** (GOFAI - "Good Old-Fashioned AI"):
- Explicit rules and logic
- Knowledge representation (facts, rules, relationships)
- Reasoning engines (logical inference)
- Expert systems
- Dominant 1960s-1980s
- Advantages: Explainable, precise for well-defined domains
- Disadvantages: Brittle, can't handle uncertainty, hard to encode all knowledge

**Machine Learning (ML)**:
- Learn from data (don't explicitly program rules)
- Statistical patterns
- Dominant 1990s-2020s+
- Advantages: Handles uncertainty, scales with data, discovers patterns
- Disadvantages: Requires lots of data, less explainable ("black box")

**Hybrid**: Combine symbolic and learning approaches

## Early AI: Rule-Based Systems

### Expert Systems

**Concept**: Encode human expertise as rules

**Structure**:
1. **Knowledge Base**: Facts and rules
   - Facts: "Temperature is 102°F"
   - Rules: "IF temperature > 100°F THEN patient has fever"
2. **Inference Engine**: Apply rules to facts
   - Forward chaining: Start with facts, derive conclusions
   - Backward chaining: Start with goal, find supporting facts
3. **User Interface**: Query and explanation

**Example: Medical Diagnosis**

**Knowledge Base**:
```
Rule 1: IF patient has fever AND patient has cough
        THEN patient might have flu
Rule 2: IF patient has fever AND patient has rash
        THEN patient might have measles
Rule 3: IF patient has chest pain AND shortness of breath
        THEN patient might have heart problem (urgent)
...
```

**Inference** (Forward Chaining):
1. User inputs: "Fever: yes, Cough: yes"
2. System matches Rule 1
3. Concludes: "Patient might have flu"
4. Recommends: "Rest, fluids, fever reducer"

**Building Expert System**:

**Components**:
- Rule parser (read rules from file)
- Fact storage (database or in-memory)
- Inference engine (apply rules)
- Explanation (show which rules fired)

**Implementation** (Simplified):
```python
# Facts
facts = {'fever': True, 'cough': True}

# Rules (if-then pairs)
rules = [
    ({'fever': True, 'cough': True}, 'flu'),
    ({'fever': True, 'rash': True}, 'measles'),
    # ... more rules
]

# Inference (simple forward chaining)
def infer(facts, rules):
    conclusions = []
    for conditions, conclusion in rules:
        if all(facts.get(k) == v for k, v in conditions.items()):
            conclusions.append(conclusion)
    return conclusions

# Run
print(infer(facts, rules))  # Output: ['flu']
```

**Effort**: 1,000-10,000 lines for full system (with explanation, user interface, rule editor)

**Historic Examples**:
- MYCIN (1970s): Medical diagnosis
- DENDRAL (1960s): Chemical structure analysis
- XCON (1980s): Configure computer systems

**Advantages**:
- Codify expert knowledge
- Preserve expertise
- Consistent decisions
- Explainable

**Disadvantages**:
- Manual rule creation (tedious)
- Brittle (doesn't handle unknowns well)
- Maintenance (rules conflict, grow complex)

**Post-Collapse Use**:
- Medical diagnosis (preserve medical knowledge)
- Agriculture (crop disease identification, planting advice)
- Manufacturing (quality control, troubleshooting)
- Legal/administrative (decision support)

### Planning and Search

**Problem**: Find sequence of actions to achieve goal

**State Space Search**:
- States: Configurations of the world
- Actions: Transitions between states
- Goal: Desired state
- Search: Find path from initial state to goal

**Algorithms**:

**Breadth-First Search (BFS)**:
- Explore all states at depth N before depth N+1
- Guarantees shortest path
- Memory intensive (stores all frontier)

**Depth-First Search (DFS)**:
- Explore one branch deeply before backtracking
- Less memory
- May not find shortest path

**A\* (A-Star)**:
- Best-first search with heuristic
- f(n) = g(n) + h(n)
  - g(n): Cost to reach state n
  - h(n): Estimated cost from n to goal (heuristic)
- Optimal if heuristic is admissible (never overestimates)

**Example: Route Finding**

**Problem**: Find path from A to B on map

**States**: Locations (cities, intersections)
**Actions**: Roads connecting locations
**Cost**: Distance or time
**Heuristic**: Straight-line distance to goal

**A\* Implementation** (Simplified):
```python
import heapq

def a_star(start, goal, neighbors, cost, heuristic):
    # Priority queue: (f_score, current_node)
    frontier = [(heuristic(start, goal), start)]
    came_from = {}
    g_score = {start: 0}

    while frontier:
        _, current = heapq.heappop(frontier)

        if current == goal:
            # Reconstruct path
            path = []
            while current in came_from:
                path.append(current)
                current = came_from[current]
            return path[::-1]

        for neighbor in neighbors(current):
            tentative_g = g_score[current] + cost(current, neighbor)
            if neighbor not in g_score or tentative_g < g_score[neighbor]:
                g_score[neighbor] = tentative_g
                f_score = tentative_g + heuristic(neighbor, goal)
                heapq.heappush(frontier, (f_score, neighbor))
                came_from[neighbor] = current

    return None  # No path found
```

**Uses**:
- Route planning (navigation)
- Logistics (delivery routes)
- Robotics (motion planning)
- Game AI (pathfinding)
- Manufacturing (scheduling)

## Machine Learning Fundamentals

### Supervised Learning

**Concept**: Learn from labeled examples
- Training data: (input, correct output) pairs
- Goal: Predict output for new inputs

**Example**: Image classification
- Training: 1,000 images of cats (labeled "cat"), 1,000 of dogs (labeled "dog")
- Learn: Model that distinguishes cats from dogs
- Predict: New image → "cat" or "dog"

**Algorithms**:

**Linear Regression** (Simplest):
- Fit straight line (or hyperplane) to data
- Predict continuous value

**Example**: Predict house price from size
```
Price = a × Size + b
```
Find a and b that minimize error on training data.

**Implementation**:
```python
import numpy as np

# Training data: sizes and prices
sizes = np.array([1000, 1500, 2000, 2500, 3000])
prices = np.array([200k, 280k, 350k, 425k, 500k])

# Fit line: price = a * size + b
# Using least squares
a, b = np.polyfit(sizes, prices, 1)

# Predict
new_size = 1800
predicted_price = a * new_size + b
```

**Logistic Regression** (Classification):
- Predict probability of class
- Sigmoid function squashes output to [0, 1]
- Example: Spam detection (spam or not spam)

**Decision Trees**:
- Tree structure: Nodes test features, leaves predict class
- Example:
  ```
  Is temperature > 30°C?
    Yes: Is humidity > 70%?
      Yes: Predict rain
      No: Predict sunny
    No: Is wind > 20 mph?
      Yes: Predict cloudy
      No: Predict clear
  ```
- Intuitive, explainable
- Can overfit (memorize training data)

**Random Forests**:
- Many decision trees (ensemble)
- Each tree trained on random subset of data and features
- Vote or average predictions
- Reduces overfitting, improves accuracy

**Support Vector Machines (SVM)**:
- Find hyperplane that best separates classes
- Maximize margin (distance to nearest points)
- Handle non-linear boundaries with kernel trick

**k-Nearest Neighbors (k-NN)**:
- Find k closest training examples
- Predict: Majority class (classification) or average (regression)
- Simple, no training phase
- Slow prediction (must search all training data)

### Unsupervised Learning

**Concept**: Find patterns in unlabeled data
- No correct outputs provided
- Discover structure

**Clustering**:
- Group similar data points

**k-Means**:
1. Choose k cluster centers (random or heuristic)
2. Assign each point to nearest center
3. Recalculate centers (mean of assigned points)
4. Repeat until convergence

**Uses**:
- Customer segmentation
- Organize documents
- Image compression (cluster colors)

**Dimensionality Reduction**:
- Reduce features while preserving information
- Principal Component Analysis (PCA): Find directions of maximum variance

**Uses**:
- Visualization (2D or 3D projection of high-dimensional data)
- Noise reduction
- Speed up other algorithms

### Neural Networks

**Inspiration**: Simplified model of brain
- Neurons connected by synapses
- Learn by adjusting connection strengths

**Artificial Neuron** (Perceptron):
```
Inputs: x1, x2, ..., xn
Weights: w1, w2, ..., wn
Bias: b

Output: y = activation(w1*x1 + w2*x2 + ... + wn*xn + b)
```

**Activation Function**: Non-linearity
- Sigmoid: 1 / (1 + e^(-x))  [0 to 1]
- ReLU: max(0, x)  [0 to infinity]
- Tanh: (e^x - e^(-x)) / (e^x + e^(-x))  [-1 to 1]

**Multilayer Perceptron (MLP)**:
- Input layer → Hidden layer(s) → Output layer
- Each neuron connected to all neurons in next layer (fully connected)

**Example** (3-layer network for XOR):
```
Input Layer (2 neurons)
   ↓
Hidden Layer (2-4 neurons)
   ↓
Output Layer (1 neuron)
```

**Training**: Backpropagation
1. Forward pass: Compute output
2. Calculate error (output vs. target)
3. Backward pass: Propagate error back through network
4. Update weights to reduce error (gradient descent)

**Implementation** (Simplified):
```python
import numpy as np

def sigmoid(x):
    return 1 / (1 + np.exp(-x))

def sigmoid_derivative(x):
    return x * (1 - x)

# Network structure: 2 inputs, 2 hidden, 1 output
input_size = 2
hidden_size = 2
output_size = 1

# Initialize weights randomly
weights_input_hidden = np.random.randn(input_size, hidden_size)
weights_hidden_output = np.random.randn(hidden_size, output_size)

# Training data (XOR)
X = np.array([[0, 0], [0, 1], [1, 0], [1, 1]])
y = np.array([[0], [1], [1], [0]])

# Training
learning_rate = 0.5
for epoch in range(10000):
    # Forward pass
    hidden = sigmoid(np.dot(X, weights_input_hidden))
    output = sigmoid(np.dot(hidden, weights_hidden_output))

    # Calculate error
    output_error = y - output

    # Backpropagation
    output_delta = output_error * sigmoid_derivative(output)
    hidden_error = output_delta.dot(weights_hidden_output.T)
    hidden_delta = hidden_error * sigmoid_derivative(hidden)

    # Update weights
    weights_hidden_output += hidden.T.dot(output_delta) * learning_rate
    weights_input_hidden += X.T.dot(hidden_delta) * learning_rate

# Test
print(output)  # Should be close to [[0], [1], [1], [0]]
```

**Effort**: Small networks (10s of neurons) easy to implement. Large networks (100,000s+) need optimized libraries.

## Deep Learning

**Deep Neural Networks**: Many hidden layers (10-100+)

**Why Deep**:
- Learn hierarchical representations
- Low layers: Simple features (edges, colors)
- Middle layers: Parts (eyes, wheels)
- High layers: Complex concepts (faces, cars)

**Challenges**:
- Vanishing gradients (error signal diminishes in deep networks)
- Requires large datasets (millions of examples)
- Computationally expensive (billions of operations per training step)

**Breakthroughs** (2010s):
- ReLU activation (helps gradients)
- Dropout (prevents overfitting)
- Batch normalization (stabilizes training)
- GPUs (parallel computation, 10-100× speedup)
- Large datasets (ImageNet, Common Crawl)

### Convolutional Neural Networks (CNNs)

**For Image and spatial data**:
- **Convolutional layers**: Detect local patterns (edges, textures)
- **Pooling layers**: Reduce size, increase robustness
- **Fully connected layers**: Final classification

**Example** (Image Classification):
```
Input (32×32×3 RGB image)
  ↓
Conv layer (detect edges)
  ↓
Pooling (reduce to 16×16)
  ↓
Conv layer (detect shapes)
  ↓
Pooling (reduce to 8×8)
  ↓
Fully connected
  ↓
Output (10 classes)
```

**Applications**:
- Image classification
- Object detection
- Face recognition
- Medical imaging

**Computational Cost**: High (millions to billions of operations per image)

### Recurrent Neural Networks (RNNs)

**For sequential data** (time series, text, audio):
- **Recurrent connections**: Output feeds back as input
- **Memory**: Maintains state across sequence

**Variants**:
- **LSTM** (Long Short-Term Memory): Gates control information flow, better long-term memory
- **GRU** (Gated Recurrent Unit): Simplified LSTM

**Applications**:
- Language modeling (predict next word)
- Machine translation
- Speech recognition
- Time series prediction (stock prices, weather)

### Transformers (Modern Architecture)

**Attention Mechanism**: Weigh importance of different inputs
- "Attend to" relevant parts of input

**Transformer** (2017):
- Self-attention: Each position attends to all positions
- Parallel (unlike RNN sequential)
- Scalable to huge models

**Applications**:
- Language models (GPT, BERT)
- Machine translation
- Image generation (Vision Transformers)

**By 2025**: Dominated NLP and increasingly other domains

**GPT** (Generative Pre-trained Transformer):
- Trained on huge text corpus
- Billions of parameters (GPT-3: 175 billion)
- Few-shot learning (learn new tasks from few examples)
- Can write, answer questions, translate, code, etc.

**Computational Cost**: Extreme
- Training GPT-3: ~$4-5 million, thousands of GPUs, weeks
- Inference (running model): Still expensive (hundreds of dollars per hour for large models)

## Practical AI for Post-Collapse

### Early Stages (Years 10-30)

**What's Achievable**:
- Expert systems (rules-based)
- Simple machine learning (linear/logistic regression, decision trees)
- k-Nearest neighbors
- Clustering

**Hardware**:
- Early computers (8-bit to 32-bit)
- Limited memory (kilobytes to megabytes)
- Slow (1-10 MHz)

**Applications**:
- Medical diagnosis expert systems
- Crop/livestock management
- Resource optimization (linear programming)
- Simple forecasting (regression)

**Implementation**:
- Write from scratch in C or assembly
- Or port existing algorithms
- No frameworks, libraries minimal

### Middle Stages (Years 30-60)

**What's Achievable**:
- Multilayer perceptrons (small networks, 10-1000 neurons)
- Support Vector Machines
- Random Forests
- Basic computer vision (simple filters, edge detection)
- Basic NLP (keyword matching, simple parsing)

**Hardware**:
- Modern-ish computers (GHz CPUs)
- Memory: 100s of MB to GB
- Possibly GPUs (if graphics cards salvaged or manufactured)

**Applications**:
- Image classification (medical imaging, quality control)
- Speech recognition (limited vocabulary)
- Predictive maintenance
- Advanced optimization

**Implementation**:
- C/C++ libraries (write basic matrix operations)
- Or use salvaged libraries (NumPy, etc. if Python available)

### Advanced Stages (Years 60-100+)

**What's Achievable**:
- Deep neural networks (CNNs, RNNs, Transformers)
- Large models (millions to billions of parameters)
- Computer vision (object detection, segmentation)
- NLP (language models, translation)
- Reinforcement learning (game AI, robotics)

**Hardware**:
- Powerful CPUs (multi-core, GHz)
- GPUs (thousands of cores, optimized for parallel math)
- Memory: 10s of GB
- Storage: Terabytes (for datasets)

**Applications**:
- Autonomous vehicles
- Advanced robotics
- Scientific discovery (drug design, materials science)
- Language translation
- Creative AI (art, music, writing)

**Implementation**:
- Frameworks: TensorFlow, PyTorch (salvage or rewrite)
- Optimized libraries: BLAS, cuDNN
- Distributed training (multiple machines)

## Building AI Infrastructure

### Datasets

**Critical**: AI learns from data
- Large, diverse, labeled datasets

**Post-Collapse Challenges**:
- Pre-collapse datasets on hard drives/SSDs (preserve these!)
- Collecting new data (images, text, sensor data)
- Labeling (time-consuming, requires human effort)

**Strategies**:
- Preserve existing datasets (ImageNet, Common Crawl, Wikipedia, scientific corpora)
- Crowdsource labeling (distribute work across community)
- Transfer learning (pre-trained models, fine-tune on small new dataset)
- Self-supervised learning (learn from unlabeled data)

### Compute

**Requirements**:
- Floating-point operations (multiply, add)
- Matrix operations (dot product, convolution)
- Massive parallelism (modern DNNs)

**CPUs**: Good for small models, sequential tasks
**GPUs**: 10-100× faster for DNNs (thousands of parallel cores)
**TPUs** (Tensor Processing Units): Google's custom AI chips (even faster)

**Post-Collapse**:
- Salvaged GPUs (gaming, workstation cards)
- Or build custom AI accelerators (once IC capability matures)
- Distributed: Multiple machines working together

### Software Libraries

**Linear Algebra**:
- BLAS (Basic Linear Algebra Subprograms): Matrix operations
- LAPACK: Higher-level linear algebra

**DL Frameworks**:
- TensorFlow (Google)
- PyTorch (Meta/Facebook)
- JAX (Google)
- Others: Keras, Caffe, MXNet

**Salvage**: Pre-collapse software on hard drives
**Or Build**: Reimplement algorithms (major effort, but achievable)

### Training vs. Inference

**Training**: Learning from data
- Expensive (hours to weeks)
- Needs large compute, datasets
- Done once (or periodically)

**Inference**: Running trained model
- Cheap (milliseconds to seconds)
- Smaller compute
- Done repeatedly

**Strategy**: Train on powerful machines (or salvaged data centers), deploy to smaller devices

## AI Ethics and Safety

### Concerns

**Bias**: AI learns biases from data
- Example: Hiring AI discriminates if trained on biased historical data
- Mitigation: Diverse datasets, fairness metrics, human oversight

**Transparency**: DNNs are "black boxes"
- Hard to understand why decision made
- Critical for medical, legal, safety applications
- Mitigation: Explainable AI (simpler models, visualization, attention mechanisms)

**Safety**: AI making wrong decisions
- Autonomous vehicles: Accidents
- Medical AI: Misdiagnosis
- Mitigation: Testing, validation, human in loop

**Alignment**: Ensuring AI does what we want
- Superintelligent AI could be dangerous if goals misaligned
- Post-collapse: Focus on narrow AI (specific tasks), not AGI initially

**Economic**: Automation displaces workers
- Post-collapse: Labor shortage more likely, so automation beneficial
- But ensure benefits distributed

### Recommendations

1. **Start with explainable AI** (rules, simple ML)
2. **Test thoroughly** before deployment
3. **Human oversight** for critical decisions
4. **Document biases** in datasets
5. **Establish ethics guidelines** as capability grows

## Rebuilding AI: Roadmap

### Stage 1 (Year 10-20): Expert Systems
- Rules-based AI
- Simple machine learning
- Preserve AI knowledge
- Small datasets (local collection)

### Stage 2 (Year 20-40): Classical ML
- SVM, Random Forest, small neural networks
- Computer vision (basic)
- NLP (keyword-based)
- Moderate datasets (regional)

### Stage 3 (Year 40-70): Deep Learning (Early)
- CNNs for vision
- RNNs for sequences
- Models: thousands to millions of parameters
- Large datasets (continental)
- GPUs (salvaged or early custom)

### Stage 4 (Year 70-100): Modern AI
- Transformers
- Large language models (smaller than GPT-3 but capable)
- Reinforcement learning
- Robotics
- Scientific AI

### Stage 5 (Year 100+): Advanced AI
- Models rivaling pre-collapse (GPT-3, GPT-4 equivalent)
- Multimodal AI (vision, language, audio integrated)
- Possible AGI (human-level general intelligence)

## Practical Projects

### Project 1: Simple Expert System

**Medical diagnosis**:
- 50-100 rules
- Disease identification
- Treatment recommendations

**Effort**: 1,000 lines of code

### Project 2: Linear Regression

**Predict crop yield**:
- Features: Rainfall, temperature, fertilizer
- Target: Yield
- Train on historical data

**Effort**: 100 lines of code (with library), 500 from scratch

### Project 3: Image Classifier (Simple)

**k-NN or decision tree**:
- Features: Pixel values or handcrafted (histogram, edges)
- Classes: Types of crops, diseases, products

**Effort**: 500-2,000 lines

### Project 4: Neural Network

**Small MLP**:
- 2-layer network, 100 neurons
- Classify simple data (handwritten digits, simple images)

**Effort**: 1,000-5,000 lines (from scratch), 100-500 with library

### Project 5: CNN (Advanced)

**Image classification**:
- 5-10 convolutional layers
- 1,000-class dataset (or smaller)
- Requires GPU or patient CPU training

**Effort**: 10,000+ lines from scratch, 500-1,000 with framework

## Conclusion

AI is the technology multiplier. It enables:
- Automation (do more with less labor)
- Optimization (make best use of limited resources)
- Discovery (find solutions faster)
- Preservation (organize and access knowledge)

But AI requires foundation:
1. **Mathematics**: Linear algebra, calculus, probability, statistics
2. **Programming**: Implement algorithms efficiently
3. **Compute**: Powerful CPUs/GPUs
4. **Data**: Large, quality datasets

**Key Principle**: Start simple. Rules-based systems preserve and apply expertise immediately. Machine learning adds pattern recognition. Deep learning enables human-level perception and generation. Each stage builds on the previous.

AI will take decades to rebuild to 2025 levels. But even simple AI (expert systems, linear models) provides enormous value. Don't wait for perfect capability—deploy what you can build, and improve over time.

**Final Thought**: AI is crystallized intelligence. The algorithms in this chapter represent millennia of human mathematical and computational thought. Preserve them. Implement them. Use them. They're as valuable as any physical technology for rebuilding civilization.

The road to AI is long. But with each rule added to an expert system, each model trained, each prediction made, you're giving your civilization a tool that multiplies human capability. That's the path from collapse back to flourishing.
