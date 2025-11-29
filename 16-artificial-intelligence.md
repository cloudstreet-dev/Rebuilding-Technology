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

**Cross-References**: This chapter builds on Chapter 9 (Building Computers) for hardware, Chapter 13 (Programming) for software implementation, and connects to Chapter 3.5 (Medicine) and Chapter 3.2 (Agriculture) for applications. See Chapter 11 (Storage) for dataset preservation requirements.

## Computational Requirements: What AI Actually Costs

Before discussing AI algorithms, understand what's computationally achievable at each stage of rebuilding.

### Operations and Memory

**FLOPS** (Floating Point Operations Per Second): The fundamental measure

| Hardware Era | Approximate FLOPS | Memory | Example |
|-------------|------------------|--------|---------|
| 1970s mainframe | 1-10 MFLOPS | 1-4 MB | IBM 370 |
| 1980s PC | 0.01-0.1 MFLOPS | 64-640 KB | IBM PC, Apple II |
| Early 1990s PC | 1-10 MFLOPS | 1-16 MB | 486, early Pentium |
| Late 1990s PC | 100-500 MFLOPS | 32-256 MB | Pentium II/III |
| 2010 PC | 10-50 GFLOPS | 4-16 GB | Multi-core CPU |
| 2010 GPU | 1-5 TFLOPS | 1-6 GB | NVIDIA GTX 580 |
| 2020 GPU | 10-30 TFLOPS | 8-24 GB | NVIDIA RTX 3090 |
| 2020 AI cluster | 1-100 PFLOPS | 100+ TB | Thousands of GPUs |

**What Different Hardware Can Run**:

| Hardware Level | Achievable AI | Example Tasks |
|---------------|---------------|---------------|
| 1980s (0.1 MFLOPS, 64 KB) | Expert systems, very simple ML | Rule-based diagnosis, linear regression on tiny datasets |
| Early 1990s (10 MFLOPS, 4 MB) | Small neural nets (100s neurons), decision trees | Character recognition, simple classification |
| Late 1990s (500 MFLOPS, 128 MB) | MLPs (1000s neurons), SVMs, Random Forests | Handwriting recognition, basic speech |
| 2000s (10 GFLOPS, 1 GB) | Small CNNs, RNNs | Image classification (low-res), simple NLP |
| 2010s GPU (1 TFLOPS, 4 GB) | Deep CNNs, LSTMs | ImageNet classification, machine translation |
| 2020s GPU cluster | Large language models, diffusion models | GPT-3, Stable Diffusion, ChatGPT |

### Training vs. Inference Costs

**Training** (learning from data):
| Model Type | Parameters | Training FLOPS | Training Time (single GPU) |
|-----------|------------|---------------|---------------------------|
| Linear regression | 100s | Thousands | Milliseconds |
| Decision tree | N/A | Thousands-millions | Seconds |
| Small MLP (1000 neurons) | 10K-100K | 10^9-10^11 | Minutes-hours |
| LeNet-5 (1998 CNN) | 60K | 10^12 | Hours |
| AlexNet (2012 CNN) | 60M | 10^15 | Days |
| ResNet-50 (2015 CNN) | 25M | 10^16 | Days |
| BERT (2018 transformer) | 340M | 10^18 | Weeks |
| GPT-3 (2020) | 175B | 10^23 | Months (thousands of GPUs) |

**Inference** (running trained model once):
| Model Type | Parameters | Inference FLOPS | Time (modern CPU) |
|-----------|------------|----------------|-------------------|
| Linear regression | 100s | 100s | Microseconds |
| Decision tree | N/A | 100s | Microseconds |
| Small MLP | 100K | 100K | Milliseconds |
| LeNet-5 | 60K | 10^6 | Milliseconds |
| AlexNet | 60M | 10^9 | 100ms-1s |
| ResNet-50 | 25M | 10^10 | 100ms-1s |
| BERT | 340M | 10^11 | Seconds |
| GPT-3 | 175B | 10^12 | Minutes (needs GPU) |

**Key Insight**: Inference is 1000-1,000,000× cheaper than training. A model trained pre-collapse on massive hardware can run on modest post-collapse hardware.

### Memory Requirements

| Model | Parameters | Memory (weights only) | Memory (with activations) |
|-------|------------|----------------------|--------------------------|
| Small MLP | 100K | 400 KB | 1-10 MB |
| LeNet-5 | 60K | 240 KB | 1-5 MB |
| AlexNet | 60M | 240 MB | 1-2 GB |
| ResNet-50 | 25M | 100 MB | 500 MB-2 GB |
| BERT | 340M | 1.3 GB | 4-8 GB |
| GPT-3 | 175B | 700 GB | 1+ TB |

**Post-Collapse Implications**:
- 1980s hardware (64 KB): Can run only tiny expert systems, linear models
- 1990s hardware (4-16 MB): Can run small neural networks, decision trees
- 2000s hardware (256 MB-1 GB): Can run inference on AlexNet-size models
- Modern salvaged hardware (8+ GB): Can run most inference tasks

### Realistic Timeline

Given the computational progression in Chapter 9:

| Post-Collapse Era | Hardware Level | AI Capability |
|------------------|----------------|---------------|
| Year 5-15 | 1970s-1980s equivalent | Expert systems, simple statistics |
| Year 15-30 | Late 1980s-early 1990s | Small neural nets, decision trees |
| Year 30-50 | Late 1990s-2000s | Moderate ML, small CNNs |
| Year 50-75 | 2000s-2010s | Deep learning (smaller models) |
| Year 75-100+ | 2010s+ | Modern deep learning |

**Salvaged Hardware Exception**: If modern GPUs survive and can be powered, deep learning inference possible much earlier. Training remains limited by total compute available.

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

### Practical Expert System Domains

Expert systems are immediately valuable post-collapse because expertise is scarce. Here are domains where rule-based systems provide enormous value:

**Equipment Troubleshooting**:

When experienced technicians are rare, expert systems preserve diagnostic knowledge.

