# 100DaysOfCode Log - Round 4 - [Jonathan Albert Cunanan]

### R4D1 15/11

- Setup express server and nunjucks templating
- Read about top NodeJs Hosting providers.
- Understood nothing about whats the price on deploying a webserver without database per month.

### R4D2 16/11

- Started coding the banner. Tried two experiment to create a desktop and mobile layout. 1st approach is to build 2 elements and hide them according to breakpoints. 2nd one is 1 element and think about how to structure them in mobile & desktop. 1st one didn't worked for me, went for 2nd haha.

### R4D3 17/11

- Fix some layout spacing and Added a warning state button for the landing page.

### R4D4 18/11

- Code my client work. Put some themed call-to-action buttons. Overriding classes in boostrap is hard. Well I guess that's their way of preventing confusion/bugs on their side. I like ease of overriding at bulma, which can also cause confusion on my end, and then blaming bulma haha

### R4D5 19/11

- Code endlessly until the next day. Didn't make it to my client's skype meeting. Used **markedjs** to easily put content on each sections. Passed in different renderer options too. Stayed up till 8am lol.

- First time to dive on AWS Lightsail. They say it's easy to deploy apps there, but got a little bit confused. Luckily there's video tutorials on how to connect a GoDaddy Domain name to Amazon lightsail IP. Added notes on deployment.

### R4D6 20/11

- Code my client's revisions on section names. Already deployed my app on the internet. Stayed up to 3 am now. Thinking of ways how to simplify deployment.

### R4D7 21/11

- Attend the Facebook dev circles meetup

### R4D8 23/11

- Rewrote my react portfolio from scratch

### R4D9 24/11

- Watched Kent Advanced react patterns tutorial. Learned about the updater function.

### R4D10 26/11

- Client wants some additional sections. Pushed ui fixes and added the section. Separated the html by partials, using nunjucks templating engine

- Code my portfolio. Added tests to my navbar. Used react-testing-library. Great utils.

### R4D11 27/11

- Watched advanced react patterns. Learned about compound components

- Push some content fix in my client work

### R4D12 28/11

- Code my portfolio, added footer.

- Installed Aws Elasticbeanstalk CLI. A little bit challenging to setup environment variables.

### R4D13 29/11

- Setup a XAMPP environment, and also installed wordpress. A little bit confusing and challenging to set it up. But it works. I put some key notes on doing it.

- Watch tutorial of AWS. Good intro of IAM roles.

- Code my portfolio.

### R4D14 3/12

- Watched AWS Deployment videos in frontend masters

### R4D15 4/12

- Checked out wordpress API

### R4D16 5/12

- Stayed up late to practice deployment with AWS Beanstalk, my nextjs app has still errors

### R4D17 6/12

- Meeting with client
- Found out some clues on why my nextjs app is not working, some permission errors with node-sass

### R4D18 7/12

- Code my portfolio again. Building a card component

### R4D19 8/12

- Code my client work today. There are some revisions.

### R4D20 17/12

- Code my portfolio! It's done now at https://jcunanan05.github.io/
- Found a good tool called Jotform, That takes up filling out forms and has a pdf generator. Thumbs up for their tool.

### R421 19/12

- Client meetings

### R4D22 24/12

- Watched GraphQL fem intro videos

### R4D23 25/12

- GatsbyJS Tutorials. Greeted programmers Merry Christmas

### R4D24 26/12

- Had meeting with a friend on how would he make a blog. He wants wordpress, but I'm efficient with js. Settled with gatbsy and wordpress

### R4D25 30/12

- Checkout some tutorials, Found good ones at Frontend Masters
- Watched Webpack 4 Fundamentals on fem

### R4D26 31/12

- Last day of the year! Watched webpack 4 fundamentals. Got confidence in understanding webpack runtime code.

### R4D27 04/01

- I felt like I need to migrate my server rendered html into a full blown static site. I switched from node.js + nunjucks to Gatbsy.js I feel more comfortable with components.

### R4D28 05/01

- Started rewriting from bootstrap 4 to bulma. I love writing code in Bulma CSS framework.
- Tried parsing `.md` files with gatsby-plugin-remark-transformer. I realized, I can just do it with marked.js library, liked I used to. Spent some time rewriting code again.

### R4D29 07/01

- Found out that git by default on my mac is case insensitive. When I renamed my exisitng files in TitleCase, nothing was commited. Lol I removed and returned my src folder.

### R4D30 08/01

- Found it difficult to put scripts in react. It doesn't execute when I just put it. I did some `document.createElement('script')` and put `async` and `defer` on the element, and injected it on the bottom of the page. Added the script on the component.

