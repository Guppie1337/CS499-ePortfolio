## Introduction

In this portfolio, I will present several projects that were created throughout my college courses. Although given the opportunity to work with items completed for coursework, I've decided to use some personal projects to further demonstrate a "before and after" approach. Not only do I hope to express my thoughts thoroughly, but I hope my transition is worthy enough to inspire others to keep learning!

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

## Projects
### Munchy Bear (Software Engineering/Design)

Munchy Bear is a simple arcade game developed in Unity3D for mobile devices; specifically Android. It was the first project I ever completed on my own (except for my wife's art) to get a better understanding of the development process from concept to publish. When I first went through the process of programming it, I was very new to understanding Object Oriented Programming and had very little concept of abstraction. I ended up putting all of the logic for state transitions in the Update method (Unity game loop lifecycle) via nested booleans, and only realized the complexity when more than 2 states existed; Play. Pause, and Game Over. Due to this, I feel the project is great for demonstrating my ability abstract a state machine and reassign responsibilities.

### Character Concept Lab (Algorithms and Data Structure)

Character Concept Lab is yet again a mobile app developed in Unity3D. This application is designed to be used as a base tool for anyone working with concept creation; artists, writers, table-top RPG players, and more. Overall, the idea is very simple. You get attributes from some kind of data store and display them to the user through a healthy blend of logic. Although very simple, there is always room for improvement. My initial approach was to name a text file for each attribute and parse it line by line to retrieve the information. This implementation worked well to get the project done, but it left little room for extensibility. Furthermore, it was very explicit on the file searching and was not structure well at all. To utilize a more relational data structure, I decided a transition to XMLwould be more appropriate for populating collections.


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
