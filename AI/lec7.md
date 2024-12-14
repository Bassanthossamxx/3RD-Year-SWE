### Lecture 7: Knowledge Representation in AI

**Purpose of Knowledge Representation:**
- Enable intelligent reasoning.
- Facilitate decision-making in complex systems.
- Provide the foundation for expert systems.

---

### Types of Knowledge:
1. **Declarative Knowledge**
   - Represents facts and their relationships.
   - Example: "Cats are mammals."

2. **Procedural Knowledge**
   - Focuses on rules and step-by-step processes.
   - Example: "To diagnose a disease, follow predefined medical tests."

---

### Reasoning and Inference
1. **Reasoning:**
   - Logical thinking to connect pieces of knowledge.
   - Types:
     - **Deductive Reasoning**: General to specific.
       - Example: "All mammals have backbones. A cat is a mammal. → A cat has a backbone."
     - **Inductive Reasoning**: Specific to general.
       - Example: "This cat has a backbone. That cat has a backbone. → All cats probably have backbones."
     - **Abductive Reasoning**: Most likely explanation.
       - Example: "The ground is wet. → It probably rained."

2. **Inference:**
   - Extracts or derives new knowledge from existing knowledge.
   - Example: "All mammals have backbones. A whale is a mammal. → A whale has a backbone."

---

### Knowledge Representation Techniques
1. **Symbolic Knowledge Representation (Logical-based)**
   - **Production Rules**:
     - Logical rules written as "IF-THEN" statements.
     - Structure:
       - IF Condition THEN Action.
       - Example: "IF the battery voltage is below 10 volts, THEN it’s a bad battery."
     - Advantages:
       - Simple and intuitive.
       - Handles complex decision-making.
     - Limitations:
       - Scalability issues with many rules.

2. **Decision Tables:**
   - Tabular format for rule-based decision-making.
   - Structure:
      - Conditions: Criteria for decisions.
      - Actions: Possible results.
      - Entries: Y (True), N (False), or - (Irrelevant).

   - Example:
     - Rule 1: IF cash is available AND the order amount > 100, THEN give a 20% discount.
   - Benefits:
     - Clarity: Lists all conditions and actions in one place.
     - Efficiency: Easy to understand.
     - Accuracy: Ensures all scenarios are covered.

3. **Semantic Nets:**
   - Graphical representation of relationships between concepts.
   - Components:
     - **Nodes:** Represent objects or concepts.
     - **Edges:** Represent relationships (e.g., "is a", "has").
   - Example:
     - Mammal → "is a" → Animal.
     - Fish → "lives in" → Water.
   - Detailed Representation:
     - **Object-Attribute-Value (OAV) Triplets**: "Fish → Lives in → Water."

4. **Frames:**
   - Represents stereotypical situations.
   - Structure:
     - Frame Name (e.g., "Lecture").
     - Slots: Attributes (e.g., "Course").
     - Values: Specific details (e.g., "Operating Systems").
   - Hierarchy:
     - Parent Frame: General concept (e.g., "Meeting").
     - Child Frame: Specific details (e.g., "Lecture").

5. **Logic (Propositional and Predicate):**
   - **Propositional Logic:**
     - Statements are either true or false.
     - Connectives:
       - ∧ (AND), ∨ (OR), ¬ (NOT), → (Implies).
     - Example:
       - (P ∧ Q) → R: If P and Q are true, R is true.
   - **Predicate Logic (First-Order Logic):**
     - Adds quantifiers and variables to propositional logic.
     - Key Quantifiers:
       - Universal (∀): Applies to all objects.
         - Example: ∀x (Human(x) → Mortal(x)) – "All humans are mortal."
       - Existential (∃): Applies to some objects.
         - Example: ∃x (Cat(x) ∧ Black(x)) – "There exists a black cat."

---

### Advanced Representation: Ontology
- Structured representation of concepts, relationships, and rules within a domain.
- Components:
  1. **Concepts (Classes):** Represent objects or categories (e.g., "Person").
  2. **Relationships (Properties):** Define connections (e.g., "is a parent of").
  3. **Instances (Individuals):** Specific examples (e.g., "John").
  4. **Hierarchy (Taxonomy):** Parent-child relationships (e.g., "Animal" → "Mammal").
- Applications:
  - AI reasoning, e.g., expert systems.

---

### Theorem Proving in AI
- **Definition:** Process of proving logical statements using formal methods and inference rules.
- Techniques:
  1. **Resolution:** Derive contradictions or conclusions.
  2. **Forward Chaining:** Start with facts and infer until a goal is reached.
  3. **Backward Chaining:** Start with a goal and work backward to determine supporting facts.
- Applications:
  - Logical reasoning in AI systems.
  - Systematic theorem proofs.

---

**Key Takeaways:**
1. Knowledge is the foundation of AI systems.
2. Reasoning uses knowledge for decision-making.
3. Inference derives new knowledge logically.
4. Knowledge representation techniques, like semantic nets and frames, are crucial for AI's understanding and reasoning.
5. Ontologies and logical systems enhance AI’s ability to model and reason within domains.

