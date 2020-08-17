# Power on and power off
  
Scenario: Power on the calculator

  Given The calculator is off
  
  When I press "on/off"
  
  Then I see screen sets to "zero"

Scenario: Power off the calculator

  Given The calculator is on
  And screen displays either "zero" or previous calculations
  
  When I press "on/off"
  
  Then I see screen sets to no display
  