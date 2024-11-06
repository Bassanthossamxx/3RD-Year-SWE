# AI Lecture 1:

## 1. **Introduction to AI**
   - **Definition**: AI is a field in computer science focused on creating machines that perform tasks typically requiring human intelligence.
   - **History**: The field of AI was formally established in 1956 at the Dartmouth Conference.
   - **Scope**: AI encompasses various domains, including natural language processing (NLP), robotics, machine learning, and automated reasoning, aiming to understand and replicate human intelligence.

## 2. **Milestones in AI Development**
   - **1950**: Alan Turing introduced the Turing Test to assess machine intelligence.
   - **1956**: Dartmouth Conference marked the official beginning of AI research.
   - **1970s**: Development of expert systems (e.g., MYCIN for medical diagnosis).
   - **1980s**: Rise of machine learning and neural networks for data-driven AI.

## 3. **Definitions of AI Approaches**
   - **Thinking/Acting Humanly**: AI designed to mimic human cognitive processes and behavior.
   - **Thinking/Acting Rationally**: AI designed to reason logically and maximize success.

## 4. **Key Disciplines and Subfields in AI**
   - **Natural Language Processing (NLP)**
     - **Goal**: Enable machines to understand, interpret, and respond to human language.
     - **Core Areas**:
       - **Syntax and Grammar**: Parsing sentences and understanding structure.
       - **Semantics**: Understanding the meaning behind text.
       - **Applications**: Chatbots, translation tools (e.g., Google Translate), and virtual assistants.
   
   - **Knowledge Representation & Automated Reasoning**
     - **Knowledge Representation**: Storing knowledge in a format machines can use to solve complex tasks, like ontologies and knowledge graphs.
     - **Automated Reasoning**: AI’s ability to derive new knowledge from known facts, such as theorem proving in domains like mathematics or legal reasoning.

   - **Machine Learning**
     - **Definition**: A subset of AI focused on developing systems that learn from data.
     - **Types of Machine Learning**:
       - **Supervised Learning**: Learning from labeled data (e.g., classification).
       - **Unsupervised Learning**: Discovering patterns in unlabeled data (e.g., clustering).
       - **Reinforcement Learning**: Learning through rewards and punishments (e.g., AI agents in games).
     - **Example**: Neural networks used for image recognition and voice synthesis.

   - **Computer Vision**
     - **Goal**: Equip machines with the ability to interpret and make decisions based on visual data.
     - **Applications**:
       - **Autonomous Vehicles**: Recognizing objects and obstacles.
       - **Medical Imaging**: Identifying diseases from scans.
       - **Security**: Facial recognition for access control systems.
     - **Challenges**: Handling variations in lighting, perspective, and occlusion.

   - **Robotics**
     - **Definition**: The integration of AI with machines that interact with the physical world.
     - **Key Areas**:
       - **Autonomous Movement**: Navigating environments with minimal human intervention (e.g., self-driving cars).
       - **Object Manipulation**: Ability to handle objects, used in manufacturing and healthcare.
     - **Applications**: From factory robots to service robots like vacuum cleaners.

## 5. **Agent Concepts**
   - **Definition of Agent**: An entity that perceives its environment through sensors and acts upon it through actuators.
      - **Examples**:
         - **Human Agents**: Sensors (eyes, ears), actuators (hands, legs).
         - **Robotic Agents**: Sensors (cameras, infrared), actuators (motors).
         - **Software Agents**: Sensors (keystrokes, file contents), actuators (sending packets, writing files).
   - **Percepts and Actions**:
      - **Percept**: Input received from the environment.
      - **Action**: Decision or response based on percepts.
   - **Agent Function**: A function mapping percept sequences to actions, often implemented in programs or as tables.

## 6. **Agent Example: Vacuum Cleaner**
   - **Environment**: Two locations (A and B), each possibly dirty.
   - **Actions**:
      - If the square is dirty, suck dirt; else, move to the other square.
   - **MATLAB Example**:
      ```matlab
      function action = agent_function(percept)
          if percept == 'dirty'
              action = 'clean';
          else
              action = 'move';
          end
      end
      ```
   - **Python Example**: A vacuum class that moves between locations A and B, cleans dirt, and tracks environment state.

## 7. **Agent Behavior**
   - **Effectiveness**: Determined by the success of actions and resource efficiency (time, energy).
   - **Rationality**: Agents should behave optimally based on available information.

## 8. **Learning and Autonomy**
   - **Learning**: Agents adapt by learning from percept history, enhancing future decisions (e.g., vacuum cleaner learns dirt patterns).
   - **Autonomy**: Agents act independently and improve with experience over time.

## 9. **Differences Between Agents and Traditional Software**
   - **Autonomous**: Operates on the user's behalf, can act proactively.
   - **Intelligence**: Varies from simple rules to learning capabilities.
   - **Social Ability**: Communicates with users, systems, or other agents.
   - **Cooperation**: Can collaborate with other agents for complex tasks.
   - **Mobility**: Can migrate across systems for specific resources or tasks.

## 10. **Challenges in AI**
   - **Combinatorial Explosion**: As tasks grow in complexity, possibilities increase exponentially.
   - **Ethical Concerns**: Privacy, job displacement, and decision-making authority.
   - **Understanding Human Context**: AI struggles with understanding nuances in language and social situations.

## 11. **PEAS Framework (Performance, Environment, Actuators, Sensors)**
   - **PEAS Description**:
      - **Performance Measure**: Defines criteria for success (e.g., cleanliness in a vacuum environment).
      - **Environment**: Environment the agent interacts with (e.g., locations and dirt conditions).
      - **Actuators**: Possible actions (e.g., move, clean).
      - **Sensors**: Percepts (e.g., location, dirt status).
   - **Example**: Automated taxi using performance, actuators (steering, brakes), sensors (cameras, GPS), and environment (roads, traffic, pedestrians).

## 12. **Advanced Agent Structures**
   - **Utility-Based Agents**: Maximize expected utility based on performance.
   - **Goal-Based Agents**: Take actions aimed at achieving defined goals.
   - **Learning Agents**: Improve over time by learning from previous actions and outcomes.

## 13. **Categories of Task Environments**
   - **Environment Types**:
      - **Fully vs. Partially Observable**: Determines if the agent can perceive the entire state.
      - **Single vs. Multi-Agent**: Indicates if the agent works alone or with others.
      - **Deterministic vs. Stochastic**: Whether there is randomness in state transitions.
      - **Static vs. Dynamic**: Whether the environment changes over time.

## 14. **Agent Program Structures**
   - **Representation Types**:
      - **Atomic**: Treats states as black boxes without internal structure.
      - **Factored**: Breaks down states into variables with multiple values.
      - **Structured**: Explicitly represents objects and relationships.