### R4D31 09/01

- I encountered a CORS issue when I am using mailgun. Stuck until evening. Even though i put headers, still nothing works.

### R4D32 10/01

- Solved CORS! I need a back-end to communicate with mailgun. I created 'again' a node server but still I have cors even with a cors plugin! Turns out, I need to enable CORS at a _preflight request_ called OPTIONS, on a rest route. I can now send emails!

### R4D33 11/01

- Learned about react concepts. `componentDidUpdate()` will error out, when you didn't compare it to the upcoming props. It is well written in the docs.

### R4D34 12/01

- Used `multer`, an express middleware to handle `Content-Type: multipart/form-data`. Learned about multipart/form-data, that it has a `boundary`. Boundary is automatically provided by a javascript api called `FormData` I used it with axios to post data to the server.

- Amazed that multer is well-writen.

- Learned about buffer type. It is like the data. And learned about the mailgun api while reading its docs.

- Bought Ruby on rails book! :)

### R4D35 13/01

- Finished my mailgun logic.

### R4D36 14/01

- Got problem in deploying, haven't really fixed my CORS problems. Tried the basic working code in npm's cors() package. Works, but only for one website.

### R4D37 15/01

- Finally got the site to deployment. Setup CI with travisCI, S3 / Cloudfront, in my portfolio's repo, and my work's repo.

### R4D38 16/01

- Got some work feedback, fix some typo, add some sections. Encountered an issue because I disabled our domain with www subdomain. The indexed search result on google now is disabled.

- Work client wants success mail features after they successfully have the email.

- Updated my backend code with cors that supports multiple websites.

- Also discovered about adding mailgun to my DNS, idk why still my MX (mail exchange) dns is still not working

### R4D39 17/01

- Made some deployment logic, where I put up an heroku and netlify deployment on the `dev` branch. Added a `DEPLOYMENT_ENV` variable on heroku, that will add my netlify site to the whitelisted CORS websites.

- Refactored my back-end code. So satisfying to erase long codes. haha

### R4D40 18/01

- Finally added the success mail feature. Got some permissions problems in aws ElasticBeanstalk for putting travisCI also in our backend repo. My mistake is, I am creating the policy from scratch, tying elastic beanstalk services altogether. After few hours, I finally discovered there's already a permission defaults by aws, Which is called ElasticBeanstalkWorker.

### R4D41 19/01

- Watching webpack 4 fundamentals on frontendmasters, it's awesome learning about webpack-dev-server, webpack-merge, packages. Hot reloading is awesome.

### R4D42 20/01

- Just reading about MDN Docs, MDN docs is awesome. Read about high level concepts/pros/cons of Django and Express

### R4D43 21/01

- Played around with rails tutorial, adding minimal code to the generated code.

### R4D44 22/01

- Amazingly, I had another project! I used gatsby again to initialize my project. Finally made the test suite working! The docs were incomplete. I found the working code at [GatsbyJS's repo](https://github.com/gatsbyjs/gatsby/tree/master/examples/using-jest).

### R4D45 23/01

- I setup the deployment environment of my new project using travisCI and AWS S3, CloudFront. Also managed my DNS using AWS Route53, transferred it from GoDaddy. I found a good guide in this [stackoverflow link](https://stackoverflow.com/questions/11602232/how-to-link-godaddy-domain-with-aws-elastic-beanstalk-environment). It's just easier to manage, and get certificates from Route53.

### R4D46 24/01

- Slowly migrated my bulma components to the repo. Making a more reusable, general vanilla components because i believe i'll use more theming here.

### R4D47 25/01

- Started adding content code to my project. I used marked.js to parse my files.

### R4D48 28/01

- Deadline is almost there. I added a mailchimp api code with an exisiting server. So I made my cors more dynamic, but i had errors. Turns out, I just need to handle empty arguments.

### R4D49 30/01

- Made the banner component. I really don't know how to style the header. It's wierd because the image is square. I settled to a 2 column layout.

### R4D50 31/01

- Started a blog project with wordpress. It's for my friend.
- Setting up testing again with Gatsby made me do a boilerplate.
- Pushed some fixes on my works codebase

### R4D51 02/02

- Finished Webpack fundamentals! Learned about presets, environments, and most common packages to install. Planning to make my own boilerplate.

### R4D52 04/02

- Learned [how to remove node.js on mac](https://stackoverflow.com/questions/9044788/how-do-i-uninstall-nodejs-installed-from-pkg-mac-os-x), and [how to install Node Version Manager (NVM)](https://github.com/creationix/nvm).
