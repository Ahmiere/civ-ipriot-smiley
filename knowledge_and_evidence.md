# Evidence and Knowledge

This document includes instructions and knowledge questions that must be completed to receive a *Competent* grade on this portfolio task.

## 1. Required evidence

### 1.1. Answer all questions in this document

- Each answer should be complete, well-articulated, and within the specified word count limits (if added) for each question.
- Please make sure **all** external sources are properly cited.
- You must **use your own words**. Please include your full chat transcripts if you use generative AI in any way.
- Generative AI hallucinates, is not an authoritative source

### 1.2. Make all the required modifications to the code

- Please follow the instructions in this document to make the changes needed to the code.

- When requested to upload evidence, upload all screenshots to `screenshots/` and embed them in this document. For example:

```markdown
![Example Running Code](screenshots/screenshot1.png)
```

![Sample](screenshots/sample.png)
> Note the `!`, and the use of a relative path.

- You must upload the code into your GitHub repository.
- While you can use a branch, your code should be in main when you submit.
- Upload a zip of this repository to Blackboard when you are ready to submit.
- You will be notified of your result via Blackboard
- However, if using GitHub classrooms, you may also receive additional feedback on GitHub directly

### 1.3. Optional: Use of Raspberry Pi and SenseHat

Raspberry Pi or SenseHat is **optional** for this activity. You can use the included `sense_hat.py` file to simulate the SenseHat on your computer.

If you use a Pi, please **delete** the `sense_hat.py` file.

### 1.4. Accessible version of the code

This project relies on visual patterns that appear on an LED matrix. If you have any accessibility requirements, you can use the `udl/accessible` branch to complete the project. This branch provides an accessible code version that uses text-based patterns instead of visual ones.

Please discuss this with your lecturer before using that branch.

## 2. Specific Tasks & Questions

Address the following tasks and questions based on the code provided in this repository.

### 2.1. Set up the project locally

1. Fork this repository (if not using GitHub Classrooms)
2. Clone your repository locally
3. Run the project locally by executing the `main.py` file
4. Evidence this by providing screenshots of the project directory structure and the output of the `main.py` file

![Local Execution](screenshots/local_execution.png)

If you are running on a Raspberry Pi, you can use the following command to run the project and then screenshot the result:

```bash
ls
python3 main.py
```

### 2.2. Fundamental code comprehension

 Answer each of the following questions **as they relate to that code** supplied by in this repository (ignore `sense_hat.py`):

1. Examine the code for the `smiley.py` file and provide  an example of a variable of each of the following types and their corresponding values (`_` should be replaced with the appropriate values):

   | Type                    | name   | value         |
   | ----------              |--------|---------------|
   | built-in primitive type | dimmed | True          |
   | built-in composite type | YELLOW | (255, 255, 0) |
   | user-defined type       | Smiley | Smiley()      |

2. Fill in (`_`) the following table based on the code in `smiley.py`:

   | Object                   | Type                    |
   | ------------             |-------------------------|
   | self.pixels              | built-in composite type |
   | A member of self.pixels  | built-in primitive type |
   | self                     | user-defined type       |

3. Examine the code for `smiley.py`, `sad.py`, and `happy.py`. Give an example of each of the following control structures using an example from **each** of these files. Include the first line and the line range:

   | Control Flow | File      | First line | Line range |
   | ------------ |-----------| -------- |------------|
   |  sequence    | smiley.py | self.sense_hat = SenseHat()| 13 to 25   |
   |  selection   | sad.py    | if wide_open:| 26 to 30   |
   |  iteration   | happy.py  | for pixel in mouth:| 21 to 22   |

4. Though everything in Python is an object, it is sometimes said to have four "primitive" types. Examining the three files `smiley.py`, `sad.py`, and `happy.py`, identify which of the following types are used in any of these files, and give an example of each (use an example from the code, if applicable, otherwise provide an example of your own):

   | Type                    | Used? | Example                         |
   | ----------------------- |-------|---------------------------------|
   | int                     | yes   | WHITE = (255, 255, 255)         |
   | float                   | yes   | def blink(self, delay=0.25)     |
   | str                     | no?   | greeting = "hello"              |
   | bool                    | yes   | self.draw_eyes(wide_open=False) |

