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

I need these data to be connected to each other, in order for later work in `Palladio`. Therefore, I created column <mark>connections</mark>, and then created <mark>target</mark>, and <mark>source</mark> (from connections column) for each original column (game-publisher-genre-developer-religious inspiration).  

<u>But by this point, I stumbled upon a big problem. In the original lesson, with the lecturer's guide and example, his data has different structure than mine. All of his data can be splitted and paired, but my data is not always splittable and pairable, some of them is unique. Therefore, if I use the original code snippet that the lecturer provided, it will not work (and indeed it did not work). Hence, I have to change some elements in his original codes.</u>

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
The above code snippet is for pairing (so each item in a category can be paired with each other). And this is the new one:
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
<mark>Note: my split value is `,` instead of `;`, at first I forgot about this and copied exactly what the lecturer presented and later realized that I do not have the same data structure as his.</mark>

First thing first, I created a new column named `genre_connections` based on column `Genre` by filling 32 rows with the above new jython code. Next, I do the same for column `Publisher`, `Religious Inspiration` (since only these three caterogies have multiple options/have non-unique values). 

Second step is to split multi-valued cells in column `genre_connections` that I just created. In order to do this task, I go to `Edit Cells` and split them up by the separator `,` with `Split multi-valued cells`. This step makes sure that no multiple entries are in one cell. 

Thirdly, based on column `genre_connections`, I created two new column `genre_target` and `genre_source`, using this below code snippet:
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
I did the same for the rest, creating these two new columns for each connections column. After this step, when the new rows with empty entries are added, I go to `Edit Cells` once again and go to the option `Fill Down` to fill down the text downwards (so that there will be no empty cells anymore). Of course, I also did the same for every column.

At the end, the whole database looks like this.  
![Alt text](<../assets/image/posts/Screenshot 2023-09-29 131458.png>)

### III. Using Palladio