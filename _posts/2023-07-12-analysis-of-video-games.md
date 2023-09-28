# Introduction

I have played many games since I was a tiny girl.

When I started to play my most recent game God of War Ragnarok, I have come to realize that many video games draw inspiration for their world-buiding and aesthetics from religious theme.

Therefore, I start this project to see the connection between video games, their genres, their developers, their publishers, and religious ideas.

# How the project works

I have used what I learned in the session "Network Analysis" to construct a graph showing different connections between five elements (game titles, genres, devs, publishers, religious ideas).

Tools I use: Excel, OpenRefine, Palladio.

### I. Create a spreadsheet

At this first step, I create a spreadsheet using Excel.

I put on five different categories which are game titles, genres, developers, publishers, and religious ideas).

<details>
<summary><b>How did I get the list?</b></summary>
<blockquote>
This step, unfortunately, I have to do it manually. The web scraping method can only provide me game titles, their developers, their genres, and their publishers, since these are actual tags on steam platform, meanwhile there has never been a tag for religious inspiration (understandable!). Therefore, I tried to use my own experience, gathering all the games that I haved played and see whether they have religious inspiration or not.
</blockquote>
</details><br>

![Alt text]({{ site.baseurl }}/assets/image/posts/ana_of_vid_1.png)

Now I have 32 game titles. 

<mark>Updated:</mark>
>I have added more game titles into the list, now I have 37 game titles on my spreadsheet.

Then I saved the file as csv. format

### II. Use OpenRefine

I loaded the file into OpenRefine.


![Alt text]({{ site.baseurl }}/assets/image/posts/the_list_in_openrefine.png)

As you can see except the game titles column, the other columns have data which are not unique/has multiple options. Therefore, I need to be sure that no multiple entries are in one cell. In order to do this task, I go to `Edit Cells` and split them up by the separator `,` with `Split multi-valued cells`.

When the new rows with empty entries are added, I go to `Edit Cells` once again and go to the option `Fill Down` to fill down the text downwards (so that there will be no empty cells anymore).

Nevertheless, I need these data to be connected to each other, in order for later work in `Palladio`. Therefore, after the above task, I created column <mark>connections</mark>, <mark>target</mark>, and <mark>source</mark> for each original column (game-publisher-genre-developer-religious inspiration).  

But by this point, I stumbled upon a big problem. In the original lesson, with the lecturer's guide and example, his data has different structure than mine. All of his data can be splitted and paired, but my data is not always splittable and pairable, some of them is unique. Therefore, if I use the original code snippet that the lecturer provided, it will not work (and indeed it did not work). Hence, I have to change some elements in his original codes.

This is his original code snippet:
```
import itertools
eds = value.split('; ')
pairs = itertools.combinations(eds, 2)
pairs = list(pairs)
pairs = ["&".join(pair) for pair in pairs]
pairs = "|".join(pairs)
return pairs
```
And this is the new one:
```
import itertools
eds = value.split(", ")
if len(eds) > 1:
  conns = itertools.combinations(eds, 2)
  conns = list(conns)
  conns = ["&".join(conn) for conn in conns]
  conns = "|".join(conns)
  return conns
else:
  return eds[0]
```
This is the code snippet for the new source columns:
```
import itertools
pairs= value.split("&")
if len(pairs) == 2:
  source = pairs[0]
  target = pairs[1]
  return source
else:
  element = pairs[0]
  return element 
```
And this is the new code snippet for the new target columns:
```
import itertools
pairs= value.split("&")
if len(pairs) == 2:
  source = pairs[0]
  target = pairs[1]
  return target
else:
  element = pairs[0]
  return element
```