# Subtraction

Scenario: Subtraction of "positive number" from "positive number"
When first number is larger than second number
  
  Given The calculator is on
  
  When I type in "positive number"
  And I press "minus"
  And I type in "positive number"
  And I press "equals"
  
  Then I see the "subtracted number" as the result

Scenario: Subtraction of "positive number" from "positive number"
When first number is smaller than second number
  
  Given The calculator is on
  
  When I type in "positive number"
  And I press "minus"
  And I type in "positive number"
  And I press "equals"
  
  Then I see "minus" prefix
  And the "subtracted number" as the result
  
Scenario: Subtraction of "positive number" from "negative number"
  
  Given The calculator is on
  
  When I type in "negative number"
  And I press "minus"
  And I type in "positive number"
  And I press "equals"
  
  Then I see "minus" as prefix
  And the "subtracted number" as the result

Scenario: Subtraction of "fraction" from "fraction"
  
  Given The calculator is on
  
  When I type in "first fraction"
  And I press "minus"
  And I type in "second fraction"
  And I press "equals"
  
  Then I see "subtracted fraction"
  with no common factor in numerator and denominator form as the result

Scenario: Subtraction of "decimal number" from "decimal number"
  
  Given The calculator is on
  
  When I type in "first decimal number"
  And I press "minus"
  And I type in "second decimal number"
  And I press "equals"
  
  Then I see "subtracted decimal number" with two digits of precision as the result

Scenario: Typing operator more than once
  
  Given The calculator is on
  
  When I type "first operator"
  And I type "second operator"
  
  Then I see "second operator" replaces "first operator"
  
Scenario: Subtraction of more than two numbers
  
  Given The calculator is on
  
  When I type "first number"
  And I press "minus"
  And I type "second number"
  And I press "minus"
  And I type "third number"
  And I press "equals"
  
  Then I see difference of all numbers with operations carried out from left to right
  
Scenario: Subtraction of numbers where the result goes out of range
  
  Given The calculator is on
  And user has a suffix table
  
  When I type "first operand"
  And I press "minus"
  And I type "second operand"
  And I press "equals"
  
  Then I see four digit output followed by a letter as the result
  
Scenario: Identity operation
  
  Given The calculator is on
  
  When I type "number"
  And I press "minus"
  I type "zero"
  And I press "equals"
  
  Then I see "number" as the result
  
Scenario: Converse operation
  
  Given The calculator is on
  
  When I type "zero"
  And I press "minus"
  I type negative of "number"
  And I press "equals"
  
  Then I see negative of "number" as the result
