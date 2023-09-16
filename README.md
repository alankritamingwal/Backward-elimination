# Backward-elimination
Added Backward Elimination Function (backward_elimination): I created a new function named backward_elimination to perform the backward elimination process. This function takes a Pandas dataframe as input, which represents the entire dataset, and iteratively removes the least significant attributes until a stopping criterion is met.

Initialization of Available Attributes: At the beginning of the backward_elimination function, I created a dataframe named available_attributes_df that initially contains all available attributes except the instance ID and class columns.

Stopping Criterion: I introduced a stopping criterion variable named stopping_criterion to control when the backward elimination process should stop. In the example code, the stopping criterion is set to continue until no further improvement in performance is observed.

Iterative Attribute Removal: Inside the backward_elimination function, there is a loop that iterates through the available attributes. For each attribute, it temporarily removes that attribute from the dataset and runs the Naive Bayes algorithm on the reduced dataset to evaluate its performance.

Performance Comparison: The code keeps track of the best performance achieved and the attribute that led to that performance. If removing an attribute results in an accuracy improvement, that attribute is marked as the "worst" attribute and is removed from the list of available attributes.

Updating Available Attributes: The attribute marked as the "worst" attribute is removed from the available_attributes_df, and the loop continues to evaluate the next available attribute. This process continues until the stopping criterion is met.

Final Optimal Attribute Set: After the backward elimination process is complete, the initial_available_attributes_df contains the initial set of available attributes before any elimination occurred. This set is the optimal attribute subset selected by the backward elimination process.

Main Function Integration: In the main function, I incorporated the backward_elimination function to find the optimal attribute subset. The code then runs the Naive Bayes algorithm on this selected attribute subset and provides relevant statistics, such as accuracy and the list of optimal attributes.
