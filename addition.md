# Addition

Scenario: Addition of two positive numbers
  
  Given The calculator is on
  
  When I type in "positive number"
  And I press "plus"
  And I type in "positive number"
  And I press "equals"
  
  Then I see the "added number" as the result
  
Scenario: Addition of two negative numbers
  
  Given The calculator is on
  
  When I type in "negative number"
  And I press "plus"
  And I type in "negative number"
  And I press "equals"
  
  Then I see "minus" as prefix
  And the "added number" as the result

Scenario: Addition of fractions
  
  Given The calculator is on
  
  When I type in "first fraction"
  And I press "plus"
  And I type in "second fraction"
  And I press "equals"
  
  Then I see "added fraction" with no common factor in numerator and denominator form as the result

Scenario: Addition of "negative number" and "positive number"
  
  Given The calculator is on
  
  When I type in "negative number"
  And I press "plus"
  And I type in "positive number"
  And I press "equals"
  
  Then I see sign of greater number as prefix
  And the "subtracted number" as the result

Scenario: Addition of decimals
  
  Given The calculator is on
  
  When I type in "first decimal number"
  And I press "plus"
  And I type in "second decimal number"
  And I press "equals"
  
  Then I see "added decimal number" with two digits of precision as the result

Scenario: Typing operator more than once
  
  Given The calculator is on
  
  When I type "first operator"
  And I type "second operator"
  
  Then I see "second operator" replaces "first operator"
  
Scenario: Addition of more than two numbers
  
  Given The calculator is on
  
  When I type "first number"
  And I press "plus"
  And I type "second number"
  And I press "plus"
  And I type "third number"
  And I press "equals"
  
  Then I see sum of all numbers with operations carried out from left to right
  
Scenario: Adding numbers where the result goes out of range
  
  Given The calculator is on
  And user has a suffix table
  
  When I type "first operand"
  And I press "plus"
  And I type "second operand"
  And I press "equals"
  
  Then I see four digit output followed by a letter as the result
  
Scenario: Identity operation
  
  Given The calculator is on
  
  When I type "zero"
  And I press "plus"
  I type "number"
  And I press "equals"
  
  Then I see "number" as the result
  
Scenario: Converse operation
  
  Given The calculator is on
  
  When I type "number"
  And I press "plus"
  I type negative of "number"
  And I press "equals"
  
  Then I see "zero" as the result
