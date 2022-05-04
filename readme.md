Initially, I wanted to write a DSL for specifying Identification Cards, however, when I began implementation I realized this information is much easier to just store in a list. Eventually, I decided to make a very very simple DSL for describing recipes.  
This DSL is could be used for example:  
 - In a multiplayer game where you compete with other players and program robots in a kitchen to cook different recipes, attempting to cook the same meal accurately and swiftly. An example gamename would be "ChefBots -- Kitchens of the Future"  
 - A bit more farfetched, but the idea behind this DSL can eventually (far into the future) be used to develop real life robot chefs who should be capable of cooking any recipe a user can think of, even family recipes. 
 - A much more simple use case is for a hobby chef forum where users share recipes, such that each recipe is formatted correctly they should be written with the language grammar.
  
  It should be noted that this grammar is very simple, if it is not complex enough to fill the exercise requirement, I can further expand it. Just let me know.
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