**Generator Troubleshooting Example**:
```
Rule: IF engine cranks but won't start
      AND fuel tank is not empty
      AND fuel shutoff valve is open
      THEN check fuel filter (may be clogged)

Rule: IF engine cranks but won't start
      AND spark plug is wet with fuel
      THEN spark plug is fouled OR ignition problem

Rule: IF engine runs rough at idle
      AND exhaust is black
      THEN air filter clogged OR carburetor too rich

Rule: IF engine overheats
      AND coolant level is OK
      AND fan belt is tight
      THEN check thermostat (may be stuck closed)
```

**Radio Equipment Troubleshooting**:
```
Rule: IF no receive AND no transmit
      AND power light is off
      THEN check power supply connections

Rule: IF receive OK AND transmit weak
      AND SWR meter shows high
      THEN antenna connection problem OR antenna damage

Rule: IF receive distorted AND multiple signals
      THEN check for intermodulation (strong nearby transmitter)
```

**Crop Disease Identification**:

Decision tree for plant diagnosis (see Chapter 3.2 Agriculture):

```
START: Examine affected plant part

Leaves affected?
├── Yes → Are leaves yellowing?
│   ├── Yes → Pattern?
│   │   ├── Between veins (interveinal) → Nutrient deficiency (Iron, Manganese)
│   │   ├── Starting at tips → Nitrogen deficiency
│   │   └── Uniform yellowing → Overwatering OR root disease
│   └── No → Are there spots?
│       ├── Yes → Spot color?
│       │   ├── Brown/tan → Fungal disease (apply fungicide)
│       │   ├── Black → Bacterial disease (remove affected parts)
│       │   └── Yellow halos → Viral disease (remove plant, prevent spread)
│       └── No → Are leaves wilting?
│           ├── During hot day, recover at night → Normal, increase water
│           └── Constant wilt → Root rot OR vascular disease
└── No → Examine stems, roots...
```

**Water Quality Assessment**:

Critical for public health (see Chapter 3.3):
```
Rule: IF water is cloudy AND has odor
      THEN do NOT drink without treatment
      AND test for bacteria

Rule: IF pH < 6.5
      THEN water is acidic
      AND may corrode pipes (lead risk)
      AND add lime for treatment

Rule: IF chlorine residual < 0.2 mg/L
      AND water has been stored > 24 hours
      THEN re-chlorinate before use

Rule: IF nitrate > 10 mg/L
      THEN do NOT give to infants
      AND investigate contamination source (agricultural runoff, septic)
```

**Structural Safety Evaluation**:

Post-disaster building assessment:
```
Rule: IF visible cracks in foundation
      AND cracks > 1/4 inch wide
      AND cracks are diagonal
      THEN structure may be unsafe
      AND consult engineer before occupying

Rule: IF walls are out of plumb > 1 inch per 8 feet
      THEN structural damage likely
      AND evacuate immediately

Rule: IF ceiling is sagging
      AND water stains visible
      THEN roof leak AND possible structural damage
      AND do NOT store heavy items in attic
```

**Vehicle Diagnostics**:
```
Rule: IF engine makes knocking sound
      AND sound increases with RPM
      THEN possible rod bearing failure
      AND stop engine immediately
      AND do NOT drive

Rule: IF brakes squeal
      AND squeal disappears when braking
      THEN brake pads worn
      AND replace within 500 miles

Rule: IF steering pulls to one side
      AND tire pressure is equal
      THEN alignment problem OR brake dragging
```

**Medical Triage** (see Chapter 3.5):
```
Rule: IF patient is unresponsive
      AND not breathing
      THEN begin CPR immediately
      AND this is highest priority (RED tag)

Rule: IF patient has severe bleeding
      AND bleeding is from artery (bright red, spurting)
      THEN apply tourniquet above wound
      AND this is high priority (RED tag)

Rule: IF patient can walk
      AND has minor injuries only
      THEN this is low priority (GREEN tag)
      AND direct to minor treatment area
```

**Implementation Strategy**:

1. **Start with most critical domain** for your community
2. **Interview local experts** (the old mechanic, experienced farmer, etc.)
3. **Document rules incrementally** (add rules as situations arise)
4. **Test with known cases** before relying on system
5. **Include confidence levels** ("likely", "possible", "check further")
6. **Always recommend human verification** for critical decisions

**Rule Base Size Guidelines**:

| Domain | Typical Rules | Effort |
|--------|--------------|--------|
| Simple troubleshooting | 20-50 | Days |
| Crop disease ID | 50-200 | Weeks |
| Medical diagnosis (basic) | 100-500 | Months |
| Comprehensive vehicle repair | 500-2000 | Years |

### Knowledge Acquisition: Building the Rule Base

The hardest part of expert systems isn't programming—it's getting knowledge from experts.

**The Knowledge Acquisition Bottleneck**:
- Experts know more than they can articulate
- Much knowledge is implicit ("it just feels wrong")
- Experts may disagree
- Knowledge must be validated

**Interview Techniques**:

**1. Structured Interviews**:
- Prepare specific scenarios
- Ask: "What do you check first when X happens?"
- Record exact decision sequence

**2. Think-Aloud Protocol**:
- Expert works on real problem while narrating
- "I'm looking at the color here because..."
- Captures implicit reasoning

**3. Card Sorting**:
- Write symptoms/conditions on cards
- Expert groups and prioritizes
- Reveals categorization structure

**4. Critical Incident Review**:
- Discuss past difficult cases
- "What made this one unusual?"
- Captures exception handling

**5. Teach-Back**:
- Knowledge engineer explains understanding
- Expert corrects misunderstandings
- Iterative refinement

**Documentation Template**:
```
RULE: [Unique ID]
IF:
  - [Condition 1]
  - [Condition 2]
  - ...
THEN:
  - [Conclusion/Action]
  - [Confidence: High/Medium/Low]
SOURCE: [Expert name, date]
VALIDATION: [Test cases that confirmed rule]
EXCEPTIONS: [When this rule doesn't apply]
```

**Iterative Refinement Process**:

```
1. Initial interview → Draft rules
2. Expert reviews rules → Corrections
3. Test with known cases → Find gaps
4. Additional interviews → New rules
5. Expert reviews again → Refinement
6. Deploy limited trial → Real-world feedback
7. Update rules → Repeat
```

