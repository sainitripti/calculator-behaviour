# Division
  
Scenario: Division by zero when first operand is any number

  Given The calculator is on
  
  When I type in "first number"
  And I press "divide"
  And I type in "zero"
  And I press "equals"
  
  Then I see "Cannot divide by zero" as result
  
Scenario: Divide "zero" by any number

  Given The calculator is on
  
  When I type in "zero"
  And I press "divide"
  And I type in "second number"
  And I press "equals"
  
  Then I see "zero" as result
  
Scenario: Sign rules for operands

  Given The calculator is on
  
  When I type in "first number"
  And I press "divide"
  And I type in "second number"
  And I press "equals"
  
  Then I see "minus" as prefix if one of the number is negative
  And the "divided number" as result
  
Scenario: Division isn't symmetric

  Given The calculator is on
  
  When I type in "first number"
  And I press "divide"
  And I type in "second number"
  And I press "equals"
  And I type in "first number"
  And I press "divide"
  And I type in "second number"
  And I press "equals"
  
  Then I see different results in first and second case
  
Scenario: Division when both operands are "zero"

  Given The calculator is on
  
  When I type in "zero"
  And I press "divide"
  And I type in "zero"
  And I press "equals"
  
  Then I see "Result is not defined" as output
  
Scenario: Recurring decimal case

  Given The calculator is on
  
  When I type in "first decimal number"
  And I press "divide"
  And I type in "second decimal number"
  And I press "equals"
  
  Then I see "divided number" with two digits of precision as result
  
Scenario: Press "/" more than one times

  Given The calculator is on
  
  When I press "divide"
  And I press "divide"
  
  Then I see "divide" one time ( Second "divide" replaces first "divide")
  
Scenario: Interleaving of more than one operators

  Given The calculator is on
  
  When I press "plus"
  And I press "multiply"
  And I press "divide"

  Then I see the last operator ( "divide" )
  
Scenario: When second operand is not present

  Given The calculator is on
  
  When I type in "first number"
  And I press "divide"
  And I press "equals"
  
  Then I see "one" as result
  ( default value of second operand is equal to the first operand)
  
Scenario: Division by any/all operands being fractions

  Given The calculator is on
  
  When I type in "first number"
  And I press "divide"
  And I type in "fraction number"
  And I press "equals"
  
  Then I see "divided fraction number" as result with two digits of precision
  
Scenario: Division of more than two numbers

  Given The calculator is on
  
  When I type in "first number"
  And I press "divide"
  And I type in "second number"
  And I press "divide"
  And I type in "third number"
  And I press "equals"
  
  Then I see "divided number" with operations carried out from left to right
  