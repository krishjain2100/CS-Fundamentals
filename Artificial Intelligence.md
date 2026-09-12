An **agent** is anything that can be viewed as perceiving its **environment** through **sensors** and acting upon that environment through **actuators**. We use the term **percept** to refer to the agent’s perceptual inputs at any given instant. An agent’s **percept sequence** is the complete history of everything the agent has ever perceived.

Mathematically, an agent’s behavior is described by the **agent function** that maps any given percept sequence to an action.

A **rational agent** is one that does the right thing, i.e., every entry in the table for the agent function is filled out correctly. When an agent is plunked down in an environment, it generates a sequence of actions according to the percepts it receives. This sequence of actions causes the environment to go through a sequence of states. If the sequence is desirable, then the agent has performed well. This notion of desirability is captured by a **performance measure** that evaluates any given sequence of environment states.

Notice that we said _environment_ states, not _agent_ states. If we define success in terms of agent’s opinion of its own performance, an agent could achieve perfect rationality simply by deluding itself that its performance was perfect.

_As_ a general rule, it is better to design performance measures according to what one actually wants in the environment, rather than according to how one thinks the agent should behave.

For each possible percept sequence, a rational agent should select an action that is expected to maximise its performance measure, given the evidence provided by the percept sequence and whatever built-in knowledge the agent has.

We need to be careful to distinguish between rationality and **omniscience**. An omniscient agent knows the _actual_ outcome of its actions and can act accordingly; but omniscience is impossible in reality. Rationality maximizes _expected_ performance, while perfection maximizes _actual_ performance.

Our definition of rationality does not require omniscience because then the rational choice depends only on the percept sequence _to date_. We must also ensure that we haven’t inadvertently allowed the agent to engage in decidedly under-intelligent activities. For example, if an agent does not look both ways before crossing a busy road, then its percept sequence will not tell it that there is a large truck approaching at high speed. Does our definition of rationality say that it’s now OK to cross the road? Far from it.

First, it would not be rational to cross the road given this uninformative percept sequence: the risk of accident from crossing without looking is too great. Second, a rational agent should choose the “looking” action before stepping into the street, because looking helps maximize the expected performance. Doing actions in order to modify future percepts, called information gathering, is an important part of rationality.

To the extent that an agent relies on the prior knowledge of its designer rather than on its own percepts, we say that the agent lacks **autonomy**. A rational agent should be autonomous, it should learn what it can to compensate for partial or incorrect prior knowledge.

In our discussion of the rationality, we have to specify the performance measure, the environment, and the agent’s actuators and sensors. We group all these under the heading of the **task environment**. We call this the **PEAS** (Performance, Environment, Actuators, Sensors) description.

- **Fully observable** vs. **Partially observable**: If an agent’s sensors give it access to the complete state of the environment at each point in time, then we say that the task environment is fully observable. A task environment is effectively fully observable if the sensors detect all aspects that are _relevant_ to the choice of action, relevance, in turn, depends on the performance measure. 

 - **Deterministic** vs. **Stochastic**: If the next state of the environment is completely determined by the current state and the action executed by the agent, then we say the environment is deterministic, otherwise, it is stochastic. In principle, an agent need not worry about uncertainty in a fully observable, deterministic environment. In our definition, we ignore uncertainty that arises purely from the actions of other agents in a multi-agent environment; thus, a game can be deterministic even though each agent may be unable to predict the actions of the others. If the environment is partially observable, however, then it could _appear_ to be stochastic.

- **Static** vs. **dynamic**: If the environment can change while an agent is deliberating, then we say the environment is dynamic for that agent, otherwise, it is static.

- **Single agent vs. Multi-agent:** If an environment contains only one active entity maximising a performance measure, it is a single-agent environment (e.g., a crossword puzzle). If there are multiple entities whose actions impact each other's performance measures, it is a multi-agent environment (e.g., chess). Multi-agent environments can further be classified as competitive or cooperative.

- **Episodic vs. Sequential:** In an episodic task environment, the agent's experience is divided into atomic, independent episodes. In each episode, the agent receives a percept and performs a single action. Crucially, the next episode does not depend on the actions taken in previous episodes (e.g., an image classification bot). In sequential environments, a current decision could affect all future decisions (e.g., chess or a maze).

- **Discrete vs. Continuous:** This applies to the state of the environment, the handling of time, and the agent's percepts and actions. If the environment has a finite, countable number of distinct states, percepts, and actions, it is discrete (e.g., a chess game has discrete turns and moves). If the states and actions vary smoothly over time, it is continuous (e.g., a self-driving car managing speed and steering angles).

- **Known vs. Unknown:** This refers to the agent's state of knowledge, not a physical property of the environment. In a known environment, the outcomes or probabilities of all actions are given. In an unknown environment, the agent must learn the "laws of physics" to make good decisions. This is independent of observability, solitaire is known but partially observable, while a new simple video game (like checkers if it were known) is unknown but fully observable.


**Important Points:**

- Environmental properties depend heavily on how the task is framed. Medical diagnosis can be viewed as single-agent (treating the disease) and episodic (mapping symptoms to a diagnosis). However, if the agent must negotiate with skeptical staff or propose a sequential series of treatments over time, it becomes multi-agent and sequential.

- The hardest environments for agents to navigate are partially observable, multi-agent, stochastic, sequential, dynamic, continuous, and unknown (e.g., driving a rental car in a foreign country with unfamiliar laws).

- Developers use environment generators to simulate variations within an environment class (e.g., randomising dirt patterns or weather conditions) to ensure the rational agent maximizes its average performance across all possibilities.


**Thinking Rationally: Laws of Thought**

- This perspective argues that an AI system should display a logical thought process, rooted in Aristotle's logical way of deduction and reasoning.

- A limitation of this approach is that it does not account for actions taken without deliberation, such as reflex actions (e.g., pulling a hand away from something hot).

**Strong AI vs. Weak AI Hypothesis**

- **Weak AI Hypothesis:** Focuses on whether machines can _act_ intelligently. It suggests that a system passing the Turing test (appearing to act humanly) may merely be simulating thinking rather than genuinely thinking.

- **Strong AI Hypothesis:** Focuses on whether machines can _really think_. It suggests that machines can act intelligently not just through simulation, but through actual thought, possessing an awareness of their mental states and the process used to arrive at a solution.

---

The job of AI is to design an **agent program** that implements the agent function. the mapping from percepts to actions. We assume this program will run on some sort of computing device with physical sensors and actuators, we call this the **architecture**.
Agent = _architecture_ + _program_.

**Agent programs**: The agent programs take the current percept as input from the sensors and return an action to the actuators. Notice the difference between the agent program, which takes the current percept as input, and the agent function, which takes the entire percept history.

Four basic kinds of agent programs that embody the principles underlying almost all intelligent systems:

- Simple reflex agents
- Model-based reflex agents
- Goal-based agents
- Utility-based agent

**TOO MUCH AFTER THIS IN THIS SECTION**

---
