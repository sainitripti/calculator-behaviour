# Multiplication
  
Scenario: Result overflow

  Given The calculator is on
  And user has a suffix table
  
  When I type in "first number"
  And I press "multiply"
  And I type in "second number"
  And I press "equals"
  
  Then I see part of multiplied output
  followed by a letter on overflow of the result

Scenario: Signs of the numbers

  Given The calculator is on
  
  When I type in "first number"
  And I press "multiply"
  And I type in "second number"
  And I press "equals"
  
  Then I see "multiplied result" as a result
  with "minus" prefix if one of the numbers is negative

Scenario: Zero value multiplication

  Given The calculator is on
  
  When I type in "first number"
  And I press "multiply"
  And I type in "zero"
  And I press "equals"
  
  Then I see "zero" as the result

Scenario: Multiplication by "one"

  Given The calculator is on
  
  When I type in "first number"
  And I press "multiply"
  And I type in "one"
  And I press "equals"
  
  Then I see "first number" as the result

Scenario: Decimal value multiplication

  Given The calculator is on
  
  When I type in "first decimal number"
  And I press "multiply"
  And I type in "second decimal number"
  And I press "equals"
  
  Then I see "multiplied decimal number" with two digits of precision as result

Scenario: Irrational value multiplication

  Given The calculator is on
  
  When I type in "irrational number"
  And I press "multiply"
  And I type in "irrational number"
  And I press "equals"
  
  Then I see "multiplied real number" rounded to two digits of precision as result

Scenario: Simple multiplication

  Given The calculator is on
  
  When I type in "first number"
  And I press "multiply"
  And I type in "second number"
  And I press "equals"
  
  Then I see "multiplied number" as result

Scenario: Rational multiplication
And operands are rational numbers

  Given The calculator is on
  
  When I type in "first number"
  And I press "multiply"
  And I type in "second number"
  And I press "equals"
  
  Then I see "multiplied rational number" as result

Scenario: Decimal & integer multiplication

  Given The calculator is on
  
  When I type in "decimal number"
  And I press "multiply"
  And I type in "integer number"
  And I press "equals"
  
  Then I see "multiplied decimal number" with two digits of precision as result

Scenario: More than two numbers multiplication

  Given The calculator is on
  
  When I type in "first number"
  And I press "multiply"
  And I type in "second number"
  And I press "multiply"
  And I type in "third number"
  And I press "equals"
  
  Then I see "multiplied number" with operations carried out from left to right

Scenario: Range of operand exceeds allowed limit

  Given The calculator is on
  
  When I type in large "first number"
  And I press "multiply"
  And I type in "second number"
  And I press "equals"
  
  Then I see "Input out of range" error

Scenario: Pressing "multiply button" more than one time

  Given The calculator is on
  
  When I press "multiply" more than one time
  
  Then I see "multiply" one time ( Second "multiply" replaces first "multiply")

Scenario: Interleaving operators (Press *, then press /, then press +)

  Given The calculator is on
  
  When I press "multiply"
  And I press "divide"
  And I press "plus"
  
  Then I see the last operator ( "plus" )

Scenario: Decimal value capping

  Given The calculator is on
  
  When I type in ten digit "decimal number"
  
  Then I cannot enter more digits to the number
