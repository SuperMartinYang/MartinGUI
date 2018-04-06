# MartinGUI

Based on the thought of [FishGUI](http://product.dangdang.com/1024374277.html), MartinGUI is using Python

Program based on MartinGUI: Code once, Run anywhere

## Steps

### 1. Requirement

define what we need to do

* Objective and Range

* Stakeholder

* Non-functional requirement

* Analyze functional requirement (Using Example analysis)

* Write Requirement Instruction 

| Instruction Name | MartinGUI Requirement Instruction | Privacy Level | Public |
|---------------------------|-----------------------------------------------------|--------------------|----------|
| Instruction Num | 0.1 | Editor | Martin Yang |
|Edite Date | 2018.03.03 | Reviewer | Martin Yang |
| Review Date | 2018.03.28 | Total Page | \** |

| Project Name | MartinGUI |
|---------------------|-----------------|
| Project Description | GUI framework, can provide Embed system a Graphic environment |
| User Describe | public |
| Functional Requirement | Can support User Interface described below: <br />* Create a Main Window when system boot<br />* Create multiple Controls (such as buttons, labels, and edit boxes)<br />* Provide animation function<br />* User can input Numbers into edit box<br />* User can use mouse to click buttons, then trigger some actions<br />* Create a new Window which is over the main Window<br />* User can operate Controls on new Window<br />* When there's an animation runs on main Window, even though a new Window is over main Window, animation still plays<br />* some specific button in keyboard could invoke specific function |
| Use Cases | ... |
| Restriction | Mouse can only control the active Window<br />Windows back cannot be move to the front<br />Windows below can get timer message to make animation active<br />Window level is limited to 3 |
| Non-functional Requirement | Can be secondary development<br />Can be used in deferent system which has Python installed<br />The speed should be acceptable|

### 2.Analyze Use Case 

* Decide System Boundary 
* Decide participants
* Come up with all Use Cases
* Decide the level of each case
* Describe each case in words
* Draw a Object Flowchart

``` mermaid
graph LR
A[User] --Computer--> B[Application]
B --> C[MartinGUI framework]
C --> D[OS]
C --> E[Graphic Panel]
```
Figure 1. System Boundary

``` mermaid
graph LR
A((User)) --> B((Boot System))
A --> C((Choose 400))
A --> D((Choose Cancel))
A --> E((Open Window1))
A --> F((Input Words))
A --> G((Start Animation))
H((Timer)) --> G
B --> I((Create Window))
E --> I
I --> J((Create Button))
I --> K((Create Edit))
I --> L((Create Check box))
I --> M((Create Radio Button))
I --> N((Create Label))
I --> O((Create Group))
I --> P((Create Bitmap))
```
Figure 2. Use Case Analysis

Describe Use Case:
* Use Case name: Boot System
* User purpose: display main window and controls
	* Pre-requisite: None
	* Steps:
		* User boot system
		* Create a main window in screen
		* Create controls on main window

``` mermaid
sequenceDiagram
participant User
participant OS

User->OS: Button(TAB)
OS->OS: change focus
loop check
	User->OS: Button(0)
	OS->OS: display No. 
end
note right of OS: repeat to check digit button
```

Figure 3. Sequence Diagram of Input Words

``` mermaid
sequenceDiagram
participant User
participant OS
participant Timer

User->OS: click mouse (left, x, y)
OS->OS: set Timer
loop check
	Timer->OS: Tick()
	OS->OS: switch bitmap
end
```

Figure 4. Create Animation


## Design method
High cohesion and low coupling ensuring these probabilities: 
1. readability 
2. reusability 
3. extensibility 
4. maintainability 

### Terms: 
Encapsulation(properties and methods), inheritance, and polymorphism(same method name, different method body) are three fundamental principles of OOLs
Generalization is the inverse of inheritance
Parent Class & Child Class <-> SuperClass & SubClass <-> BaseClass & DerivedClass

### Principles
开闭原则:一个模块对扩展应是开放的，对修改应是关闭的
完全替换原则:派生类应该能完全替换掉基类
依赖倒置原则:依赖于抽象，而不要依赖于具象
非循环依赖、原则:包和包之间不能有循环依赖、关系
只实现你真正需要的东西，不要去实现你认为需要的东西
不要重复自己:任何代码都只出现一次
保持简化的设计
为人写代码，而不是为机器写代码

### Steps of OO development
OO analysis
structure analysis
OO design
Programming (libraries & framework: system [.NET, MFC], middleware [EJB], industry, white-box, black-box)
Testing

### s/w life cycle model
waterfall model
Iterative model


## Design Patterns
### Purposes:
1. Adapt to the change of requirement
1. For interface programming, not for programming
1. Use aggregation (interface) first rather than inheritation (class)

### Classification: 
Based on Purpose:
* Creational: encapsulate the process of creating Object
* Structural: deal with the structure of Object
* Behavioural: iteractive between Objects

Based on Scope:
* Class (static): relation between baseClass and derivedClass 
* Object (dynamic): relation between Objects

![Diagram](http://img.chongchonggou.com/upload/1/57/157c1d76b2f082f91bb17d42f0292de9.png)

![23 design patterns](https://img-blog.csdn.net/20170429095108968?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdm9wNDQ0/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)