**Conflict Resolution**:

When experts disagree:
- Document both opinions with sources
- Look for conditions that differentiate (when is expert A right vs expert B?)
- Consider confidence-weighted voting
- Test both approaches empirically

**Preserving Tacit Knowledge**:

Some knowledge resists explicit rules:
- "The sound a healthy engine makes"
- "How ripe fruit should feel"
- "When a patient looks sick"

Approaches:
- **Comparison examples**: "Like this, not like that"
- **Multimedia**: Photos, audio recordings, video
- **Training alongside system**: Expert system as teaching aid

### Fuzzy Logic

Between crisp rules and machine learning lies fuzzy logic—a way to handle imprecise concepts like "hot", "fast", or "slightly damaged".

**The Problem with Crisp Rules**:
```
IF temperature > 80°F THEN turn_on_cooling

Problem: At 79.9°F, cooling is off. At 80.1°F, it's on.
Reality: The transition should be gradual.
```

**Fuzzy Sets**:

Instead of "is member" (yes/no), fuzzy sets define "degree of membership" (0.0 to 1.0).

```
Temperature "Hot":
- 60°F: membership = 0.0 (not hot)
- 70°F: membership = 0.2 (slightly hot)
- 80°F: membership = 0.6 (fairly hot)
- 90°F: membership = 0.9 (very hot)
- 100°F: membership = 1.0 (definitely hot)
```

**Membership Functions**:

Common shapes:
```
Triangular:           Trapezoidal:          Gaussian:
    /\                  ____                   ___
   /  \                /    \                 /   \
  /    \              /      \               /     \
```

**Triangular Membership Function**:
```c
float triangular_membership(float x, float a, float b, float c) {
    // a = left foot, b = peak, c = right foot
    if (x <= a || x >= c) return 0.0f;
    if (x <= b) return (x - a) / (b - a);
    return (c - x) / (c - b);
}

// Example: "medium temperature" peaks at 70°F
// a=50, b=70, c=90
// At 60°F: (60-50)/(70-50) = 0.5
// At 70°F: 1.0
// At 80°F: (90-80)/(90-70) = 0.5
```

**Fuzzy Rules**:
```
IF temperature IS hot AND humidity IS high THEN fan_speed IS fast
IF temperature IS cold AND humidity IS low THEN fan_speed IS slow
IF temperature IS medium THEN fan_speed IS medium
```

**Fuzzy Inference Process**:

1. **Fuzzification**: Convert crisp inputs to fuzzy memberships
2. **Rule Evaluation**: Apply fuzzy AND/OR to rule antecedents
3. **Aggregation**: Combine rule outputs
4. **Defuzzification**: Convert fuzzy output to crisp value

**Example: Fan Speed Controller**

```c
// Step 1: Define membership functions
// Temperature: cold(0-60), medium(40-90), hot(70-100)
// Humidity: low(0-40), medium(30-70), high(60-100)
// Fan speed: slow(0-40), medium(30-70), fast(60-100)

float cold_membership(float temp) {
    return triangular_membership(temp, 0, 0, 60);
}
float medium_temp_membership(float temp) {
    return triangular_membership(temp, 40, 65, 90);
}
float hot_membership(float temp) {
    return triangular_membership(temp, 70, 100, 100);
}

// Step 2: Evaluate rules
float fuzzy_control(float temperature, float humidity) {
    // Get memberships
    float temp_cold = cold_membership(temperature);
    float temp_medium = medium_temp_membership(temperature);
    float temp_hot = hot_membership(temperature);
    float hum_low = low_membership(humidity);
    float hum_high = high_membership(humidity);

    // Rule 1: IF hot AND high humidity THEN fast
    float rule1 = fminf(temp_hot, hum_high);  // AND = min

    // Rule 2: IF cold AND low humidity THEN slow
    float rule2 = fminf(temp_cold, hum_low);

    // Rule 3: IF medium temp THEN medium speed
    float rule3 = temp_medium;

    // Step 3: Aggregate (simplified centroid method)
    // Each rule contributes to output region proportional to strength

    // Step 4: Defuzzify (weighted average)
    float slow_center = 20;
    float medium_center = 50;
    float fast_center = 80;

    float numerator = rule2 * slow_center +
                      rule3 * medium_center +
                      rule1 * fast_center;
    float denominator = rule2 + rule3 + rule1 + 0.001f;  // Avoid divide by zero

    return numerator / denominator;
}
```

**Fuzzy Logic Advantages**:
- Handles imprecise inputs gracefully
- Rules are human-readable
- No training data needed
- Smooth transitions (no abrupt jumps)
- Works well for control systems

**Fuzzy Logic vs. ML**:

| Aspect | Fuzzy Logic | Machine Learning |
|--------|-------------|------------------|
| Training data | Not required | Required |
| Rules | Designed by human | Learned from data |
| Interpretability | High | Low (for neural nets) |
| Precision | Moderate | Can be very high |
| Best for | Control systems, expert knowledge | Pattern recognition, prediction |

**Post-Collapse Applications**:

- **Climate control**: HVAC, greenhouse temperature
- **Vehicle control**: Speed regulation, braking
- **Process control**: Water treatment, manufacturing
- **Decision support**: When expert knowledge is fuzzy ("roughly 3 days old")

**Implementation Notes**:
- Fuzzy logic runs on any hardware (simple arithmetic)
- Pre-compute membership function parameters
- Use lookup tables for speed if needed
- Combine with expert systems for hybrid reasoning

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

### Genetic Algorithms and Evolutionary Computation

When you can't compute gradients or the solution space is complex, evolutionary algorithms find good solutions through simulated natural selection.

**Core Concepts**:

- **Individual**: One candidate solution (encoded as "chromosome")
- **Population**: Group of candidate solutions
- **Fitness**: How good is this solution? (objective function)
- **Selection**: Better individuals more likely to reproduce
- **Crossover**: Combine parts of two parents to create child
- **Mutation**: Random small changes to maintain diversity

**Basic Genetic Algorithm**:

```
1. Initialize random population
2. Evaluate fitness of each individual
3. Select parents (fitness-proportional)
4. Create children via crossover
5. Apply mutation to children
6. Replace population with children
7. Repeat until convergence or max generations
```

