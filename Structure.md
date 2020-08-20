
# A Foreign key is a column in a table that is going to reference the primary key on another table

## A piece of information that is common to both tables.


ingredients 
| |
--| recipes
  | |
  |----- dishes


ingredients can be found in many recipes
recipes can have many ingredients


dishes can have many recipes
recipes belong to a single dish

I believe I need another table for the relatioship since it's many to many
---
### Each recipe results in a single dish. So don't worry about this relationship, it's not new.
### Recipes have many ingredients. 
### Ingredients are in many recipes.
### ingredients recipes is a relationship table that tracks the ingredients in recipes. 

From a SO answer to a many-to-many question
[SO](https://dba.stackexchange.com/questions/151904/mapping-many-to-many-relationship)

SELECT r.recipe_name, i.ingredient_name, ir.ingredient_qty, ir.ingredient_unit, ir.recipe_scale
FROM recipes as r
INNER JOIN ingredients_recipes as ir
ON r.recipe_id = ir.recipe_id
INNER JOIN ingredients as i
ON i.ingredient_id = ir.ingredient_id


