# What is Design and Architecture?
No difference between the two. 

Traditional definitions:
Architecture: context of a system at a high level that is divorced from lower-level details.
Design: implies structures and decisions at a lower level

The low-level details support the high-level details. They're both part of the same whole. 

## The Goal?
The goal of software architecture is to minimize the human resources required to build and maintain the required system.

The measure of design quality is simply the measure of the effort required to meet the needs of the customer. If that effort is low, and stays low throughout its lifetime, the design is good. If that effort grows with each new release, the design is bad. 

## Signature of Mess
Ever-increasing support of developers -> growth of code is approaching an asymptote
    - This trend isn't sustainable, no matter the profit of the company
Cost per LOC rising per release

Productivity by release declines while developer effort hasn't decreased. Despite heroics, overtime, and dedication, their effort has diverted away from features and is now consumed with managing the mess.

## What Went Wrong?
Developers urge "we'll clean it up later, get it to market first!"
Either never gets cleaned up or gets to market and now one has to keep up with competitors as well as their mess. Realistically, the mess is never cleaned because features need to keep being shipped and there's no time for the piling mess.

## Conclusion
Best option for a development organization is to recognize and avoid its own overconfidence and to take quality seriously. Build a system that minimizes effort and maximizes productivity.