**Implementation**:

```c
#define POP_SIZE 100
#define GENE_LENGTH 20
#define MUTATION_RATE 0.01
#define CROSSOVER_RATE 0.7

typedef struct {
    int genes[GENE_LENGTH];  // Binary chromosome
    float fitness;
} Individual;

// Fitness function (problem-specific)
float evaluate_fitness(Individual* ind) {
    // Example: OneMax - count number of 1s
    int sum = 0;
    for (int i = 0; i < GENE_LENGTH; i++) {
        sum += ind->genes[i];
    }
    return (float)sum;
}

// Tournament selection - pick best of k random individuals
Individual* tournament_select(Individual* pop, int k) {
    Individual* best = &pop[rand() % POP_SIZE];
    for (int i = 1; i < k; i++) {
        Individual* competitor = &pop[rand() % POP_SIZE];
        if (competitor->fitness > best->fitness) {
            best = competitor;
        }
    }
    return best;
}

// Single-point crossover
void crossover(Individual* parent1, Individual* parent2,
               Individual* child1, Individual* child2) {
    int point = rand() % GENE_LENGTH;
    for (int i = 0; i < GENE_LENGTH; i++) {
        if (i < point) {
            child1->genes[i] = parent1->genes[i];
            child2->genes[i] = parent2->genes[i];
        } else {
            child1->genes[i] = parent2->genes[i];
            child2->genes[i] = parent1->genes[i];
        }
    }
}

// Mutation
void mutate(Individual* ind) {
    for (int i = 0; i < GENE_LENGTH; i++) {
        if ((float)rand() / RAND_MAX < MUTATION_RATE) {
            ind->genes[i] = 1 - ind->genes[i];  // Flip bit
        }
    }
}

// Main GA loop
void genetic_algorithm(int max_generations) {
    Individual population[POP_SIZE];
    Individual new_population[POP_SIZE];

    // Initialize random population
    for (int i = 0; i < POP_SIZE; i++) {
        for (int j = 0; j < GENE_LENGTH; j++) {
            population[i].genes[j] = rand() % 2;
        }
        population[i].fitness = evaluate_fitness(&population[i]);
    }

    for (int gen = 0; gen < max_generations; gen++) {
        // Create new population
        for (int i = 0; i < POP_SIZE; i += 2) {
            Individual* p1 = tournament_select(population, 3);
            Individual* p2 = tournament_select(population, 3);

            if ((float)rand() / RAND_MAX < CROSSOVER_RATE) {
                crossover(p1, p2, &new_population[i], &new_population[i+1]);
            } else {
                new_population[i] = *p1;
                new_population[i+1] = *p2;
            }

            mutate(&new_population[i]);
            mutate(&new_population[i+1]);

            new_population[i].fitness = evaluate_fitness(&new_population[i]);
            new_population[i+1].fitness = evaluate_fitness(&new_population[i+1]);
        }

        // Replace population
        memcpy(population, new_population, sizeof(population));
    }
}
```

**Encoding Solutions**:

Different problems require different encodings:

| Problem | Encoding | Example |
|---------|----------|---------|
| Binary optimization | Bit string | [1,0,1,1,0,0,1,0] |
| Permutation (TSP) | Integer permutation | [3,1,4,2,5,0] |
| Real parameters | Float array | [0.5, 2.3, -1.1] |
| Scheduling | Task assignments | [(task1,slot3), (task2,slot1)] |

**Crossover Variants**:

- **Single-point**: Cut at one point, swap tails
- **Two-point**: Swap middle segment
- **Uniform**: Each gene randomly from parent1 or parent2
- **Order crossover** (for permutations): Preserve relative order

**Post-Collapse Applications**:

**1. Scheduling**:
- Crop rotation planning
- Manufacturing schedules
- Work shift assignments

**2. Design Optimization**:
- Antenna design (shape, dimensions)
- Circuit component values
- Building layout

**3. Resource Allocation**:
- Distribution network design
- Load balancing
- Inventory optimization

**4. Route Optimization** (Traveling Salesman Problem):
```c
// Fitness = negative total distance (higher is better)
float tsp_fitness(int* route, float distances[N][N]) {
    float total = 0;
    for (int i = 0; i < N-1; i++) {
        total += distances[route[i]][route[i+1]];
    }
    total += distances[route[N-1]][route[0]];  // Return to start
    return -total;
}
```

**When to Use GAs**:

| Good For | Not Good For |
|----------|--------------|
| No gradient available | Smooth, differentiable problems (use gradient descent) |
| Complex, multimodal landscapes | Simple convex problems |
| Discrete/combinatorial problems | When exact methods exist |
| Exploring large search spaces | When speed is critical |

**Computational Notes**:
- GAs are "embarrassingly parallel" - fitness evaluations independent
- Simple to implement, no advanced math required
- May not find global optimum, but usually finds good solutions
- Tune parameters: population size, mutation rate, selection pressure

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

**Random Forest Post-Collapse Note**: Random Forests are "embarrassingly parallel"—each tree trains independently. On limited hardware, train trees sequentially and average. They work well with limited data, handle missing values naturally, and provide feature importance rankings. Excellent practical choice before neural networks become feasible.

**Support Vector Machines (SVM)**:
- Find hyperplane that best separates classes
- Maximize margin (distance to nearest points)
- Handle non-linear boundaries with kernel trick

**k-Nearest Neighbors (k-NN)**:
- Find k closest training examples
- Predict: Majority class (classification) or average (regression)
- Simple, no training phase
- Slow prediction (must search all training data)

**k-NN Post-Collapse Note**: With small datasets (under 1000 samples), k-NN often beats more complex methods and requires no training. Store your examples, compute distances, done. The simplicity is a feature—if your neural network fails mysteriously, k-NN provides a baseline that always works.

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

### Feature Engineering

**The Most Important Step**: Feature engineering often matters more than algorithm choice. Good features can make a simple model outperform a complex one with poor features.

**What Are Features?**

Raw data → Transformed/selected inputs for model

