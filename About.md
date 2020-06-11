# RecipeApp
For some time I've been thinking that it would be helpful to have a database of recipes that we use on a regular basis. A cookbook online, but something with a bit more depth than a typical recipe site (don't get me wrong, I really depend on those sites greatly because I can't know everything).

## Background 
Once a week we sit at the breakfast table and write out our meal plan for the week - just dinners because we plan leftovers as lunch - and then our grocery expands from that. Occasionally we forget something, a rarely used ingredient that we've run out of in our pantry or just a plain old oversight.

There are staples, things that we ensure we purchase like eggs, milk, cheese and some canned items. Then there are the items that we're going to need to plan on depleting such as the bunch of cilantro or 2 KG bag of carrots we bought so we could use 2 carrots in a soup.

## Waste Not...
I imagine an app that we could query for recipes that contain carrots and perhaps a few other ingredients that we already have in order to use up the surplus and reduce our food waste. Planning our menu helps a lot, but there's still that cilantro...

But also avoid wasting money. When we buy our groceries, it would be nice to track what we are buying, how much we are spending on those items and compare trends. Some are generally more expensive, while other foods are affected by seasonality.

A tool to catalogue these transactions could help us stick more closely to a budget, even determine the cost per meal. To stick with $100/week for groceries, we could pick our "feature" (read expensive) meal and the remainder based on an average maximum cost filling in the difference. Or possibly find a way to fit a dinner out within that monthly budget - and without sharing a happy meal.

## The App
### Database
It requires a database to store the data. To conceptualize this, I need to first identify the primary containers or objects before I let myself get bogged down by the granular properties of each object.

Recipes: The beast that started it all, a container to store information about the meals we make and what goes into those meals.

Grocery Lists: To track what we're spending (or expecting to spend) we'll need to keep track of the list of grocery items that we'll be buying.

Inventory: After we purchase our groceries, these items should go into our inventory.

Groceries: The individual food items and their various quantities.

Meal Plan: This will group recipes together for a specific period of time. For us, weekly makes sense, but this could even transition us to multi-week plans.

Grocery Receipts: The overall and itemized cost of groceries purchased. This will help supply estimated costs for grocery lists. 

### Functions
Add Recipe to Meal Plan: To build a meal plan, recipes need to be added.

Meal Plan to Grocery List: Aggregate items from recipes into required quantities and add them to a Grocery List.

Check Inventory: Used on its own it would return the current inventory for a grocery item, or called from the {Meal Plan to Grocery List} function it should advise on the additional required quantity of the Grocery item to add to the Grocery List. 

Remove Grocery From Inventory: will deduct a specific quantity of a Grocery item from the Inventory, or remove it entirely.

Add Grocery to Inventory: will increase the current Inventory for a Grocery item by a specific quantity.

Add Grocery to Grocery List: Used on its own for those one off Grocery items that are often used on their own, such as cereal or ketchup. Called from the {Meal Plan to Grocery List} after {Check Inventory} will add the required quantity to the Grocery List.
