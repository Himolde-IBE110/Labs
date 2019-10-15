# Lab Web technologies and the Cloud
Lab exercises. Introduction to Information Technology. Web technologies. 
Based on https://www.w3schools.com/whatis/whatis_html.asp, Edx course HTML5 and CSS Fundamentals*, Khan Academy https://www.khanacademy.org/computing/hour-of-code/hour-of-html/pt/css-basics and https://aws.amazon.com/getting-started/tutorials/
If you find this topic intersting, you can take the courses at https://aws.amazon.com/training/ 

The school library provides several books as online resources. You can access them through the library databases link: https://www.himolde.no/bibliotek/english/databases/ in the Database Ebook Central ProQuest - E-books in full text. 

In the next assignment, you will create a Web page and publish it in the Cloud. The objective in this lab is that you learn by doing.

As you already know, the Web is an information system where resources are identified by URLs and can be accessed via the HTTP protocol. It is based on 3 technologies: 
- the Hypertext Transfer Protocol (HTTP): the underlying protocol used by the World Wide Web that defines how messages are formatted and transmitted, and what actions Web servers and clients (browsers) should take in response to a message received. 
- The Hypertext Markup Language (HTML). It is the markup language we use to write documents that can be displayed in a Web browser.  The current HTML version is HTML5. Modern Web pages and Web applications are generally composed of at least three components, so what people often mean when they say 'HTML5' is the trio of languages: HTML5, CSS3 and JavaScript.
  - The 'HTML' part contains all the content, organized into a logical structure.  This is the part that an author might be most concerned with: the words, chapter headings, figures, diagrams, etc. HTML5 was developed to provide more powerful and flexible ways for developers to create dynamic Web pages.
  - The 'CSS' part (version 3 being current) is all about the presentation or style of the page; what it looks like without too much regard for the specific content. You may think of it as the way you might specify a "theme" in a word processing document, setting fonts, sizes, indentations and whatever else may apply to what it looks like. 
  - The 'JavaScript', or 'JS' for short, part is about the actions a page can take such as interaction with the user, and customizing and changing the page according to any number of parameters.  This is what allows a Web page to be more than just a document, but potentially a Web application. 
- A Uniform Resource Locator (URL) allows to refer to a Web resource (web pages, images, etc), specifying its location on a computer network and a mechanism for retrieving it.

## Improving my first Web page.
You have already created your first Web page in the Wireshark lab. In this lab you are going to improve it a little. Remember that you can build and edit your HTML pages by either using online editors or editors that you can install on your machine like Visual Studio Code. In the demonstration we will use the JSBin online editor (https://jsbin.com/?html,output) 

1. Open up a new tab and go to jsbin.com. Remember there is no need to login or register. 
2. Open this page in your browser: https://himolde-ibe110.github.io/Labs/hello.html). Right click on that page and select **View page source**. This is the HTML code of your page. Copy it and paste it into the left panel of jsbin. 
Now that you have an initial code, lets start.

3. Modify the page using the style in this code:
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>JS Bin</title>
  <style>
    q {
      font-size: 12px;
      line-height: 15px;
      color: gray;
    }
    </style>
</head>
<body>
    <p>She looked over the top of her book and whispered <q>I'm hungry.</q> My heart stopped.</p>
    </body>
</html>
```
4. Change the look of the text inside the q tag. 
5. Change the look of a paragraph. Remember that the tag is p.

6. Uncomment the next lines and place them in the page:
```html
 <!--  <script type="text/javascript">
    document.write("<p>The date is " + Date() + "</p>");
</script>
   
 <script type="text/javascript">
    d = new Date()
    h = d.getHours()
    if (h < 12) {
      document.write("Good morning!");
    }
    else if (h > 12 && h < 20) {
      document.write("Good afternoon!");
    }
    else
    {
      document.write("Good night!");
    }
  </script>-->
```
7. Change the message so the page shows hours and minutes and am or pm according to the hour.
Hint: Use let date = new Date(); let minutes = date.getMinutes(); and let hours = date.getHours();

## Publishing your Web page in the Cloud
Prerequisites

In order to deploy a site you need a couple of things:

    1. The Heroku CLI requires Git, the popular version control system. If you don’t already have Git installed, complete the following before proceeding: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git You may want to attend the course https://classroom.udacity.com/courses/ud123 about Version control with Git.
    2. First time using Git? https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup
    3. Heroku Account – sign up here: https://signup.heroku.com/
    4. Download the Heroku Toolbelt – a command line application for managing your Heroku account http://devcenter.heroku.com/articles/heroku-cli

## Deploying Your Site

1. First, you need to navigate to your project in the command prompt. Ex.:

cd Projects/my-site

If you’re happy with the state of your application – create an index.php file. Heroku has no support for deploying static web sites (only HTML-CSS) but we can trick Heroku to deploy a static site by including 1 dynamic file, a php file. PHP stands for "Hypertext Preprocessor", and is a scripting language that dynamic web pages: the PHP code is executed on the server, and the result is returned to the browser as plain HTML. You can click here https://www.w3schools.com/php/ to see some examples. 

2. The index.php file will be served by Heroku before your index.html. We need to make the browser redirect from index.php to index.html. We only need to include one line of PHP code.

```php
<?php include_once("index.html");?>
```
You can do that in Linux with:
```bash
echo '<?php include_once("index.html");?>' > index.php
```
Tip: Make sure there’s no spaces before the <?php or else it won’t work!

3. Create a file composer.json with {} as content.  This file describes the dependencies of your project and may contain other metadata as well, we just want Heroku to be happy so we say we have no dependencies.
```bash
echo '{}' > composer.json
```
4. Run heroku --version to verify that heroku is installed
5. Run heroku login in your terminal or command prompt and fill in your Heroku credentials
6. In your project folder, execute 
```bash
git init 
```
to initialize your git repository

7. and
```bash
git add . 
```
to add the working directory files to the staging area. It tells Git that you want to include updates to a particular file in the next commit.

8. heroku app:create the-name-of-your-site-if-not-taken

9. The changes are saved to the local repository
```git
commit -m "First commit" 
``` 
10. To public your site you need to execute:
```
git push heroku master 
```
As the result you should have in your screen the message: "https://here-comes-your-site" deployed to Keroku. 

My test web site is published on the url https://my-static-test01.herokuapp.com/

If you need help, please send to the Discussion a print of your screen showing the error. 