Example: Predicting crop yield
- **Raw data**: Daily temperature, rainfall, soil samples, planting date
- **Engineered features**: Growing degree days, cumulative rainfall, soil pH, days since planting

**Domain-Specific Feature Examples**:

**Agriculture**:
- Growing degree days: Σ max(0, (T_avg - T_base)) over season
- Cumulative rainfall in critical periods (germination, flowering)
- Soil nutrient ratios (N:P:K)
- Days since last frost

**Medical**:
- BMI from height/weight
- Blood pressure categories (normal, elevated, stage 1, stage 2)
- Symptom duration in days
- Age-adjusted values

**Equipment monitoring**:
- Rate of change (derivative) of temperature
- Vibration frequency spectrum peaks
- Time since last maintenance
- Deviation from baseline

**Feature Transformations**:

**1. Normalization/Standardization**:
```c
// Min-max normalization (scale to [0, 1])
float normalize(float x, float min_val, float max_val) {
    return (x - min_val) / (max_val - min_val);
}

// Z-score standardization (mean=0, std=1)
float standardize(float x, float mean, float std) {
    return (x - mean) / std;
}
```

**Why normalize?**
- Features on different scales can dominate (distance of 1000m vs temperature of 20°C)
- Gradient descent converges faster with normalized features
- Some algorithms (k-NN, SVM) require normalization

**2. Handling Missing Data**:
```c
// Option 1: Replace with mean
float impute_mean(float* data, int n, int missing_flag) {
    float sum = 0;
    int count = 0;
    for (int i = 0; i < n; i++) {
        if (data[i] != missing_flag) {
            sum += data[i];
            count++;
        }
    }
    return sum / count;
}

// Option 2: Replace with median (robust to outliers)
// Option 3: Create "is_missing" feature (missingness may be informative)
// Option 4: Use model that handles missing (decision trees)
```

**3. Categorical Encoding**:

**One-hot encoding** (for nominal categories):
```
Color: Red, Green, Blue

Red   → [1, 0, 0]
Green → [0, 1, 0]
Blue  → [0, 0, 1]
```

**Ordinal encoding** (for ordered categories):
```
Size: Small, Medium, Large

Small  → 0
Medium → 1
Large  → 2
```

**4. Polynomial Features** (capture non-linear relationships):
```
Original: x1, x2
Degree 2: x1, x2, x1², x2², x1*x2
```

**5. Log Transform** (for skewed distributions):
```c
// Useful for values spanning orders of magnitude (income, populations)
float log_transform(float x) {
    return logf(x + 1);  // +1 to handle x=0
}
```

**Feature Selection**:

Too many features → overfitting, slow training, noise

**Methods**:

1. **Correlation filter**: Remove features with low correlation to target
2. **Variance threshold**: Remove features with near-zero variance (constant)
3. **Recursive elimination**: Train model, remove least important features, repeat
4. **Domain knowledge**: Expert says this feature shouldn't matter

**Simple correlation-based selection**:
```c
// Compute Pearson correlation between feature and target
float correlation(float* x, float* y, int n) {
    float sum_x = 0, sum_y = 0, sum_xy = 0;
    float sum_x2 = 0, sum_y2 = 0;

    for (int i = 0; i < n; i++) {
        sum_x += x[i];
        sum_y += y[i];
        sum_xy += x[i] * y[i];
        sum_x2 += x[i] * x[i];
        sum_y2 += y[i] * y[i];
    }

    float num = n * sum_xy - sum_x * sum_y;
    float den = sqrtf((n * sum_x2 - sum_x * sum_x) *
                      (n * sum_y2 - sum_y * sum_y));
    return num / den;
}
```

**The Feature Engineering Process**:

1. **Understand the domain**: What factors actually influence the outcome?
2. **Explore raw data**: Statistics, histograms, correlations
3. **Create candidate features**: Based on domain knowledge
4. **Test features**: Does adding this improve model performance?
5. **Iterate**: Remove useless features, create new ones based on errors

**Post-Collapse Practical Notes**:
- Start with simple, interpretable features
- Domain experts are more valuable than sophisticated algorithms
- A few good features beat many mediocre ones
- Document what each feature means and why it's included

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

### Fixed-Point and Integer Neural Networks

GPUs and floating-point units may not be available post-collapse. Neural networks can run on integer-only hardware with careful design.

**Why Fixed-Point?**
- Early computers lack floating-point units (FPU)
- Integer operations 2-10× faster than float on many CPUs
- Lower power consumption
- Simpler hardware implementation

**Fixed-Point Representation** (see Chapter 13 for fundamentals):

Use Q format: Qm.n means m integer bits, n fractional bits

**Example**: Q8.8 (8 integer, 8 fractional, 16 bits total)
- Range: -128.0 to 127.996
- Resolution: 1/256 ≈ 0.004
- Value 1.5 stored as: 1.5 × 256 = 384 (0x0180)

**Fixed-Point Operations**:
```c
// Q8.8 fixed-point operations
typedef int16_t fixed_t;
#define FRAC_BITS 8
#define FIXED_ONE (1 << FRAC_BITS)  // 256

// Convert float to fixed
fixed_t float_to_fixed(float f) {
    return (fixed_t)(f * FIXED_ONE);
}

// Multiply two fixed-point numbers
fixed_t fixed_mul(fixed_t a, fixed_t b) {
    // Result needs 32 bits, then shift back
    int32_t result = (int32_t)a * (int32_t)b;
    return (fixed_t)(result >> FRAC_BITS);
}

// Add (same as integer add)
fixed_t fixed_add(fixed_t a, fixed_t b) {
    return a + b;
}
```

**Quantized Neural Networks**:

Modern technique: Train in float, convert to integer for inference.

**Quantization Approaches**:
1. **Post-training quantization**: Convert trained float model to int8
2. **Quantization-aware training**: Train knowing target is int8
3. **Binary/ternary networks**: Weights are {-1, 0, +1} only

**8-bit Quantization** (most common):
- Weights: 8-bit integers (-128 to 127)
- Activations: 8-bit integers (0 to 255 for ReLU)
- Accumulation: 32-bit integers
- Scale factors: One per layer or per channel

