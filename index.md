## Introduction

      In this portfolio, I will present several projects that were created throughout my college courses. Although given the opportunity to work with items completed for coursework, I've decided to use some personal projects to further demonstrate a "before and after" approach. Not only do I hope to express my thoughts thoroughly, but I hope my transition is worthy enough to inspire others to keep learning!

      Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

## Projects
1. Munchy Bear
2. Character Concept Lab
3. Campsite Locator

### Initial Code Review
Link to video goes here.

### Munchy Bear (Software Engineering/Design)

      Munchy Bear is a simple arcade game developed in Unity3D for mobile devices; specifically Android. It was the first project I ever completed on my own (except for my wife's art) to get a better understanding of the development process from concept to publish. When I first went through the process of programming it, I was very new to understanding Object Oriented Programming and had very little concept of abstraction. I ended up putting all of the logic for state transitions in the Update method (Unity game loop lifecycle) via nested booleans, and only realized the complexity when more than 2 states existed; Play. Pause, and Game Over. Due to this, I feel the project is great for demonstrating my ability to abstract a state machine and reassign responsibilities.

![Munchy Bear Image](https://guppie1337.github.io/ceastridge-snhu-cs499/munchy_bear_display.png)

      _Reflection:_ 
      When I first started to consider implementing the state machine/abstraction refactor, I considered the change to be a relatively simple task. However, once I started to design how and where states would transition information, I ran into the same issue but with more classes. To make things nicer, I created a “singleton” type of object that references all the controllers in the game scene. Once the references were established, the state machines would handle most of the work by talk directly with the controllers required. 
      
      The good thing about games, most of the transitional methods are obvious; you activate, deactivate, and update everything. This made it easy for me to decide on an abstract base class that each state would implement and override. Considering that my game has scenes which automatically destroys and recreates objects on load transitions, I’ve considered that idea of making the menu and achievements board into UI panels and utilizing states to have them overlay the gameplay scene. This way, if the user decides to view either of those during play they don’t have to wait for everything to load all over again. Furthermore, this would take advantage of the optimization of memory management within the game.

      The biggest challenge I’ve faced is the amount of tight coupling that exists within the project. It’s absolutely astounding how much you can get done even though you don’t have the best practices. Being that it was so tightly coupled, it has proven to be a very tedious process to clean everything up and reorganize responsibilities. Although the state machine is working, some of the implementation is still hardcoded through the singleton object class where the responsibility should not exist in. This refactoring of responsibilities will be the biggest part of the abstraction. However, once it’s complete, any future refactors should be much easier and cleaner to accomplish. 

### Character Concept Lab (Algorithms and Data Structure)

      Character Concept Lab is yet again a mobile app developed in Unity3D. This application is designed to be used as a base tool for anyone working with concept creation; artists, writers, table-top RPG players, and more. Overall, the idea is very simple. You get attributes from some kind of data store and display them to the user through a healthy blend of logic. Although very simple, there is always room for improvement. My initial approach was to name a text file for each attribute and parse it line by line to retrieve the information. This implementation worked well to get the project done, but it left little room for extensibility. Furthermore, it was very explicit on the file searching and was not structured well at all. To utilize a more relational data structure, I decided a transition to XML would be more appropriate for populating collections.

![Character Concept Lab Image](https://guppie1337.github.io/ceastridge-snhu-cs499/character_concept_lab_display.JPG)


### Campsite Locator (Databases)

      Campsite Locator is the only addition to this portfolio that was directly coursework. The concept was to hold a database of campsites and allow individuals to search for them. The initial implementation would override any Google Maps/Location API search results and populate the campsite on the map and parse the associated information. The campsites would each populate a flyout drawer to give the user information about the campsite. All the information for each campsite I wanted the user to know was associated in the Campsite class (Data Access Object). Instead of keeping this approach, I've decided to go with an approach that focused on _User Experience_ that takes advantage of both the Google Maps/Location API and my hard-implemented database for campsites. 

![Campsite Locator Image](https://guppie1337.github.io/ceastridge-snhu-cs499/campsite_locator_display.png)

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Guppie1337/CS499-ePortfolio/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
