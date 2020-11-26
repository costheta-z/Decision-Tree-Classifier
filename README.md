# Decision Tree Classifier
### What is a Decision Tree:
What is a Decision Tree?
A Decision tree is a type of classifier, a collection of nodes and vertices intended to form a conclusion
based on available affiliated attribute values. They are self-learning trees which can be trained using a
sample dataset, so that they'd be able to classify the object associated with a set of attribute values into
labels that the objects most likely belongs to. These classify in a different manner than the Naïve Bayes
classifier family of algorithms, which assume every pair of features being classified is independent of each
other.
An internal node of a decision tree represents attributes, each branch represents a decision rule and each
leaf node represents the outcomes. The topmost node in a decision tree is known as the root node and is
also the first attribute based on which the classification progresses. It learns to partition based on the
attribute values. It partitions the tree in a recursive manner called recursive partitioning. This flowchart-like
structure helps you in decision making.
Decision trees classify the examples by sorting them down the tree from the root to some leaf node, with
the leaf node providing the classification to the example, this approach is called a Top-Down approach.
Each node in the tree acts as a test case for some attribute, and each edge descending from that node
corresponds to one of the possible answers to the test case. This process is recursive and is repeated for
every subtree rooted at the new nodes.
### What it does:
$ 1. $ Trains the tree based on a randomly picked sub table of the iris dataset.
$ 2. $ Given certain attributes then it would be able to classify the component possessing these attributes belongs to which class of the data set.
### Accuracy:
The accuracy of correct classification depends on the purity of the data set that trained the tree. 
Thus the point of splitting for 2 different classes determines how precise the classification would be.
### Features:
1. Prevents bias: It enforces the consideration of all possible outcomes of a decision and traces
each path to a conclusion.
2. Not restricted by data: Decision trees are able to handle both continuous (through C4.5 algo by
Ross Quinlan) and categorical variables, the example of iris data set used in this project has continuous features.
3. Most weighted fields: Decision trees provide a clear indication of which fields are most important
for prediction or classification.
4. Saves Time: Outcomes can be achieved faster through the use of a decision tree than manual
classification.
5. More Efficiency and Accuracy: supplies us with the most probable outcome of our problem with
better accuracy than simpler probabilistic independent algorithms. Acceptable information we
feed into the dataset improves the accuracy as the time progresses because with the historical
records collected, the selections interpreted get higher and better.
### Properties of a Decision Tree:
•	Divide and conquer structure for sorting a training set into pure subsets.
•	Leaves represent class labels and branches represent conjunctions of features that lead to these class labels.
•	A decision tree model contains a key column, input columns, and at least one predictable (label/class) column.
•	Decision trees use multiple algorithms to decide to split a node in two or more sub-nodes. 
•	The creation of sub-nodes increases the homogeneity of resultant sub-nodes i.e. purity of the node increases with respect to the target variable. 
•	Decision tree splits the nodes on all available variables and then selects the split which results in most homogeneous sub-nodes.
•	The decision of making strategic splits heavily affects a tree’s accuracy. The decision criteria are different for classification and regression trees.

•	Variance:     $\frac{\sum_{i=1}^n (x_i-u)^2}{n}$     
•	Entropy: Entropy is used to measure the impurity or randomness of a dataset. $-\sum_{i=1}^n (p_i*log<sub>2</sub>(p_i))$
•	Gini: It is the probability of correctly labeling a randomly chosen element if it was randomly labeled according to the distribution of labels in the node. 
$\sum_{i=1}^n (p_i)^2$
•	Information Gain:  Decision tree algorithm implementation uses information gain to decide which feature needs to be split in the next step.  Information Gain is used for splitting the nodes when the target variable is categorical. It works on the concept of the entropy
$IG=1-Entropy$
### Entropy and IG formulae explained:
A decision tree is built top-down from a root node and involves partitioning the data into subsets that contain instances with similar values (homogenous). This partitioning introduces certain new criteria and terms to be aware of that enable in determining the point of division. 

