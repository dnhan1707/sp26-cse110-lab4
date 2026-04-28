1. Line 2 will print '3' since 'var i' in the loop is a function scope, and it is value 3 since the input length is 3.
2. It prints '150' since discountedPrice is declared with var inside the for loop on line 7. With let or const, it would be block-scoped and not exist outside the loop. But because it's var, it's function-scoped, meaning it leaks out of the loop and is accessible anywhere in the discountPrices function, including line 13.
3. This line would print 150, finalPrice was declared with var on line 4 at the top of the function, outside the loop. So it's clearly in scope on line 14 regardless of var vs let. By the time we reach line 14, the loop has finished and finalPrice holds the value from the final iteration: 150.
4. The output of the function is [50, 100, 150]. As the loop iterates over each price in the input array, it computes 50% of the value and appends the result to the discounted array, which is then returned at the end.
5. Line 12 throws a ReferenceError. Because i is declared with let, its lifetime is confined to the for loop block, so any reference made outside that block cannot resolve the variable.
6. Line 13 raises a ReferenceError as well. The variable discountPrice was introduced using let within the loop body, which means it only exists inside that block and disappears once the loop ends.
7. Line 14 also produces a ReferenceError. Since finalPrice is declared with let inside the loop, it cannot be referenced after the loop closes — the binding no longer exists in that outer scope.
8. The function still returns [50, 100, 150] without issue. The discounted array is built up correctly during the loop, and because the return statement sits in the same scope where the array was declared, it has no trouble accessing it.
9. Line 11 throws a ReferenceError. The loop counter i was declared with let, which restricts its visibility to the body of the for loop, so it is unreachable from outside.
10. Line 12 prints 3. The constant length lives in the same block as the console.log call, so it remains accessible at that point and holds the array's length value.
11. The function returns [50, 100, 150]. Even though discounted was declared with const, that only prevents reassigning the binding itself — mutating the array's contents through .push is perfectly legal.
12. A. student.name, B. student['Grad Year'], C. student.greeting(), D. student['Favorite Teacher'].name, E. student.courseLoad[0]
13. A. '32', B. 1, C. 3, D. '3null', E. 4, F. 0, G. '3undefined', H. NaN,
14. A. true, B. false, C. true, D. false, E. false, F. true
15. The key difference lies in type handling. The == operator coerces operands into a common type before comparing them, whereas === skips coercion entirely and demands that both the value and the type match precisely for the comparison to be true.
16. (Code in part2-question16.js)
17. The resulting array will be [2, 4, 6]. Inside modifyArray, each element of [1, 2, 3] is handed off to the doSomething callback, which doubles the number and returns it. Each returned value is then appended to newArr, producing the doubled sequence.
18. (Code in part2-question18.js)
19. The output order is 1, 4, 3, 2. JavaScript runs the synchronous console.log calls right away, which prints 1 followed by 4. The setTimeout scheduled with 0ms is queued and fires next once the call stack clears, printing 3. The 1000ms timer resolves last, finally logging 2.