5. Examining `smiley.py`, provide an example of a class variable and an instance variable (attribute). Explain **why** one is defined as a class variable and the other as an instance variable.

    > "class Smiley:
    WHITE = (255, 255, 255)
    GREEN = (0, 255, 0)
    RED = (255, 0, 0)
    YELLOW = (255, 255, 0)
    BLANK = (0, 0, 0)" is an example of a class variable since it is 
   > defining the attributes of its self (the class).
     "Y = self.YELLOW" is an example of an instance variable as it does 
   > not define the attributes of the variable, rather it just references 
   > the class so that it can adjust some details within the class.

6. Examine `happy.py`, and identify the constructor (initializer) for the `Happy` class:
   1. What is the purpose of a constructor (in general) and this one (in particular)?

   > The purpose of a constructor is assign initial values to the instance 
   > variables (otherwise known as attributes) of an object. Which ensures 
   > that whenever the specific object that has been initialised is created 
   > it starts out with an already defined list of characteristics.

   2. What statement(s) does it execute (consider the `super` call), and what is the result?

   > The initialiser for the Happy class executes a total of three different 
   > statements, the first of which is a secondary initialiser that is used 
   > to initialise the parent classes "Smiley" and "Blinkable" which are 
   > both used within the Happy class.
   > The other two statements executed by the initialiser are calling upon  
   > functions (draw_mouth and draw_eyes) from the parent classes and draws 
   > the mouth and then the eyes of the Happy class output
   > 😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊

### 2.3. Code style

1. What code style is used in the code? Is it likely to be the same as the code style used in the SenseHat? Give to reasons as to why/why not:

> The code style of this code is following the PEP-8 style guide which is the standard, and since this is the standard I would say that it is highly likely that this code style is also used for the SenseHat.
>

2. List three aspects of this convention you see applied in the code.

> 1. The naming of variables and functions are done in snake_case
> 2. The imports within the code is positioned at the top of the file
> 3. Docstrings have been written for all public modules, functions, classes, and methods, which is placed after the "def" function.

3. Give two examples of organizational documentation in the code.

> Below is an example of how comments are never made longer than 72 characters long, which is mentioned within the PEP 8 standard
> 1.        Draws the eyes (open or closed) on the standard smiley.
> 2. Here is an example of docstrings being used in the Happy class
>    """
     Draws the eyes (open or closed) on the standard smiley.
     :param wide_open (bool): eyes open or closed.
     """


### 2.4. Identifying and understanding classes

> Note: Ignore the `sense_hat.py` file when answering the questions below

1. List all the classes you identified in the project. Indicate which classes are base classes and which are subclasses. For subclasses, identify all direct base classes.
  
  Use the following table for your answers:

| Class Name | Super or Sub? | Direct parent(s)  |
|------------|---------------|-------------------|
| Blinkable  | Super         | ABC               |
| Smiley     | Base          | N/A               |
| Happy      | Sub           | Smiley, Blinkable |
| Sad        | Sub           | Smiley            |

2. Explain the concept of abstraction, giving an example from the project (note "implementing an ABC" is **not** in itself an example of abstraction). (Max 150 words)

> Abstraction is the process of removing certain attributes to place more focus upon details that are deemed more important. An example from within this project is shown below for the blink function
> 
>      def blink(self):
>        pass

3. What is the name of the process of deriving from base classes? What is its purpose in this project? (Max 150 words)

> The process of deriving from base classes is referred to as inheritance, and the purpose it has for this project is to allow different classes to share a common function and be able to edit what it does to match its intended purpose for the class it's used in.


### 2.5. Compare and contrast classes

Compare and contrast the classes Happy and Sad.

