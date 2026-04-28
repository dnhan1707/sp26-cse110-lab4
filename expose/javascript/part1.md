1. values added: 20 
2. final result: 20 
3. We shouldn't use var because it's function-scoped instead of block-scoped. In this code, result is declared inside the if block but is still accessible on line 13 outside of it, which is confusing and error-prone. With let or const, the variable would stay inside the block where it was declared, making the code's scope clearer and safer. Use const by default, and let when you need to reassign.
4. values added: 20 
5. Line 13 would return Reference Error since the keyword 'let' is block scope which mean it only exists in the if statement block and not anywhere else.
6. The code would not get to line 9 since there is error on line 7 where it is attempting to change the 'const' variable.
7. ReferenceError would be returned since the scope issue as well, the 'const' variable also block scope which again only exist in the if statement just like 5.    