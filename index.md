# Index
## motivation
1. I like some jokes about university.

2. I would like to make some memes to show the **status from students**.


Here is a meme I made using the R package{magic}.

![image](https://raw.githubusercontent.com/dailymomo/stats220/main/my_meme.png)

*I find two pictures about *darts* and *"hard working"*. If these two pictures have different means, that would be great!

*Let major selection fit these two picture.

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


Click [stats220](https://github.com/dailymomo/stats220) to go back to `stats220` Github page.