**Quantized Layer Computation**:
```c
// Quantized fully-connected layer
// weights: int8_t[out_features][in_features]
// input: int8_t[in_features]
// output: int8_t[out_features]
// scale: float (or fixed-point)

void quantized_linear(int8_t* input, int8_t* weights,
                      int8_t* output, int32_t* bias,
                      int in_features, int out_features,
                      int input_scale, int weight_scale, int output_scale) {
    for (int o = 0; o < out_features; o++) {
        int32_t acc = bias[o];  // 32-bit accumulator
        for (int i = 0; i < in_features; i++) {
            acc += (int32_t)input[i] * (int32_t)weights[o * in_features + i];
        }
        // Rescale and clamp to int8
        acc = (acc * input_scale * weight_scale) / output_scale;
        output[o] = (int8_t)CLAMP(acc, -128, 127);
    }
}
```

**Activation Functions Without Float**:

**ReLU** (trivial):
```c
int8_t relu(int8_t x) {
    return x > 0 ? x : 0;
}
```

**Sigmoid via Lookup Table**:
```c
// Pre-computed sigmoid table for input range [-8, 8] in Q4.4
// sigmoid(x) = 1 / (1 + exp(-x))
const uint8_t sigmoid_table[256] = {
    // Index 0 = x=-8.0, index 255 = x=7.9375
    0, 0, 0, 1, 1, 1, 2, 2, 3, 4, 5, 6, 7, 9, 11, 13,
    // ... (fill with pre-computed values)
    245, 247, 249, 250, 251, 252, 253, 253, 254, 254, 255, 255, ...
};

uint8_t sigmoid_lut(int8_t x) {
    // Map x from Q4.4 range to table index
    int index = (x + 128);  // Shift to 0-255
    return sigmoid_table[index];
}
```

**Tanh via Lookup Table**:
```c
// Similar approach, output in Q0.7 (signed)
const int8_t tanh_table[256] = { ... };
```

**Binary Neural Networks** (extreme quantization):

Weights and activations are ±1 only:
- Multiply becomes XNOR
- Sum becomes popcount
- Extremely fast on any hardware

```c
// Binary neuron: weights and inputs are packed bits
// 1 bit = +1, 0 bit = -1
uint32_t binary_neuron(uint32_t input, uint32_t weights, int num_bits) {
    // XNOR: same bits give 1, different give 0
    uint32_t xnor = ~(input ^ weights);
    // Count 1s (popcount) - this is the dot product
    int ones = __builtin_popcount(xnor);
    // Convert to signed: (2 * ones - num_bits) gives actual dot product
    return (2 * ones - num_bits);
}
```

**Accuracy vs. Precision Trade-off**:

| Precision | Typical Accuracy Loss | Memory Savings |
|-----------|----------------------|----------------|
| Float32 (baseline) | 0% | 1× |
| Float16 | 0-0.5% | 2× |
| Int8 | 1-3% | 4× |
| Int4 | 5-10% | 8× |
| Binary | 10-30% | 32× |

**Post-Collapse Recommendation**:
- For inference on salvaged weights: Use int8 quantization
- For training from scratch: May need float (software emulation if needed)
- For extremely limited hardware: Consider binary networks for simple tasks

**Hardware Without FPU**:

On CPUs without floating-point:
1. Use fixed-point for everything
2. Pre-compute activation tables
3. Accept lower precision (int8 or int16)
4. Software float emulation only for training (very slow)

**Example**: Running MNIST classifier on 8-bit micro:
- LeNet-5 with int8 weights: ~60KB
- Lookup tables for activations: ~1KB
- Works on Arduino-class hardware (slow but functional)

### Numerical Stability in Neural Networks

Naive implementations fail. Understanding numerical issues is essential for working implementations.

**Common Problems**:

**1. Overflow in Exponential (exp)**:
```c
// WRONG: This overflows for large x
float sigmoid(float x) {
    return 1.0f / (1.0f + expf(-x));  // exp(100) = infinity!
}

// RIGHT: Numerically stable sigmoid
float sigmoid_stable(float x) {
    if (x >= 0) {
        return 1.0f / (1.0f + expf(-x));
    } else {
        float e = expf(x);
        return e / (1.0f + e);  // Avoid exp of large positive number
    }
}
```

**2. Log of Zero/Small Numbers**:
```c
// WRONG: log(0) = -infinity
float cross_entropy(float predicted, float actual) {
    return -actual * logf(predicted);  // Fails if predicted = 0
}

// RIGHT: Add small epsilon
#define EPS 1e-7f
float cross_entropy_stable(float predicted, float actual) {
    return -actual * logf(predicted + EPS);
}
```

**3. Softmax Overflow** (classification output):
```c
// WRONG: exp of large numbers overflow
void softmax_naive(float* x, int n) {
    float sum = 0;
    for (int i = 0; i < n; i++) {
        x[i] = expf(x[i]);  // Overflow if x[i] > 88
        sum += x[i];
    }
    for (int i = 0; i < n; i++) x[i] /= sum;
}

// RIGHT: Subtract max first (log-sum-exp trick)
void softmax_stable(float* x, int n) {
    // Find max
    float max_val = x[0];
    for (int i = 1; i < n; i++) {
        if (x[i] > max_val) max_val = x[i];
    }
    // Subtract max before exp
    float sum = 0;
    for (int i = 0; i < n; i++) {
        x[i] = expf(x[i] - max_val);  // Now max exp is exp(0) = 1
        sum += x[i];
    }
    for (int i = 0; i < n; i++) x[i] /= sum;
}
```

**4. Gradient Explosion/Vanishing**:

In deep networks, gradients can explode (become huge) or vanish (become tiny).

**Gradient Clipping** (prevent explosion):
```c
void clip_gradients(float* gradients, int n, float max_norm) {
    // Compute gradient norm
    float norm = 0;
    for (int i = 0; i < n; i++) {
        norm += gradients[i] * gradients[i];
    }
    norm = sqrtf(norm);

    // Scale down if too large
    if (norm > max_norm) {
        float scale = max_norm / norm;
        for (int i = 0; i < n; i++) {
            gradients[i] *= scale;
        }
    }
}
```

