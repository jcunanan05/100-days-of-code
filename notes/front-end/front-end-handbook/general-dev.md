## General Front-End Development

### So, You want to be a front-end engineer

res: [https://www.youtube.com/watch?v=Lsg84NtJbmI]()

#### "Dev"Olution

- Designer
- Hacker - poking things and coming up with solutions
- Developer - crafts solultions and knows best practices
- Engineer - knows the concepts behind the best practices and crafts solutions

#### Lesson plan

1. Understanding browsers
2. Engineer's Toolbox
3. Some best practices

#### Understanding Browsers

- Main Flow: Parse HTML -> DOM Tree -> Render Tree -> Layout and Paint

- Parsing in General: needs "context-free" grammar

  1. Input
  2. Lexical Analysis - input is broken into tokens
  3. Syntax Analysis - rules are applied to the token to get the output
  4. Output

- Backus-naur form - simple parsing analysis form

- Parsing HTML

  1. Document
  2. Tokenizer
  3. Tree construction
  4. DOM Tree - In-memory representation of the document

- Parsing loop attaches script execution in the middle thats why it's always good to **_put scripts at the bottom_**

  1. Speed up the parsing process
  2. Help browsers to limit the amount of variability while parsing

- DOM - interface to help us interact with the DOM Tree

- Parsing CSS - Single pass using the flex / bison parser

  - simpler parsing than HTML

- Parsing JS - more complicated

### Being a web developer

res: [http://www.yellowshoe.com.au/standards/]()
res: [https://developer.yahoo.com/performance/rules.html]()

- Compilation of best practices and explanations

### Planning a front-end JS App

res: [https://www.youtube.com/watch?v=q4zEGkjTBFA]()
slides: [http://codylindley.com/spotlight-front-end/]()

#### 16 steps

1. Verify you have working and stable api

- prototype to help the backend engineers

2. Select software management tools - like version control, bug ticketing, document storage, task management

- examples: github, stackoverflow, slack, conceptboard, trello

3. Create a foundational specification

- which devices? min resolution?
- which languages?
- offline?
- Accessibility Standards?
- SEO Strategy?

4. Select a software development process

- pick one that works for the team

5. Select host platform and Hosting service
6. Select package managers
7. Select site and user analytics
8. Select code and style enforcement
9. Select a task runner
10. Select app architecture / structure
11. Select testing methodologies and tools
12. select code quality / complexity tools
13. Define deployment strategy
14. Select package monitoring solution
15. Select JS error monitoring solution
16. Select uptime and performance monitoring solution
