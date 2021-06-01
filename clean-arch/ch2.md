## A Tale of Two Values
Every software system provides two different values to stakeholders: behavior and structure.
Developers are responsible for ensuring both of these values remain high. They typically focus on the lesser of two values, leaving the system eventually valueless.

## Behavior
Developers help make the stakeholders a functional specification, or requirements document. Then, they write the code that satisfy those requirements.

## Architecture
Sofware - intended to be an avenue to easily change the behavior of machines.
    * must be "soft" - easy to change
    * When stakeholders change requirements, the change should be simple and easy to make. 

Differences between scope and shape often drive the growth in software development costs. It's the reason that costs grow out of proportion to the size of requested changes.
Each new request is harder to fit than the last in an ever-increasing complex puzzle.

The more an architecture prefers one shape over another, the more likely new features will be harder to fit into that structure. Therefore, architectures should be as shape agnostic as practical.

## The Greater Value
Function or architecture? Which of these two provide greater value? Is it more important for software system to work, or is it more important for the software system to be easy to change?
Systems can become *impossible* to change because the cost of change exceeds the benefit of the change.

## Eisenhower's Matrix



  Important / Urgent   |  Important / Not Urgent   
-----------------------|----------------------------
  Unimportant / Urgent |  Unimportant / Not Urgent  


The first value of software (behavior) is urgent but not always important.
The second value of software (architecture) is important but not always urgent.

The dilemma for devs is that business managers are not equipped to evaluate the important of architecture. It is the responsibility of the dev team to assert the importance of architecture over the urgency of features.

## Fight for the Architecture
It's always a struggle. Developers fight for what they believe is best for the company and so does management/marketing.
Ultimately, a developer *is* a stakeholder. You fight for the software you need to safeguard. Software architects are, by virtue, more focused on the structure of the system rather its features and functions. Architects create an architecture that allows those features and functions to be easily developed, easily modified, and easily extended.

If architecture comes last, then the system will become ever more costly to develop, and eventually change will be become practically impossible for part or all of the system.