**Weight Initialization** (prevent vanishing):
```c
// Xavier/Glorot initialization for layer with fan_in inputs, fan_out outputs
float xavier_init(int fan_in, int fan_out) {
    float limit = sqrtf(6.0f / (fan_in + fan_out));
    return random_uniform(-limit, limit);
}

// He initialization (better for ReLU)
float he_init(int fan_in) {
    float std = sqrtf(2.0f / fan_in);
    return random_normal(0, std);
}
```

**5. Batch Normalization** (stabilizes training):

Normalize activations to mean=0, variance=1:
```c
// Per-batch normalization
void batch_norm(float* x, int batch_size, int features,
                float* gamma, float* beta,  // Learned parameters
                float* mean_out, float* var_out) {  // Running stats
    for (int f = 0; f < features; f++) {
        // Compute mean
        float mean = 0;
        for (int b = 0; b < batch_size; b++) {
            mean += x[b * features + f];
        }
        mean /= batch_size;

        // Compute variance
        float var = 0;
        for (int b = 0; b < batch_size; b++) {
            float diff = x[b * features + f] - mean;
            var += diff * diff;
        }
        var /= batch_size;

        // Normalize and scale
        float std = sqrtf(var + 1e-5f);  // Epsilon for stability
        for (int b = 0; b < batch_size; b++) {
            int idx = b * features + f;
            x[idx] = gamma[f] * (x[idx] - mean) / std + beta[f];
        }

        // Update running statistics
        mean_out[f] = 0.9f * mean_out[f] + 0.1f * mean;
        var_out[f] = 0.9f * var_out[f] + 0.1f * var;
    }
}
```

**6. Learning Rate Issues**:

| Problem | Symptom | Solution |
|---------|---------|----------|
| LR too high | Loss oscillates or explodes | Reduce LR by 10× |
| LR too low | Loss decreases very slowly | Increase LR by 2-5× |
| LR constant | Converges then plateaus | Use LR decay schedule |

**Learning Rate Schedule**:
```c
float get_learning_rate(int epoch, float initial_lr) {
    // Step decay: halve LR every 30 epochs
    return initial_lr * powf(0.5f, epoch / 30);

    // Or exponential decay
    // return initial_lr * expf(-0.01f * epoch);
}
```

**Debugging Checklist**:

When your neural network doesn't work:

1. ☐ Check loss: Is it NaN or Inf? → Numerical instability
2. ☐ Check gradients: All zeros? → Vanishing gradients
3. ☐ Check gradients: Huge values? → Exploding gradients
4. ☐ Verify forward pass: Manual calculation matches code?
5. ☐ Verify backward pass: Gradient check (numerical vs analytical)
6. ☐ Print activations: Are they all the same? → Dead neurons
7. ☐ Try simpler problem: Can it learn XOR?

**Gradient Checking** (verify backprop implementation):
```c
// Numerical gradient approximation
float numerical_gradient(float (*loss_fn)(float* params), float* params,
                         int param_idx, float epsilon) {
    float original = params[param_idx];

    params[param_idx] = original + epsilon;
    float loss_plus = loss_fn(params);

    params[param_idx] = original - epsilon;
    float loss_minus = loss_fn(params);

    params[param_idx] = original;  // Restore

    return (loss_plus - loss_minus) / (2 * epsilon);
}

// Compare with analytical gradient
// Should match to ~1e-5 relative error
```

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
- Training GPT-3: ~$4-5 million, thousands of GPUs running in parallel for weeks
- This represents **massive parallelism**—a single GPU would take centuries, but 10,000 GPUs working together finish in weeks
- Such coordination (fast interconnects, synchronization, fault tolerance) is not achievable for many decades post-collapse
- **Post-collapse implication**: Training large language models from scratch is not realistic for 75-100+ years. Focus on preserving pre-trained weights and running inference.
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

### Preserving Pre-Collapse AI Artifacts

**This is time-critical**: AI models, datasets, and papers are on storage media that degrades. Preservation must begin immediately post-collapse.

**Priority 1: Model Weights (Highest Value)**

Pre-trained models encode billions of dollars of compute. Preserving weights lets you skip training.

**Models Worth Preserving** (by utility vs. size):

| Model | Size | Use | Priority |
|-------|------|-----|----------|
| BERT-base | 440 MB | Text classification, Q&A | High |
| DistilBERT | 250 MB | Lighter BERT alternative | High |
| ResNet-50 | 100 MB | Image classification | High |
| MobileNet | 14 MB | Efficient image classification | Very High |
| YOLOv5s | 14 MB | Object detection | Very High |
| Whisper-small | 460 MB | Speech recognition | High |
| GPT-2 (117M) | 500 MB | Text generation | Medium |
| Llama-7B | 13 GB | Language model | Medium (large) |
| GPT-3/4 | 700+ GB | Not practical to preserve | Low (too large) |

**Small, Useful Models** (prioritize these):
- EfficientNet-Lite: 15-60 MB, good image classification
- TinyBERT: 60 MB, compressed BERT
- SqueezeNet: 5 MB, basic image classification
- Sentence transformers: 100-400 MB, text similarity

**Storage Requirements**:
- Essential models (top 10): ~5 GB
- Comprehensive collection: ~50-100 GB
- Everything useful: ~500 GB-1 TB

**Priority 2: Datasets**

| Dataset | Size | Use |
|---------|------|-----|
| MNIST | 50 MB | Digit recognition (learning) |
| CIFAR-10/100 | 180 MB | Image classification basics |
| ImageNet (subset) | 10-50 GB | Visual features |
| Wikipedia | 20 GB (text) | General knowledge |
| Common Crawl (sample) | 10-100 GB | Web text |
| Scientific papers | 50-500 GB | Technical knowledge |

**Priority 3: Documentation and Code**

**Papers** (mathematical foundations):
- arXiv ML/AI papers (1990-2025): ~500 GB PDF
- Key papers (top 1000): ~5 GB
- Textbooks (digital): ~10 GB

**Source Code**:
- PyTorch: ~500 MB
- TensorFlow: ~1 GB
- NumPy/SciPy: ~200 MB
- scikit-learn: ~100 MB
- Algorithm implementations: Various

