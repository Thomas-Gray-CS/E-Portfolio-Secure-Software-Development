System Implementation Assignment - Driverless Car

Below is the Python code to support the operation of a driverless car, as well as an accompanying file that explains my thought processes and decision making while completing this. This contributes to and shows how I meet Learning Outcomes:
1) Appraise and critically evaluate object-oriented programming compared to other programming paradigms.
2) Design and implement programs that demonstrate appropriate use of object-oriented design principles.
3) Select and use appropriate data structures for a given problem..


### Python Code To Support The Operation Of A Driverless Car                                                                                                      


  ```
      class DriverlessCar:
      # Initial class for the car
      
        make = "Ford"
        model = "Fiesta"
        id = 13344
        build_year = 2023
        registration = "DN23 RPF"
      # The above is just generic information about the vehicle
        
      class TripComputer: # Class for the trip computer and car controls
      
        current_speed = 0 # Will be modified by functions and inputs as needed
        max_speed = 150  # Top speed before braking automatically
        car_in_use = True 
        car_forward = True 
        car_reverse = True 
        car_steer_left = True 
        car_steer_right = True 
        car_speed_up = True 
        car_slow_down = True
        car_brake = True 
      
      # Each of the above is set with a Boolean to represent that they can be
      # on (True) or off (false) as there are no other states that they can
      # be in
        
        def __init__(self, start, stop, forward, reverse, steerleft, steerright, speedup, slowdown, brake):
          self.start = start
          self.stop = stop
          self.forward = forward
          self.reverse = reverse
          self.steerleft = steerleft
          self.steerright = steerright
          self.speedup = speedup
          self.slowdown = slowdown
          self.brake = brake 
      
      # Each of functions is initialised within itself to ensure that they are
      # all available as all will be required
      
          def start(self):
            if self.car_in_use:
              print("Vehicle Starting")
          endif  
      
          def stop(self):
            if not self.car_in_use:
              print("Vehicle Stopping")
          endif 
      
          def forward(self):
            if self.car_forward:
              print("Car Moving Forward")
          endif
      
          def reverse(self):
            if self.reverse:
              print("Car Reversing")
          endif
      
          def steerleft(self):
            if self.steerleft:
              print("Car Turning Left")
          endif
      
          def steerright(self):
            if self.steerright:
              print("Car Turning Right")
          endif
      
      # Each of the above are written so that if the relative attribute is
      # true (as in, it is on), the relative function will execute
      
          def speedup(self):
            if current_speed < sign_value:
              current_speed = sign_value
            else:
              current_speed = current_speed
      
          def slowdown(self):
            if current_speed > sign_value:
              current_speed = sign_value
            else:
              current_speed = current_speed
      
          def brake(self):
            if self.hazard_detected:
              current_speed = 0
            else:
              current_speed = current_speed 
      
      # The three above functions should allow for the current speed
      # to be amended from either hazard or speed sign inputs
      # with the ability to maintain speed if not detected 
      
          def createtripdictionary():
            dict = {
              T_F1: start,
              T_F2: stop,
              T_F3: forward,
              T_F4: reverse,
              T_F5: steerleft,
              T_F6: steerright,
              T_F7: speedup,
              T_F8: slowdown,
              T_F9: brake,
            }    
            return dict
      
          tripdictionary = createtripdictionary   
      
      # The dictionary for the trip computer makes it easier for functions
      # to be called when required
      
      class SpeedSensor:
      
        current_speed = () # This allows for speed to be updated in time
        speed_sign_detected = True # Boolean for sign dection
        sign_value = () # Value of sign to be added as detected
      
        def __init__(self, nosign, twenty, thirty, forty, fifty, sixty, seventy):
          self.nosign = nosign
          self.twenty = twenty
          self.thirty = thirty
          self.forty = forty
          self.fifty = fifty
          self.sixty = sixty
          self.seventy = seventy
      
      # Above functions allow for all speed signs on British roads
      
          def nosign(self):
            if not speed_sign_detected.self:
              current_speed = current_speed
      
      # If no sign detected (False), speed remains the same 
      
          def twenty(self):
            if speed_sign_detected.self and sign_value == twenty:
              current_speed = 20
          
          def thirty(self):
            if speed_sign_detected.self and sign_value == thirty:
              current_speed = 30
      
          def forty(self):
            if speed_sign_detected.self and sign_value == forty:
              current_speed = 40  
      
          def fifty(self):
            if speed_sign_detected.self and sign_value == fifty:
              current_speed = 50  
      
          def sixty(self):
            if speed_sign_detected.self and sign_value == sixty:
              current_speed = 60  
      
          def seventy(self):
            if speed_sign_detected.self and sign_value == seventy:
              current_speed = 70  
      
      # Above functions change speed once sign detected, and change
      # to value of applicable sign
      
          def createspeeddictionary():
      
            dict = {
              s_F1: nosign,
              S_F2: twenty,
              S_F3: thirty,
              S_F4: forty,
              S_F5: fifty,
              S_F6: sixty,
              S_F7: seventy
            }
            return dict
      
          speeddictionary = createspeeddictionary
      
      # Dictionary created for the speed sign functions for easier recall
      # and efficiency
      
      class HazardSensor:
      
        hazard_detected = True
        
        def __init__(self, hazard):
      
          def hazard(self):
            if self.hazard_detected:
              current_speed = 0
            else:
              current_speed = current_speed
      
      # Simple class and function for hazards. All hazards will require 
      # the car to slow down. If no hazard detected, no change needed
      
      class GPS:
      
        current_location = ()
        destination = ()
        start_point = ()
      
      # Above attributes are able to be amended as users input for
      # journeys
      
        destination_list = [] # List created to store previous destinations
      
        def __init__(self, journeyended, journeystart, savedestination, searchdestination):
          self.journeyended = journeyended
          self.jounryestart = journeystart
          self.savedestination = savedestination
          self.searchdestination = searchdestination
      
          def journeyended(self):
            if current_location == destination:
              print("Destination Reached")
          endif
      
          def journeystart(self):
            if current_location == start_point:
              print("Begin Journey")
          endif
      
      # Above two functions are able to identify both start and end of
      # journey, informing passengers of this
      
          def savedestination(self):
            if destination not in destination_list:
              destination_list.append(destination)
          endif
      
      # Above function allows for destinations to be added to the list
      # as required
      
          def searchdestination(self):
            if destination in destination_list:
              print(destination) in destination_list
          endif
      
      # Above function allows passengers to search for destinations and
      # use them
      
          def creategpsdictionary():
      
            dict = {
              G_F1: journeyended,
              G_F2: journeystart,
              G_F3: savedestination,
              G_F4: searchdestination
            }
            return dict
      
          gpsdictionary = creategpsdictionary
          
      # Dictionary created to store GPS functions for efficiency and useability
      ```

---
### README File Explaining The System Implementation

[System Implementation](/pdf/system-implementation.pdf)