1. What is the key difference between the two classes?
   > Well other than the names of the classes, I'd say that the key difference between the two classes is the fact that the 'Happy' class has 'Blinkable' as a second parent class, and uses a 'blink' function, while Sad only has 'Smiley' as its only parent class and doesn't use the blink function
   >
2. What are the key similarities?
   > Both classes have the parent class 'Smiley', and the initialiser function for both classes appear to be identical, both have the variable 'wide_open' set to true for their 'draw_eyes' function, and both use a 'draw_mouth' function
   >
3. What difference stands out the most to you and why?
   > Well other than the name for kind of obvious reasons, I'd say the difference that stands out the most is that the Happy class imports the Blinkable class
   > and uses the blink function from the Blinkable class, while the Sad class never imports the Blinkable class and instead it just redefines the blink
   > function within it's own class.
   
4. How does this difference affect the functionality of these classes
   > This difference has no real or significant affect on these classes, as both classes can use and execute the blink function with no issue and run it as intended.
   >

### 2.6. Where is the Sense(Hat) in the code?

1. Which class(es) utilize the functionality of the SenseHat?
   > The class that directly imports and utilises the functionality of SenseHat is the 'Smiley' class, however both the 'Sad' and 'Happy' classes import the SenseHat function from the 'Smiley' class
   >
2. Which of these classes directly interact with the SenseHat functionalities?
   > The class that directly interacts with the SenseHat functionalities is the class 'Smiley'
   >
3. Discuss the hiding of the SenseHAT in terms of encapsulation (100-200 Words)
   > Your answer here 😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊😊


### 2.7. Sad Smileys Can’t Blink (Or Can They?)

Unlike the `Happy` smiley, the current implementation of the `Sad` smiley does not possess the ability to blink. Let's first explore how blinking has been implemented in the Happy Smiley by examining the blink() method, which takes one argument that determines the duration of the blink.

**Understanding Blink Mechanism:**

1. Does the code's author believe that every `Smiley` should be able to blink? Explain.

> I'd say that the code's author does not believe that every 'Smiley' should be able to blink, since the author of this code has only utilised the blinkable class in the 'Happy class', there fore they most likely don't believe that sad smileys should have the ability to blink
>

2. For those smileys that blink, does the author expect them to blink in the same way? Explain.

> As only 1 smiley (the 'Happy' Smiley) has the function blink defined and used within its code, I would have to say yes. However if the blink function was used in more than one class I would change my answer to no, since within the blink function a delay is mentioned and set
>

3. Referring to the implementation of blink in the Happy and Sad Smiley classes, give a brief explanation of what polymorphism is.

> When referring to the implementation of blink in the Happy and Sad Smiley classes, Polymorphism in Python allows for the same function to be able to behave differently depending on the object that calls it. In this case when referring to the implementation of blink in the Happy and Sad classes, the Happy class edits certain attributes of the blink function while Sad does not currently have the blink function it would likely be changed in some way to better differentiate itself from the Happy class.
>

4. How is inheritance used in the blink method, and why is it important for polymorphism?

> Inheritance is used in the blink method to ensure that the Blinkable class is not incorporated directly as it defines an interface that has to be followed by all subclasses that use it. Inheritance is what enables the polymorphism, this is because the blinkable class shares the blink function with multiple other subclasses with eahc subclass representing the blink method differently
>
1. **Implement Blink in Sad Class:**

   - Create a new method called `blink` within the Sad class. Ensure you use the same method signature as in the Happy class:

   ```python
   def blink(self, delay=0.25):
       pass  # Replace 'pass' with your implementation
   ```

2. **Code Implementation:** Implement the code that allows the Sad smiley to blink. Use the implementation from the Happy Smiley as a reference. Ensure your new method functions similarly by controlling the blink duration through the `delay` argument.

3. **Testing the Implementation:**

- Test the new blink functionality on your Raspberry Pi or within the Python classes provided. You might need to adjust the `main.py` script to incorporate Sad Smiley's new blinking capability.

