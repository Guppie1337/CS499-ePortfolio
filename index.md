## Introduction

In this portfolio, I will present several projects that were created throughout my college courses. Although given the opportunity to work with items completed for coursework, I've decided to use some personal projects to further demonstrate a "before and after" approach. Not only do I hope to express my thoughts thoroughly, but I hope my transition is worthy enough to inspire others to keep learning!

## Projects
1. Munchy Bear
2. Character Concept Lab
3. Campsite Locator

### Initial Code Review

If you wish to watch the initial code review, you can find it here:
[Initial Code Review (YouTube)](https://youtu.be/0-OJduv94QE)

### Munchy Bear (Software Engineering/Design)

Munchy Bear is a simple arcade game developed in Unity3D for mobile devices; specifically Android. It was the first project I ever completed on my own (except for my wife's art) to get a better understanding of the development process from concept to publish. When I first went through the process of programming it, I was very new to understanding Object Oriented Programming and had very little concept of abstraction. I ended up putting all of the logic for state transitions in the Update method (Unity game loop lifecycle) via nested booleans, and only realized the complexity when more than 2 states existed; Play. Pause, and Game Over. Due to this, I feel the project is great for demonstrating my ability to abstract a state machine and reassign responsibilities.

Here is a link to this project's final review: [Munchy Bear Final Code Review (YouTube)](https://youtu.be/EeXfDLnrCFw)

![Munchy Bear Image](https://guppie1337.github.io/ceastridge-snhu-cs499/munchy_bear_display.png)


**_Reflection:_** 

When I first started to consider implementing the state machine/abstraction refactor, I considered the change to be a relatively simple task. However, once I started to design how and where states would transition information, I ran into the same issue but with more classes. To make things nicer, I created a “singleton” type of object that references all the controllers in the game scene. Once the references were established, the state machines would handle most of the work by talk directly with the controllers required. 
      
The good thing about games, most of the transitional methods are obvious; you activate, deactivate, and update everything. This made it easy for me to decide on an abstract base class that each state would implement and override. Considering that my game has scenes which automatically destroys and recreates objects on load transitions, I’ve considered that idea of making the menu and achievements board into UI panels and utilizing states to have them overlay the gameplay scene. This way, if the user decides to view either of those during play they don’t have to wait for everything to load all over again. Furthermore, this would take advantage of the optimization of memory management within the game.

The biggest challenge I’ve faced is the amount of tight coupling that exists within the project. It’s absolutely astounding how much you can get done even though you don’t have the best practices. Being that it was so tightly coupled, it has proven to be a very tedious process to clean everything up and reorganize responsibilities. Although the state machine is working, some of the implementation is still hardcoded through the singleton object class where the responsibility should not exist in. This refactoring of responsibilities will be the biggest part of the abstraction. However, once it’s complete, any future refactors should be much easier and cleaner to accomplish. 

### Character Concept Lab (Algorithms and Data Structure)

Character Concept Lab is yet again a mobile app developed in Unity3D. This application is designed to be used as a base tool for anyone working with concept creation; artists, writers, table-top RPG players, and more. Overall, the idea is very simple. You get attributes from some kind of data store and display them to the user through a healthy blend of logic. Although very simple, there is always room for improvement. My initial approach was to name a text file for each attribute and parse it line by line to retrieve the information. This implementation worked well to get the project done, but it left little room for extensibility. Furthermore, it was very explicit on the file searching and was not structured well at all. To utilize a more relational data structure, I decided a transition to XML would be more appropriate for populating collections.

Here is a link to this project's final review: [Character Concept Lab Final Code Review (YouTube)](https://youtu.be/qFdH3VR4RSI)

![Character Concept Lab Image](https://guppie1337.github.io/ceastridge-snhu-cs499/character_concept_lab_display.JPG)


**_Reflection:_**

When I first started, I thought I knew more XML than I actually did. It started out with me using the several namespaces until I decided to look up some algorithms that were used for parsing XMLs in different ways. I originally thought I had to use the XmlDocument class to complete the task but I was delighted to find there was XDocument through LINQ that made everything so much easier. Once of the errors I was getting was due to not pulling nested elements correctly. Although I knew I wanted this to be a lot cleaner without having to call on specifics, I ended up having to at least reference the element name. I was hoping for a bit more dynamic of an approach to the implementation where there was no explicit call to the element tags, but rather have them used as keys and simply pull the values. For now, I have a simple xml document that has everything nested under a document element. At the moment, the elements are organized by their content. However, this isn’t necessary for a proper parse.

### Campsite Locator (Databases)

Campsite Locator is the only addition to this portfolio that was directly coursework. The concept was to hold a database of campsites and allow individuals to search for them. The initial implementation would override any Google Maps/Location API search results and populate the campsite on the map and parse the associated information. The campsites would each populate a flyout drawer to give the user information about the campsite. All the information for each campsite I wanted the user to know was associated in the Campsite class (Data Access Object). Instead of keeping this approach, I've decided to go with an approach that focused on _User Experience_ that takes advantage of both the Google Maps/Location API and my hard-implemented database for campsites. 

Here is a link to this project's final review: [Campsite Locator Final Code Review (YouTube)](https://youtu.be/ft_RUghT6Zs)

![Campsite Locator Image](https://guppie1337.github.io/ceastridge-snhu-cs499/campsite_locator_display.png)


**_Reflection:_**

My first task in the process was to immediately put the proper location handling responsibility back in the hands of the Google Maps/Location API. Maybe I misunderstood direction or maybe I just had a horrible design in mind and didn’t realize it at the time. When I went through my logic and reviewed how I was overriding the location searching just to populate a hardcoded campsite from the database, I knew I was doing something wrong. I had to find a way to implement the database while still allowing the user experience to flourish.

I changed the process by which a user can search for a campsite by letting them toggle campsites nearby or go to the nearest campsite to their searched location. By doing so, I let users determine campsite by going to known locations first, then branching from proximity. I was also hoping the experience would let people think things like, “wait… there are campsite near Atlanta?!”. 

Overall, the process of transitioning was simple. I wrote a few algorithms to check distances and compared them to the location when a search was processed. The user can then go to/populate campsite markers by pressing a float action button on the lower part of the screen. I felt it was a very simple. Everything looked good until I decided to run it on my Pixel XL!

The first launch yielded a crash due to a FusedLocationProvider call that was referencing a null location. The problem with the call is that it requires the user’s last location to be pulled from somewhere. To me, the issue was like being denied your first credit card because you don’t have established credit. Sure, there are other ways, but really? I refactored that method’s logic to a hardcoded, predefined location; Southern New Hampshire University. Now users can enjoy the app and utilize both the Google Maps/Location API database concurrently.

## Professional Self-Assessment

Throughout my coursework, I’ve been presented with many opportunities to work on different projects and different languages. Some projects required multiple languages and even technologies to complete. Not only do I feel I’m a well-rounded programmer by the experienced immersion, but I embrace the change of technology and choose to grow with it. When there is a desire to accomplish a task, I don’t always go for the first tool I know how to use; I make a determination of what to use and how to implement it. 

When first learning about version control software, I decided to work on a project with a friend and force the opportunity to learn more about it. We ultimately failed that project but learned many valuable things from it. I can now successfully utilize version control with local and remote repositories to the advantage of the overall development process.

Furthermore, every project started was conceptualized, documented, designed, implemented, and tested for verification and validation purposes. One thing I knew going in was that I didn’t know everything. No problem! That’s why _Agile Development_ is for! Working on a small team made it a bit difficult to be so formally “informal” about the process and distribute agile roles. Therefore, I took it upon myself to distribute responsibilities between myself and two other people. We rotated responsibilities by time and project and I successfully demonstrated competency in each role from: Stake Holder, Product Owner, Scrum Master, Developer, and Tester. I even had the opportunity to implement a Kanban process which worked very well. I still use these processes personally and professionally to this day.

As a developer and tester, I took it upon myself to maintain the integrity of the projects by playing devil’s advocate. I scrutinized everything from the process to the implementation details. Doing so allowed me to emulate a real world development environment in which security of information is a must. Whether it be for data leaks of Personally Identifiable Information like SSN, medical information, or even proprietary artifacts, I ensured our processes were as clean as we could make them for _”amateurs”._

Lastly, I believe the projects shared in this portfolio demonstrate a range of knowledge that is valuable to a prospective company. The ability to recognize, navigate, and program logic from what would be considered different roles on a project show my flexibility for any job. What I hope to showcase most of all with my projects is my creativity and eagerness to be a better programmer and designer. From personal projects to critical self-awareness, I believe I have what it takes to add great value to any project I’m fortunate to be a part of.

