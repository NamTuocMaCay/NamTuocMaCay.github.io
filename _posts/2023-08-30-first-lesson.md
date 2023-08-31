---
layout: post
title: First Lesson
categories: [content, demo]
---
The first lesson that I learned from the course is how to create a blog using Jekyll template on Github.

This is a very interesting lesson, since it helps us establish a certain vision for our study in this course.

It is no exaggeration to say that this lesson is the foundation for the course, due to the fact that we will use it the most, since we have a task of creating five posts at the end of the semester.

# What is GitHub

Github is 

> a website and cloud-based service that helps developers store and manage their code, as well as track and control changes to their code.

# How to create a blog using Jekyll template

At first you must have a github account. This one is very easy. Once we have the account, we will go to the template and start using the template. This one is also very fast and easy.

# Difficulties

When we need to learn to change the content of the template to our liking, I stumbled upon trouble. 

Mine did not appear normally, as it did not show anything on screen.

After asking the lecturer, I realized that I have made a mistake. 

According to the guildline:

![Alt text](/assets/image/posts/Screenshot 2023-08-31 210410.png)

My repository has to have the same name as my github user name. But unfortunately, I did not. Therefore, it cannot recognize my blog and that is why my blog is error. 

After fixing the above problem, I can finally use my blog. 

But once more, I encountered another problem when trying to post something on the blog.

I uploaded my post but nothing appeared on the blog. I did go to the `_posts` folder to add my post, but nothing happened. 

Then I realized that when it asks me to change the file name, I should have renamed it with the same format `.md` at the end. 

![Alt text](/assets/image/posts/Screenshot 2023-08-31 211312.png)

I fixed the name and voila the post appeared on my blog.



<!--more--

Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## Another great heading (h2)

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit.

### Some great subheading (h3)

Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum.

Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc.

### Some great subheading (h3)

Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

> https://moodle.rub.de/course/view.php?id=123#section4sftp

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt.

### Some great subheading (h3)

Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum.

In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.

#### You might want a sub-subheading (h4)

In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.

In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.

#### But it's probably overkill (h4)

In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.

##### Could be a smaller sub-heading, `pacman` (h5)

In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.

###### Small yet significant sub-heading  (h6)

In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.

### Highlight the code please!!

{% highlight c %}
float Q_rsqrt( float number )
{
	long i;
	float x2, y;
	const float threehalfs = 1.5F;

	x2 = number * 0.5F;
	y  = number;
	i  = * ( long * ) &y;                       // evil floating point bit level hacking
	i  = 0x5f3759df - ( i >> 1 );               // what the fuck? 
	y  = * ( float * ) &i;
	y  = y * ( threehalfs - ( x2 * y * y ) );   // 1st iteration
//	y  = y * ( threehalfs - ( x2 * y * y ) );   // 2nd iteration, this can be removed

	return y;
}
{% endhighlight %}

### Oh hai, an unordered list!!

In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.

- First item, yo
- Second item, dawg
- Third item, what what?!
- Fourth item, fo sheezy my neezy

### Oh hai, an ordered list!!

In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.

1. First item, yo
2. Second item, dawg
3. Third item, what what?!
4. Fourth item, fo sheezy my neezy

## Headings are cool! (h2)

Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc.

### Tables

Title 1               | Title 2               | Title 3               | Title 4
--------------------- | --------------------- | --------------------- | ---------------------
lorem                 | lorem ipsum           | lorem ipsum dolor     | lorem ipsum dolor sit
lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit
lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit
lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit

Title 1 | Title 2 | Title 3 | Title 4
--- | --- | --- | ---
lorem | lorem ipsum | lorem ipsum dolor | lorem ipsum dolor sit
lorem ipsum dolor sit amet | lorem ipsum dolor sit amet consectetur | lorem ipsum dolor sit amet | lorem ipsum dolor sit
lorem ipsum dolor | lorem ipsum | lorem | lorem ipsum
lorem ipsum dolor | lorem ipsum dolor sit | lorem ipsum dolor sit amet | lorem ipsum dolor sit amet consectetur
