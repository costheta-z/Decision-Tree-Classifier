# Decision Tree Classifier
### What is a Decision Tree:
What is a Decision Tree?
A Decision tree is a type of classifier, a collection of nodes and vertices intended to form a conclusion based on available affiliated attribute values. They are self-learning trees which can be trained using a sample dataset, so that they'd be able to classify the object associated with a set of attribute values into labels that the objects most likely belongs to. These classify in a different manner than the Naïve Bayes classifier family of algorithms, which assume every pair of features being classified is independent of each other.
An internal node of a decision tree represents attributes, each branch represents a decision rule and each leaf node represents the outcomes. The topmost node in a decision tree is known as the root node and is also the first attribute based on which the classification progresses. It learns to partition based on the attribute values. It partitions the tree in a recursive manner called recursive partitioning. This flowchart-like structure helps you in decision making. Decision trees classify the examples by sorting them down the tree from the root to some leaf node, with the leaf node providing the classification to the example, this approach is called a Top-Down approach. Each node in the tree acts as a test case for some attribute, and each edge descending from that node corresponds to one of the possible answers to the test case. This process is recursive and is repeated for every subtree rooted at the new nodes.
### What it does:
1) Trains the tree based on a randomly picked sub table of the iris dataset.
2) Given certain attributes then it would be able to classify the component possessing these attributes belongs to which class of the data set.

### Accuracy:
The accuracy of correct classification depends on the purity of the data set that trained the tree. Thus the point of splitting for 2 different classes determines how precise the classification would be.

### Features:
1) Prevents bias: It enforces the consideration of all possible outcomes of a decision and traces each path to a conclusion.
2) Not restricted by data: Decision trees are able to handle both continuous (through C4.5 algo by
Ross Quinlan) and categorical variables, the example of iris data set used in this project has continuous features.
3) Most weighted fields: Decision trees provide a clear indication of which fields are most important
for prediction or classification.
4) Saves Time: Outcomes can be achieved faster through the use of a decision tree than manual
classification.
5) More Efficiency and Accuracy: supplies us with the most probable outcome of our problem with
better accuracy than simpler probabilistic independent algorithms. Acceptable information we
feed into the dataset improves the accuracy as the time progresses because with the historical
records collected, the selections interpreted get higher and better.

### Properties of a Decision Tree:
1) Divide and conquer structure for sorting a training set into pure subsets.
2) Leaves represent class labels and branches represent conjunctions of features that lead to these class labels.
3) A decision tree model contains a key column, input columns, and at least one predictable (label/class) column.
4) Decision trees use multiple algorithms to decide to split a node in two or more sub-nodes. 
5) The creation of sub-nodes increases the homogeneity of resultant sub-nodes i.e. purity of the node increases with respect to the target variable. 
6) Decision tree splits the nodes on all available variables and then selects the split which results in most homogeneous sub-nodes.
7) The decision of making strategic splits heavily affects a tree’s accuracy. The decision criteria are different for classification and regression trees.

8) Variance: <a href="https://www.codecogs.com/eqnedit.php?latex=\frac{\sum_{i=1}^n&space;(x_i-u)^2}{n}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{\sum_{i=1}^n&space;(x_i-u)^2}{n}" title="\frac{\sum_{i=1}^n (x_i-u)^2}{n}" /></a>
9) Entropy: Entropy is used to measure the impurity or randomness of a dataset. <a href="https://www.codecogs.com/eqnedit.php?latex=-\sum_{i=1}^n&space;(p_i\times\log_2&space;(p_i))" target="_blank"><img src="https://latex.codecogs.com/gif.latex?-\sum_{i=1}^n&space;(p_i\times\log_2&space;(p_i))" title="-\sum_{i=1}^n (p_i\times\log_2 (p_i))" /></a>
10) Gini: It is the probability of correctly labeling a randomly chosen element if it was randomly labeled according to the distribution of labels in the node. 
<a href="https://www.codecogs.com/eqnedit.php?latex=\sum_{i=1}^n&space;(p_i)^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sum_{i=1}^n&space;(p_i)^2" title="\sum_{i=1}^n (p_i)^2" /></a>
11) Information Gain:  Decision tree algorithm implementation uses information gain to decide which feature needs to be split in the next step.  Information Gain is used for splitting the nodes when the target variable is categorical. It works on the concept of the entropy <a href="https://www.codecogs.com/eqnedit.php?latex=IG=1-Entropy" target="_blank"><img src="https://latex.codecogs.com/gif.latex?IG=1-Entropy" title="IG=1-Entropy" /></a>

### Entropy and IG formulae explained:
A decision tree is built top-down from a root node and involves partitioning the data into subsets that contain instances with similar values (homogenous). This partitioning introduces certain new criteria and terms to be aware of that enable in determining the point of division. 

#### 1.	Information Gain:
Information gain (IG) measures how much "information" a feature gives us about the class.
1) Information gain is the main key that is used by Decision Tree Algorithms to construct a Decision Tree.
2) Decision Trees algorithm will always try to maximize Information gain.
3) An attribute with highest Information gain will tested/split first.
 
#### 2.	Entropy:
Entropy is used for calculating the purity of a node.
1) Uncertainty
2) Purity
3) Information content

It is used to measure the impurity or randomness of a dataset. Imagine choosing a yellow ball from a box of just yellow balls (say 100 yellow balls). Then this box is said to have 0 entropy which implies 0 impurity or total purity.
Now, let’s say 30 of these balls are replaced by red and 20 by blue. If we now draw another ball from the box, the probability of drawing a yellow ball will drop from 1.0 to 0.5. Since the impurity has increased, entropy has also increased while purity has decreased. Shannon’s entropy model uses the logarithm function with base 2 (log2(P(x)) to measure the entropy because as the probability P(x) of randomly drawing a yellow ball increases, the result approaches closer to binary logarithm 1.
When a target feature contains more than one type of element (balls of different colors in a box), it is useful to sum up the entropies of each possible target value and weigh it by the probability of getting these values assuming a random draw.
Logarithm of fractions gives a negative value and hence a '-' sign is used in entropy formula to negate these negative values. 
 
### Concurrency Control:
Time complexity of main algorithm (decision_tree_algorithm)
o Best Case: O(<a href="https://www.codecogs.com/eqnedit.php?latex=M\times&space;N\times&space;log_2&space;(N)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?M\times&space;N\times&space;log_2&space;(N)" title="M\times N\times log_2 (N)" /></a>)
o Worst Case: O(<a href="https://www.codecogs.com/eqnedit.php?latex=M\times&space;N^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?M\times&space;N^2" title="M\times N^2" /></a>)
Where M is number of features and N is the number of rows in Data
For Best Case:
If tree generated is balanced then the time complexity of tree will be O(<a href="https://www.codecogs.com/eqnedit.php?latex=log_2&space;(N)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?log_2&space;(N)" title="log_2 (N)" /></a>)
So, the total time complexity of the algorithm with splitting included will be O(<a href="https://www.codecogs.com/eqnedit.php?latex=M\times&space;N\times&space;log_2&space;(N)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?M\times&space;N\times&space;log_2&space;(N)" title="M\times N\times log_2 (N)" /></a>)
For Worst Case:
If tree generated is not balanced then the time complexity of the tree will be O(N)
So, the total time Complexity of the algorithm with splitting included will be O(<a href="https://www.codecogs.com/eqnedit.php?latex=M\times&space;N^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?M\times&space;N^2" title="M\times N^2" /></a>)