**Priority 4: Training Infrastructure**

- Optimized kernels (cuDNN equivalent): Enables fast training
- Compiler tools (LLVM, GCC): Build software
- Operating systems: Linux distributions

**Preservation Strategy**:

1. **Multiple copies on different media**:
   - Hard drives (3-5 year refresh needed)
   - SSDs (10+ year retention, temperature sensitive)
   - Optical media (M-DISC: 100+ year claim)
   - Printed key algorithms (paper lasts centuries)

2. **Geographic distribution**:
   - Store copies in different locations
   - Different climate zones if possible
   - Document locations for future recovery

3. **Verification**:
   - Checksums for all files
   - Periodic integrity checks
   - Test recovery process

4. **Documentation**:
   - What each file is and why it matters
   - Dependencies (what else is needed to use it)
   - How to load/run models

**What NOT to Prioritize**:
- GPT-3/4 class models: Too large (700 GB+), require infrastructure you won't have
- Raw video datasets: Huge, can re-collect
- Redundant model variants: Keep one good version per task
- Commercial/encrypted models: May be unusable

### Transfer Learning: The Key to Limited Compute

**Transfer learning is the single most important technique for post-collapse AI.** It makes the difference between "impossible" and "achievable."

**The Principle**:
- Pre-trained models have already learned general features (edges, shapes, concepts)
- Fine-tuning adapts these features to your specific task
- Requires 10-100× less data and compute than training from scratch

**Why This Matters Post-Collapse**:

| Approach | Training Data Needed | Compute Required | Time |
|----------|---------------------|------------------|------|
| Train from scratch | 100,000+ images | Weeks of GPU | Months |
| Fine-tune pre-trained | 100-1000 images | Hours of CPU | Days |

**Example**: Crop disease detection
- **From scratch**: Need thousands of labeled disease images, powerful GPU, weeks
- **Transfer learning**: Take ResNet-50 pre-trained on ImageNet, replace final layer, train on 200 local disease photos, works in hours on CPU

**Practical Transfer Learning**:

```python
# Conceptual (requires saved weights and framework)
# 1. Load pre-trained model
model = load_model("resnet50_imagenet.weights")

# 2. Remove final classification layer
model.remove_layer(-1)

# 3. Freeze early layers (keep learned features)
for layer in model.layers[:-4]:
    layer.trainable = False

# 4. Add new output layer for your task
model.add_layer(Dense(num_your_classes))

# 5. Train on YOUR small dataset
model.train(your_images, your_labels, epochs=10)
```

**What to Preserve for Transfer Learning**:

1. **Feature extractors** (most valuable):
   - ImageNet-trained CNNs: Extract visual features for any vision task
   - Word embeddings (Word2Vec, GloVe): 300-dimensional word representations
   - Sentence encoders: Convert text to vectors

2. **Pre-trained backbones by domain**:
   - Vision: ResNet, EfficientNet, MobileNet
   - Text: BERT, DistilBERT
   - Audio: Whisper encoder

**Even Without Frameworks**:

If you only have weights (no PyTorch/TensorFlow):
1. Understand the architecture (documented in papers)
2. Implement forward pass in C
3. Use frozen features as input to simple classifier
4. Train only the final layer (much simpler)

**Critical Insight**: A 100MB pre-trained model encodes the equivalent of millions of dollars of training compute. **Preserving pre-trained weights is like preserving the accumulated knowledge of civilization.** These weights cannot be recreated post-collapse for decades—they represent the crystallized computation of thousands of GPUs running for weeks.

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

### Should AGI Be a Post-Collapse Goal?

**Artificial General Intelligence (AGI)**—human-level intelligence across all domains—was not achieved by 2025 and remains an open research problem. A critical question: should rebuilding civilization pursue AGI?

**Arguments Against Prioritizing AGI**:

1. **Opportunity Cost**: Resources spent on AGI research are resources not spent on practical tools
   - Medical diagnosis systems save lives now
   - Agricultural optimization feeds people now
   - AGI remains theoretical

2. **Unknown Timeline**: Even with pre-collapse resources, AGI was "5-50 years away" for decades
   - Post-collapse, realistic timeline is centuries
   - Pursuing it diverts from achievable goals

3. **Existential Risk**: Pre-collapse researchers warned that misaligned AGI could be dangerous
   - A rebuilding civilization has less capacity for safety research
   - Getting AGI wrong could be worse than not having it

4. **Narrow AI Suffices**: Most problems don't require general intelligence
   - Expert systems for diagnosis
   - Optimization for logistics
   - Classification for quality control
   - Each narrow system well-understood and controllable

**Arguments For Pursuing AGI**:

1. **Force Multiplier**: True AGI could accelerate all other development
   - Scientific discovery
   - Engineering design
   - Educational support

2. **Long-term Vision**: Beginning foundational work now pays off later
   - Understanding intelligence benefits narrow AI
   - Theoretical progress has practical applications

3. **Avoiding Complacency**: Narrow AI has limits
   - Complex problems may require general reasoning
   - Climate, disease, resource management involve many domains

**Practical Recommendation**:

**Focus on narrow AI for the first 50-75 years.** The practical benefits vastly outweigh speculative AGI research when:
- Expertise is scarce (preserve in expert systems)
- Resources are limited (optimize with classical ML)
- Survival needs are immediate (automate critical tasks)

**Reconsider AGI research when**:
- Deep learning infrastructure exists (GPUs, frameworks)
- Basic needs are secure (food, health, energy)
- Research capacity is available (universities, dedicated personnel)
- Safety research can proceed alongside capability research

**The Pre-Collapse Lesson**: By 2025, narrow AI transformed industries while AGI remained elusive. Post-collapse, the ratio of practical-to-theoretical benefit is even more skewed. Build what works. Save humanity first. Pursue transcendence later.

### Recommendations

1. **Start with explainable AI** (rules, simple ML)
2. **Test thoroughly** before deployment
3. **Human oversight** for critical decisions
4. **Document biases** in datasets
5. **Establish ethics guidelines** as capability grows
6. **Prioritize narrow AI** that solves immediate problems
7. **Preserve AGI research** for when infrastructure allows

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
