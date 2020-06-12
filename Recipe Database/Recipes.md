# Recipes table
Recipe Name: Common or known name
Recipe Category: Dessert, meal, appetizer, soup, salad
Recipe Description: Description of the recipe

## Child Tables
These tables are required to make the recipe more flexible and queryable.

### Recipe Steps table
Step Number: a number representing the sequence in which specific activities need to be performed
Step Duration: How long a step will take
Step Instruction: The actual instructions that must be followed when the step is to be executed

### Recipe Ingredients table
Grocery Item: ID of the required grocery item
Ingredient Quantity: Quantity of the grocery item required for the recipe
Ingredient Measure: the means in which the quantity is supposed to be measured, such as CUP, TSP, G/KG
Ingredient Preparation: how the ingredient should be prepared before use, such as diced, chopped, whole, melted, etc.