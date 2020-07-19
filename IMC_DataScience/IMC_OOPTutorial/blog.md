*adapted from the google doc I wrote this on. The formatting might be slightly off.*

# Coding for (Not Quite) Dummies: Object Oriented Programming

### Part 1: Introduction - Coding is Scary

In 1969, Martin M. Broadwell made one of the first references to a psychological learning model known as the four stages of competence. They comprise of: 

1. unconscious incompetence, 

2. conscious incompetence, 

3. conscious competence, and 

4. unconscious competence. 

   

   When it comes to programming, there are many, many different websites and articles aiming to quickly teach a person the basics, and try and convince them to take the plunge and commit to reaching those third and fourth stages.
   If you’re here, you’ve fallen victim like the rest of us.

   To progress in any significant manner beyond the second stage of competence requires a devotion to the task. Lesson writers know this, and as such don’t bother too much with trivial things like making higher level tutorials approachable - *why bother? At this point surely any prospective student knows what they’re getting into.* 

   That attitude is a convenient workload off the writer of the lesson, but not very helpful for newer students wanting to dip their toes into bigger concepts, who instead find themselves thinking they’re better off abandoning the endeavor altogether.

![img](https://lh5.googleusercontent.com/a9Lc0cdKhPta9O-ffFh6a4Bmi4Daam8k4c91pkZ4xQofIjOrCpY0FOGSS59UXTZZ-BNm32dgP8eNMldHRWVh0itfYC3aPLWTQG_y4KRQZPm3EZCty_KVFuBM4DdQqwMysv2VhjyJ)*An excerpt from Oracle’s official Java tutorials - This doesn’t scream “inviting,” now does it?*





This guide hopes to be different. I’m assuming, if you’re reading this, you’re on your journey from incompetence to competence, and to this end have the fundamentals already down - variables, loops, basic syntax, and other things like that. These lessons will discuss higher level concepts and techniques, and hopefully convince you that the past few hours you spent on Codecademy or whatever your teaching method of choice was wasn’t a waste of time. Even making it to stage 3 in this context - competence with coding - is no simple task, and one that we all are taking steps to achieve, but with any luck these articles can help guide you down that path.

### Part 2: What is an Object?

Object Oriented Programming. Even the name sounds complicated. Luckily, it’s not that bad. Let me explain.

**Object Oriented Programming** is a name that we give to certain coding languages because they make use of a type of code we call “objects.” Funny how that works, huh? Many major languages are Object Oriented, including (but not limited to) Python, C++, C#, Java, JavaScript, and many more.

​				*Quick note: For examples and sample code, I’ll be writing in Java because it’s my**primary language. Object Oriented techniques and features hold 				across all these languages by definition, but specific implementations may differ if you aren’t using Java.* 

An object is obviously not a physical object, but a special variable type. It can do more than just store a number, though. Objects are variable types that we make ourselves, and both store data and utilize functions specific to the object. What do I mean by this? Well, here’s an example. Say we want to store the data of a bunch of people, for a classroom roster or something (the context isn’t that important, is it?). We want to store their first name, last name, and age. We want to be able to access any of these pieces of data at any time. Also, we want to be able to change their age after the fact, seeing as how people age.

​			*Remember: This is Java! Your mileage may vary if you’re using something else, but the general idea should be the same.*

To start, let’s make a public class called “Person” (since that’s the type of object we’re trying to make - people). We’ll also make some variables to store names and age, though we won’t assign any values to them, seeing as how this isn’t any one specific person we’re making right now (we’re making a general template that we’ll be able to use to create specific “person” objects with later).

![img](https://lh6.googleusercontent.com/zehLJy0dg7jY0SIAesHgX1_GRqjn_et0uq-QoJPPNZWSta4vbNkB1AlJnqcahxzgZHD-pG96n0ZiGzIKNM0W2T6cbDEwZ256ye3eybvMx-EX5dhS1-eXaI5Yuc48F4uLhsRLb-zf)

To clarify, we’re making this object in its own file. To actually create a “person” object, we’ll just leave the “Person.java” file in the same directory as whatever program is actually using the object, then create an object in that file. How do we actually create the object, though? Well, that uses something we call a **constructor**. A constructor is a bit of code in the object class (the Person.java file) that lets you know how exactly you’re going to create a Person object in your code. Here’s a sample one I wrote:

![img](https://lh6.googleusercontent.com/-2fB1lh2VpfFGMAo1ZkOUvsuq_2WVJI5olcYobpgnLRUZOcYg1KmihudAuU7cnUsgmudentdtre8LAL4KL5tdC2kJW5a-sq_Bd15Kio6J8dDgcpvfzTBwYe0bl-ZqUMab1Wuw3xT)

So, what’s going on here?
Whenever we make an object, we’re making a copy of this Person object with its own firstName, lastName, and age values. These lines of code mean that, when we want to make a Person in our code, we need to give it a first name, a last name, and an age - like this!



![img](https://lh3.googleusercontent.com/PI2YJqN66b9MmyfB4FK_BWVjicH50ctnGYhrqyaU5ripJs896i9XJDYz1ScvW-s7gH52A_PFcI66GBaxY-zlWCNim7mgyIbMmWuQFRs2QWtNTs__3YlMOcI8Akrt8yvpHN4IL0tn)



Here’s an object in action. We’re making a Person object named “John” with a first name input of “John” (shocker), a last name input of “Smith”, and an age input of 26. Note that this is in a completely separate file. We’re just storing Person.java and PersonTest.java in the same directory. 
With that, we’re 1 for 3 in the things we want this Person object to do. It can store that info, sure, but there’s no magic trick with Objects for accessing the variables within them*. We’ll have to write that in ourselves, via a method. 

​			*there actually is indeed a trick for this, but it’s bad form. When we initially created those variables, we made them private. If they were instead public, we 			could then just access, and edit, them from anywhere. This typically isn’t what we’re looking to do though, since granting full access to those variables can 			be messy. If you’re coding Person.java, do you want the people using it to be able to modify firstName or lastName freely? Probably not.*

You most likely already know what a method is, but just in case, a real quick reminder: a **method** is just a fancy name for a function. You (optionally) input a value, it does something, and (optionally) outputs a value (the only required part of those three is that it does something). If we want methods to retrieve the variables, we just need to write some public methods in Person.java that will return the desired values:

![img](https://lh6.googleusercontent.com/Lmtty-FotG5btSIPU7eBzFYbY76k3W1Hwd9CLvkR1h-scr5dHKTgId5WVDqjp4QlDSbViF67QRFp0iGGStmKbmA6kqB7OCUr2945a0rwdM-oUQMcO15dykRMGshkN5DSvUcuM72q)

**public** here means that it can be accessed from outside Person.java. It would be a pretty useless retrieval method if we couldn’t actually call it from outside the file.	

​			*Compare to the private age, firstName, and lastName variables - since they’re private,* *we can’t just print John.firstName in PersonTest.java*

The int/String part right before the name just indicates what variable type is being returned. 
You’ll notice I added a getName() method that just returns the whole name, since I figured that could be useful. Here’s me using these methods in PersonTest.java:

![img](https://lh3.googleusercontent.com/bV9IZvflbUtNU4L9x_GM3mNSU4-mPL6ub5VQL3a-TJacdBZtz455z9hTvxapx5Z-kB7r8rYH728dqC_IjiCRoi67qy6-QPdeYWaG5x_g2jyCn88b-erDdX8XLWBp7la2ZwkqMS6h)




Using the method of an object is as simple as [specific object instance].[method name]. Here’s what the above code outputs:

![img](https://lh3.googleusercontent.com/-pn_m1XcMA0xH0wxxLkaechvajPV4lo0135r7WL1nuYdy1JOlXqmjEnoLveH8elh9gFi0HOKx0prMkTjZTcPt5bub14PbseULPN8DvhNivh38t-AATjeVxHnQTsnwge_NFpvMebE)

Our last task for this is to change the age of the person. This one will use a method too, but it raises an important question: How exactly do we want to approach this? Do we want to give free access to increment the age, or do we want to simply increment it by one? An easy answer is to do both! 
Quick Sublesson: Overloading

​			*Note: This does not apply to every language! I know it works for C++ and Java, for example, but not Python. Do a quick google search to see if this will 			work for you. If not, skip this.*

In some languages, two methods can be given the same name, if they take different inputs - as seen in the code example you’ll see in a second. This is called **overloading**.

I’ve gone ahead and made a function that takes an input and adjusts the age accordingly, and another that takes no input and simply increments the age by one. With that, we have our complete (simple) Person.java file!

![img](https://lh4.googleusercontent.com/NsFmGAZKJXQ0hWunbwB2_NVgK5-HcEt_rsFhNqD2tWJar0fbsUOXPpijWXj6dIlrlrX9BWGo87pm3OIsgF7W85zrfiE2J3b-YrugwbP1bQinJkZ3pFJcNiGRebTp0JZ8VUl0796s)

Our complete test program:

![img](https://lh4.googleusercontent.com/WVibNwWKr9c7c7qOi9LiPqwm1ASy0XyU6YmXngBBgu0SGD_xeesUS2cTZqEYFDLq23YzDiNMknjP_woDt5AtWuA3YuMVG83qBbvoxP83iRtWwoFBXW7VgGAP8nDRHan6utIdG7qv)

And finally, its complete output:

![img](https://lh4.googleusercontent.com/GJ86GYuZac2TbqQkIM2QLTAotJUjKLv_qn9ySq-kPS7hl66S8emJinXplmVRtbzgyAqezmuAIdYba5fOCg2_sV2dU5C21xJaOWSKJZaT8Z_CHXe1I5W9amVqysXuH48iI4uJ8-I5)



### Part 3: The End of the Beginning

This is not all there is to Object Oriented Programming. It’s not even all there is to Objects. It is, however, a good introduction to the topic. With any luck, this guide gave you an understanding of objects. We’ll continue on the topic next time. However, it’s not possible to cover everything, so eventually you’ll have to venture into the scary world of advanced computer science. Don’t worry - the people there don’t bite. Usually.

The 4 stages of competence are something of a simplification, in my mind. It’s not an easily drawn line to define where “conscious competence” stops and “unconscious competence” starts. However, the model does do an important thing of drawing a distinction between not knowing something, and not knowing but wanting to learn. Once you’ve reached that threshold, you’ve already taken the biggest step. The only thing to do from there is to not get dissuaded, and stick the landing as you continue your education. Once you’ve gotten to the point where nothing can dissuade you, then I think you can say you’ve finally reached that next stage.

Next time: Inheritance! That is, objects that are subtypes of other classes.