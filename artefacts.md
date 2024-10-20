Object Oriented Programming - Artefacts 

On this page are a number of artefacts that I have gather from my studies of Object Oriented Programming as part of my MSc Computer Science course. These show my development relating to coding practice, UML and computing theory that aligns with OOP.


### Unit 2: UML Modelling to Support Secure System Planning

Below is a discussion on ISO/IEC 27000 and how people management techniques can ensure compliance of this.

[ISO/IEC 27000 Standards](/pdf/individuals_security.pdf)


### Unit 5: An Introduction to Testing

Below is a discussion regarding the relevance of Cyclomatic Complexity in modern day programming.

[Exploring the Cyclomatic Complexity’s Relevance Today](/pdf/cyclomatic_complexity.pdf)


### Unit 8: Cryptography and Its Use in Operating Systems

Below is a discussion on an encryption algorithm, and whether it is effective.

[Cryptography Programming Exercise](/pdf/encryption_algorithm.pdf)





### Artefact 4: Python Code Showing Protected and Unprotected Variables

The below artefact shows how I meet Learning Outcome 2) Design and implement programs that demonstrate appropriate use of object-oriented design principles.

```
        class Student:
          def __init__(self, name, age, ID):
            self.name = name # this is an unprotected variable
            self.age = age # this is unprotected
            self._ID = ID # the “_” prior to “ID” highlights this as a protected variable
        
        s1 = Student("Billy", 15, 1443)
        
        print(s1.name)
        print(s1.age)
        print(s1._ID)
```

---
### Artefact 5: Polymorphism Example

The below artefact also shows how I meet Learning Outcome 2) Design and implement programs that demonstrate appropriate use of object-oriented design principles.

```
    class SteerLeft:
        def __init__(self, direction, degrees):
            self.direction = direction 
            self.degrees = degrees
    
        def info(self):
            print(f"Turning {self.direction} for {self.degrees}.")
    
    
    
    class SteerRight:
        def __init__(self, direction, degrees):
            self.direction = direction # this has been reused from the SteerLeft class as a form of polymorphism
            self.degrees = degrees
    
        def info(self):
            print(f"Turning {self.direction} for {self.degrees}.")
        
    
    Left1 = SteerLeft("Left", 90)
    Right1 = SteerRight("Right", 90)
    
    for directional in (Left1, Right1):
        directional.info()
```

---
### Artefact 6: Discussion On Cyclomatic Complexity

The below artefact shows how I meet Learning Outcome 1) Appraise and critically evaluate object-oriented programming compared to other programming paradigms.

[Cyclomatic Complexity](/pdf/cyclomatic_complexity.pdf)




