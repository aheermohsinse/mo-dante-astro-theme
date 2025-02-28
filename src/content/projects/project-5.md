---
title: 'Page Object Model (POM) | Design Pattern'
description: Page Object Model is a design pattern which has become popular in test automation for enhancing test maintenance and reducing code duplication. A page object is an object-oriented class that serves as an interface to a page of your AUT.
publishDate: 'May 24 2018'
isFeatured: true
seo:
  image:
    src: '/project-5n2.jpeg'
---

![Project preview](/project-5n2.jpeg)

<!-- **Note:** This case study is entirely fictional and created for the purpose of showcasing [Dante Astro.js theme functionality](https://justgoodui.com/astro-themes/dante/). -->

**What is POM?**
Page Object Model is a design pattern which has become popular in test automation for enhancing test maintenance and reducing code duplication. A page object is an object-oriented class that serves as an interface to a page of your AUT.

The tests then use the methods of this page object class whenever they need to interact with the UI of that page, the benefit is that if the UI changes for the page, the tests themselves don’t need to be changed, only the code within the page object needs to change.

Subsequently all changes to support that new UI are located in one place.

## Why we need POM?

Increasing automation test coverage can result in unmaintainable project structure, if locators are not managed in right way. This can happen due to duplication of code or mainly due to duplicated usage of locators.

For Example, in home page of web application we have menu bar which leads to different modules with different features.

Many automation test cases would be clicking through these menu buttons to execute specific tests. Imagine that the UI is changed/revamped and menu buttons are relocated to different position in home page, this will result automation tests to fail. Automated test cases will fail as scripts will not be able to find particular element-locators to perform action.

Now, QA Engineer need to walk through whole code to update locators where necessary. Updating element-locators in duplicated code will consume a lot of time to only adjust locators, while this time can be consumed to increase test coverage. We can save this time by using Page Object Model in our test automation framework.


## Advantages of Page Object Model:

1. According to Page Object Model, we should keep our tests and element locators separately, this will keep code clean and easy to understand and maintain.
2. The Page Object approach makes test automation framework programmer friendly, more durable and comprehensive.
3. Another important advantage is our Page Object Repository is Independent of Automation Tests. Keeping separate repository for page objects helps us to use this repository for different purposes with different frameworks like, we are able to integrate this repository with other tools like JUnit/NUnit/PhpUnit as well as with TestNG/Cucumber/etc.
4. Test cases become short and optimized as we are able to reuse page object methods in the POM classes.
5. Any change in UI can easily be implemented, updated and maintained into the Page Objects and Classes.

## How to implement POM:

POM is best applicable for the applications which contain multiple pages. Each of which have fields which can be uniquely referenced with respect to the page.

1. Create new directory/folder/package in your project depending upon which IDE you are using and name it as PageObjects, you can do this by right click on the project root level and select New > Directory, in my case, I am using PhpStorm with Codeception as an automation framework so it contains Page Object Model inside _support folder as shown in screenshot but it doesn’t matter.
You can create it at root level of project and call it accordingly in your project, you can even add sub folders inside PageObjects to keep more categorized and clean.

2. Now right click on folder and add new Class file in it and name it to actual page from test object i.e. PageObjects -> Login -> LoginHome.php

3. Now you can write method for each element in LoginHome page, each method contains a return value element and your page object class will look like this:

3. Now create test case for Login by right click on Tests folder in your project directory: add new class and name it LoginCest.php

Note: you can create TestCase class in your Tests folder and name it according to your test, it doesn’t matter which IDE you are using. Only important is that you call the page object class in your tests class so when script are executed, it get respective element locators.

Now, you can write your test cases in test class and run it. Test class will look like this:

And using Page Object Model our final project structure looks like this:

## Summary

Using Page Object Model, all element locators are being managed in separate directory and can be updated easily without any change in test cases.

I have created sample project with Page Object Model implementation, find it here.

In next blog I will explain how we can create a separate repository of Page Objects and can use in multiple projects on need base.

And that wraps it up for this article, if you would like to learn more about POM, you can follow these links.

<!-- **Note:** This case study is entirely fictional and created for the purpose of showcasing [Dante Astro.js theme functionality](https://justgoodui.com/astro-themes/dante/). -->
