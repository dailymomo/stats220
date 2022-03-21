# Index.md
## Motivation
1. I like some jokes about university, whcih related to students.
2. I would like to make some memes to show the **status from students**.


Here is the new original meme I created using the R code and the {magic} package.
![image](https://raw.githubusercontent.com/dailymomo/stats220/main/my_meme.png)

* I find two pictures about *drawing darts* and *"hard working"*. If these two pictures have different meanings, there would be great!
* Let major selection fits these two pictures.
* The meaning of this meme is that when students choose their major at the beginning of uni life, students may be like drawing darts blindly. But when we want to choose new clothes such as hoodies, we are very interested to choose and we may do a lot research.

## How to crerate this meme
1. Here is the original [Image1](https://www.dinoeliadis.com/wp-content/uploads/2018/06/800ThrowingDartBlind.jpeg) and [Image2](https://www.incimages.com/uploaded_files/image/1920x1080/getty_491709432_2000133320009280327_368554.jpg) we used from other websites.
2. Firstly, we read images using `image_read()` and set scale of 500.
3. Secondly, create blanks and add texts with specific styles by using `image_blank()` and `image_annotate`.
4. Combine each image and text together row by row.
5. Combine two rows together.
6. Save this meme as a image file in the same direction (stats220 project) using `image_write()`, and set "my_meme.png" as the name of this file.

## The original R code
```r
library(magick)

major <- image_read("https://www.dinoeliadis.com/wp-content/uploads/2018/06/800ThrowingDartBlind.jpeg") %>%
  image_scale(500)

hoodie <- image_read("https://www.incimages.com/uploaded_files/image/1920x1080/getty_491709432_2000133320009280327_368554.jpg") %>%
  image_scale(500)

text1 <- image_blank(width = 500,
                    height = 360,
                    color = "#000000") %>%
  image_annotate(text = "When I choose\nmy major",
                 color = "#FFFFFF",
                 size = 80,
                 font = "Impact",
                 gravity = "center")

text2 <- image_blank(width = 500,
                     height = 280,
                     color = "#000000") %>%
  image_annotate(text = "When I choose\nhoodie",
                 color = "#FFFFFF",
                 size = 80,
                 font = "Impact",
                 gravity = "center")

first_row <- c(major, text1) %>%
  image_append()

second_row <- c(hoodie, text2) %>%
  image_append()

meme <- c(first_row, second_row) %>%
  image_append(stack = T)

image_write(meme, "my_meme.png")

```

Click [stats220](https://github.com/dailymomo/stats220) to go back to `stats220` repo.

If you want to know more about **meme**, please see [meme](https://en.wikipedia.org/wiki/Meme).
