#### 01 - The golem of Prague
He won't talk about the war between bayes and frequentism. He will more talk about causal inference. 

##### Science before Statistics
For **statistical models** to produce scientific insight, they require additional **scientific (causal) models**.
The **reasons** for a statistical analysis are not found in the data themselves but in the **causes** of the data.
	We have to put the causes in, in order to design the right statistical model.

##### What's Causal inference
The association between variables is the main problem and this is what we mean by correlation implies causation. We should swap correlation by association. Variables can be associated but have no correlation.

Causal inference is a prediction of the consequences of an intervention. 

![[Screenshot 2024-06-27 at 11.45.44 AM.png]]

##### Causal prediction
Example: trees are swaying because of the wind. I know the cause is the wind. 
Therefore, knowing a cause means being able to predict the **consequences** of an **intervention**
The causal prediction is : what happens if I do this intervention. 

**Causal imputation**
If I know a cause that means being able to construct unobserved couterfactual outcomes. *What if I had done something else?* E.g. if another country landed on the moon.

**Causal inference**, **Description** (description of population) and the **Design** (of the research project, depends upon common knowledge of the subject). Scientific models link these 3 together. 

#### DAGs:
Directed Acyclic Graphs
Heuristic causal models.
The only information provided in DAGs are the letters and the arrows which link the letters together. E.g. B affects Y but Y doesn't affect B
![[Screenshot 2024-06-27 at 11.59.01 AM.png]]

- Relationship between X and Y. X is the treatment and Y is the effect.
- B is a competing cause, we are not interested in them, but it can be useful to measure them
- A
- C: common causes of X and Y together. It's a **confound**. We want to control for in a statistical analysis to study the relationship between X and Y. 
Adding control to a statistical analysis can be good and some controls can confuse the analysis. Therefore, DAGs are good to avoid these confusions

DAGs are intuition pumps: they get head out of data, into science. 