#### 1.	Information Gain:
Information gain (IG) measures how much “information” a feature gives us about the class.
·	Information gain is the main key that is used by Decision Tree Algorithms to construct a Decision Tree.
·	Decision Trees algorithm will always try to maximize Information gain.
·	An attribute with highest Information gain will tested/split first.
 
#### 2.	Entropy:
Entropy is used for calculating the purity of a node.
·	Uncertainty
·	Purity
·	Information content
It is used to measure the impurity or randomness of a dataset. Imagine choosing a yellow ball from a box of just yellow balls (say 100 yellow balls). Then this box is said to have 0 entropy which implies 0 impurity or total purity.
Now, let’s say 30 of these balls are replaced by red and 20 by blue. If we now draw another ball from the box, the probability of drawing a yellow ball will drop from 1.0 to 0.5. Since the impurity has increased, entropy has also increased while purity has decreased. Shannon’s entropy model uses the logarithm function with base 2 (log2(P(x)) to measure the entropy because as the probability P(x) of randomly drawing a yellow ball increases, the result approaches closer to binary logarithm 1 as shown in the graph below.
When a target feature contains more than one type of element (balls of different colors in a box), it is useful to sum up the entropies of each possible target value and weigh it by the probability of getting these values assuming a random draw. This finally leads us to the formal definition of Shannon’s entropy which serves as the baseline for the information gain calculation:
Logarithm of fractions gives a negative value and hence a ‘-’ sign is used in entropy formula to negate these negative values. 

### Operations on Decision Trees:

#### Creation (how to build tree):

1.	Select the first attribute of test dataset over which the set would split.
2.	If a pure subset is obtained, no further splitting is performed for the pure value.
3.	Grow the rest of the tree by splitting impure subsets based on new unused attributes with the help of "node impurity".

#### Split (how to split node): There are multiple ways of doing this, the suitable algorithm selection is based on type of target variables, which can be broadly divided into two categories:

1.	Continuous Target Variable

•	Reduction in Variance - Reduction in Variance is a method for splitting the node used when the target variable is continuous, i.e., regression problems. It is so-called because it uses variance as a measure for deciding the feature on which node is split into child nodes.
	Variance is used for calculating the homogeneity of a node. If a node is entirely homogeneous, then the variance is zero. Here are the steps to split a decision tree using reduction in variance:
1.	For each split, individually calculate the variance of each child node
2.	Calculate the variance of each split as the weighted average variance of child nodes
3.	Select the split with the lowest variance
4.	Perform steps 1-3 until completely homogeneous nodes are achieved

2.	Categorical Target Variable

•	Information Gain - It works on the concept of the entropy. Entropy is used for calculating the purity of a node. Lower the value of entropy from 1, the information gain is higher for the pure nodes with a maximum value of 1. ID3 algorithm uses entropy to calculate the homogeneity of a sample. Steps to split a decision tree using Information Gain:
1.	For each split, individually calculate the entropy of each child nodes.
2.	Calculate the entropy of each split as the weighted average entropy of child nodes.
3.	Select the split with the lowest entropy or highest information gain.
4.	Until you achieve homogeneous nodes, repeat steps 1-3.

•	 Gini Impurity - Lower the Gini Impurity, higher is the homogeneity of the node.
Gini Impurity is preferred over Information Gain because it does not contain logarithms which are computationally intensive.

#### Termination (When to stop splitting):
•	No more input features.
•	All examples are classified the same.
•	Too few examples to make an informative split. 
### Concurrency Control:
Time complexity of main algorithm (decision_tree_algorithm)
o Best Case: O($ M*N*log<sub>2</sub>(N) $)
o Worst Case: O($ M*N^2 $)
Where M is number of features and N is the number of rows in Data
For Best Case:
If tree generated is balanced then the time complexity of tree will be O($ log<sub></sub>(N) $)
So, the total time complexity of the algorithm with splitting included will be
O($ M*N*log<sub>2</sub>(N) $)
For Worst Case:
If tree generated is not balanced then the time complexity of the tree will be O($ N $)
So, the total time Complexity of the algorithm with splitting included will be O($ M*N^2 $)
