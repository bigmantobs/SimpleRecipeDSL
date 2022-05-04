The file extension reads IdentityDSL as I originally wanted a DSL for creation and printing of Identity Cards but upon attempting to implement it, I realized this is information which can just be kept in a list.
Instead I decided to write a really basic DSL to describe recipes, the idea here is that the user programs recipes into a cooking bot for a competitive online cooking game, wherein you must program your "chefBot" to cook a recipe better and faster than the opponent.
I am not much of a cook myself so the recipe is likely to be flawed. Additionally the DSL is very basic and must be expanded upon with ingredients, cooking techniques, etc.  

Described below is the grammar for the language:  
```  
grammar org.xtext.example.identityDSL.IdentityDSL with org.eclipse.xtext.common.Terminals

generate identityDSL "http://www.xtext.org/example/identityDSL/IdentityDSL"
  
root:  
  instructions;

instructions:
	Name | Cook | Bake | Fry | Mix
;

Name:
	'Recipe' navn=STRING
;

Cook:
	'Cook' Ingredient 'for' time=INT 'on' Heat
;

Bake:
	'Bake' Ingredient 'for' time=INT 'at' temp=INT 
;

Fry:
	'Fry' ingr=STRING Ingredient 'for' time=INT 'on' Heat
;

Mix:
	'Mix'
;

Ingredient:
	'Potato' | 'Chicken' | 'Penne'
;

Heat:
	'High' | 'Medium' | 'Low'
;
```