Include a screenshot of the sad smiley or the modified `main.py`:

![Sad Smiley Blinking](screenshots/sad_blinking.png)

- Observe and document the Sad smiley as it blinks its eyes. Describe any adjustments or issues encountered during implementation.

  > No issues were encountered during the implementation of the Sad smiley blink, however I did attempt to make the Sad smiley have a longer blink to signify low energy, but then I figured out that the blink duration was set within the main function. So no adjustments were made other than copying over the imports and blink function from the happy class to the sad class 

  ### 2.8. If It Walks Like a Duck…

  Previously, you implemented the blink functionality for the Sad smiley without utilizing the class `Blinkable`. Assuming you did not use `Blinkable` (even if you actually did), consider how the Sad smiley could blink similarly to the Happy smiley without this specific class.

  1. **Class Type Analysis:** What kind of class is `Blinkable`? Inspect its superclass for clues about its classification.

     > Blinkable is an Abstract Base class as signified by the 'ABC' parent class

  2. **Class Implementation:** `Blinkable` is a class intended to be implemented by other classes. What generic term describes this kind of class, which is designed for implementation by others? **Clue**: Notice the lack of any concrete implementation and the naming convention.

  > Blinkable is an 'Abstract class', which is the generic term describing the kind of class that is designed to be implemented by others. The generic term is 'abstract' or 'abstract classes'

  3. **OO Principle Identification:** Regarding your answer to question (2), which Object-Oriented (OO) principle does this represent? Choose from the following and justify your answer in 1-2 sentences: Abstraction, Polymorphism, Inheritance, Encapsulation.

  > The Object-Oriented principal that is represented by this class is Abstraction. I came to this conclusion after reviewing what ABC stood for in this context 'Abstract Base Class', therefore its abstraction.

  4. **Implementation Flexibility:** Explain why you could grant the Sad Smiley a blinking feature similar to the Happy Smiley's implementation, even without directly using `Blinkable`.

  > I am able to grant Sad Smiley a blinking feature similar to the Happy Smiley's implementation, even without directly using Blinkable, due to the fact that you are able to reuse behaviour the behaviour or even addnew functionality without the need of rigid inheritance heirarchies, this way the Sad class has no need to know of the Blinkable class and any objexct that defines a blink method can be inserted into my blinking system.
  5. **Concept and Language Specificity:** In relation to your response to question (4), what is this capability known as, and why is it feasible in Python and many other dynamically typed languages but not in most statically typed programming languages like C#? **Clue** This concept is hinted at in the title of this section.

  > In relation to my answer from question 4, this capability is known as "duck typing", and the reason why it works for dynamically typed languages (such as Python) is because dynamically typed languages dont have fixed types for their variables, type checking happens at the execution time, not during compilation. Therefore dynamically typed languages, such as Python, only care whether an object has the right method or attribute when it is used, not caring for the class it comes from. 
  > While statistically typed languages, such as C, are the opposite as they require type information during compile time, the compiler must know exactly what the type of each object is and what method it supports. You can't just pass any object with a blink() method without explicitly implementing an interface or inheriting from a known base class.
  ***

  ## 3. Refactoring

  ### 3.1. Does a Smiley Have to Be Yellow?

  While our current implementation predominantly features yellow smileys, emotional expressions like sickness or anger typically utilize colors like green, red, or orange. We'll explore the feasibility of integrating these colors into our smileys.

  1. **Defined Colors and Their Location:**

     1. Which colors are defined and in which class(s)?
        > The colours that are defined are white, green, red, yellow, and blank which refers to the colour black, all of these colours are defined in the Smiley class
     2. What type of variables hold these colors? Are the values expected to change during the program's execution? Explain your answer.
        > The type of variables that hold these colours are referred to as tuple variable containing multiple int variables, and no, these values are not expected to change during the program's execution due to the fact that these variables are in all uppercase, this signifies that they are a constant and should never be changed
     3. Add the color blue to the appropriate class using the appropriate format and values.

  2. **Usage of Color Variables:**

     1. In which classes are the color variables used?
        > Other than the Smiley class which creates and defines the different colour variables, and uses them to make the head. The colour variables are used in both the Happy and Sad classes to create the face and blink

  3. **Simple Method to Change Colors:**
  4. What is the easiest way you can think to change the smileys to green? Easiest, not necessarily the best!
     > The easiest way I would think to change the smileys to green instead of its current yellow would be to switch out the value of Y to be equal to the value of GREEN instead of YELLOW in the Smiley class.



  ### 3.2. Flexible Colors – Step 1

  Changing the color of the smileys once is straightforward, but it isn't very flexible. To facilitate various colors for smileys, it is advisable not to hardcode values in any class. This approach was identified earlier as a necessary change. Let's start by removing the built-in assumptions about color in our classes.

  1. **Add a method called `complexion` to the `Smiley` class:** Implement this instance method to return `self.YELLOW`. Using the term "complexion" instead of "color" provides a more abstract terminology that focuses on the meaning rather than implementation.

  2. **Refactor subclasses to use the `complexion` method:** Modify any subclass that directly accesses the color variable to instead utilize the new `complexion` method. This ensures that color handling is centralized and can be easily modified in the future.

  3. **Determine the applicable Object-Oriented principle:** Consider whether Abstraction, Polymorphism, Inheritance, or Encapsulation best applies to the modifications made in this step.
     > The Object-Oriented Principle that best applies to the modifications made in this step would be Encapsulation. 

  4. **Verify the implementation:** Ensure that the modifications function as expected. The smileys should still display in yellow, confirming that the new method correctly replaces the direct color references.

  This step is crucial for setting up a more flexible system for color management in the smiley display logic, allowing for easy adjustments and extensions in the future.

  ### 3.3. Flexible Colors – Step 2

  Having removed the hardcoded color values, we now enhance the base class to support dynamic color assignments more effectively.

  1. **Modify the `__init__()` method in the `Smiley` class:** Introduce a default argument named `complexion` and assign `YELLOW` as its default value. This allows the instantiation of smileys with customizable colors.

  2. **Introduce a new instance variable:** Create a variable called `my_complexion` and assign the `complexion` parameter to it. This step ensures that each smiley instance can maintain its own color state.

  3. **Rationale for `my_complexion`:** Using a distinct instance variable like `my_complexion` avoids potential conflicts with the method parameter names and clarifies that it is an attribute specific to the object.

  4. **Bulk rename:** We want to update our grid to use the value of complexion, but we have so many `Y`'s in the grid. Use your IDE's refactoring tool to rename all instances of the **symbol** `Y` to `X`. Where `X` is the value of the `complexion` variable. Include a screenshot evidencing you have found the correct refactor tool and the changes made.

  ![Bulk Rename](screenshots/bulk_rename.png)

  5. **Update the `complexion` method:** Adjust this method to return `self.my_complexion`, ensuring that whatever color is assigned during instantiation is what the smiley displays.

  6. **Verification:** Run the updated code to confirm that Smileys still defaults to yellow unless specified otherwise.

  ### 3.4. Flexible Colors – Step 3

  With the foundational changes in place, it's now possible to implement varied smiley colors for different emotional expressions.

  1. **Adjust the `Sad` class initialization:** In the `Sad` class's initializer method, change the superclass call to include the `complexion` argument with the value `self.BLUE`, as shown:

     ```python
     super().__init__(complexion=self.BLUE)
     ```

  2. **Test color functionality for the Sad smiley:** Execute the program to verify that the Sad smiley now appears blue.

  3. **Ensure the Happy smiley remains yellow:** Confirm that changes to the Sad smiley do not affect the default color of the Happy smiley, which should still display in yellow.

  4. **Design and Implement An Angry Smiley:** Create an Angry smiley class that inherits from the `Smiley` class. Set the color of the Angry smiley to red by passing `self.RED` as the `complexion` argument in the superclass call.

  ***


