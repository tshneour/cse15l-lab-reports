## Lab Report 3

In this report, I will be covering 4 different options of Linux's `grep` command.

# Grep's Recursive Option

Grep's recursive option `-r` allows you to recursively search through a directory and its subdirectories. 
```
[cs15lwi23zzz@ieng6-203]:skill-demo1-data:232$ grep -r "Giza" written_2/
written_2/travel_guides/berlitz1/HistoryEgypt.txt:        the world was graced by the Great Pyramid at Giza built for Khufu (or        
written_2/travel_guides/berlitz1/HistoryEgypt.txt:        Kephren had the Sphinx erected in his honor at Giza. It was at this
written_2/travel_guides/berlitz1/WhatToEgypt.txt:        soundtrack accompany the dance of lights over the monuments. At Giza
written_2/travel_guides/berlitz1/WhatToEgypt.txt:        shadow of the pyramids at Giza, and you don’t need to be a guest to
written_2/travel_guides/berlitz1/WhereToEgypt.txt:        Giza
written_2/travel_guides/berlitz1/WhereToEgypt.txt:        Whatever the latest theory, the Pyramids of Giza (the most
written_2/travel_guides/berlitz1/WhereToEgypt.txt:        Archaeologists have concluded that the Giza pyramids were
written_2/travel_guides/berlitz1/WhereToEgypt.txt:        to rest here however. Giza was the site of a royal burial ground from        
written_2/travel_guides/berlitz1/WhereToEgypt.txt:        Giza was not the only location where pyramids were
```

In this example, I use `-r` to search through all of the subdirectories of `written_2/` for files containing the string "Giza". In this case, it is useful for finding information from a particular keyword (perhaps I want to learn more about the Great Pyramids of Giza or the city itself).
```
[cs15lwi23zzz@ieng6-203]:skill-demo1-data:242$ grep -r "Lucayan" written_2/travel_guides/
written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
```

In this example, I use `-r` to search for instances of "Lucayan" within the `travel_guides/` directory, which is inside `written_2`. In this case, it is useful to use `-r` to find a file with a keyword when I don't know exactly where it is. The file on Bahamas with "Lucayan" might be in written_2/travel_guides/berlitz1 or written_2/travel_guides/berlitz2 so `-r` is perfect to solve this.

# Grep's Count Option

Grep's counting option `-c` allows you to count the number of times a file uses a specific string. 

```
[cs15lwi23aom@ieng6-203]:skill-demo1-data:245$ grep -c "California" written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
30
```

In this example, I use `-c` to count how many instances of "California" there are in `WhereToLosAngeles.txt`. This is useful for keeping record of how much a file reuses a particular word.

```
[cs15lwi23zzz@ieng6-203]:skill-demo1-data:249$ grep -cr "Napoleon" written_2/travel_guides/berlitz1 
other files...
written_2/travel_guides/berlitz1/WhereToItaly.txt:12
written_2/travel_guides/berlitz1/WhereToJapan.txt:0
written_2/travel_guides/berlitz1/WhereToJerusalem.txt:1
written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt:0
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt:0
written_2/travel_guides/berlitz1/WhereToMadeira.txt:0
written_2/travel_guides/berlitz1/WhereToMadrid.txt:2
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:0
written_2/travel_guides/berlitz1/WhereToMallorca.txt:0
```

Perhaps I want to compare against other files how many times a word is used. Interestingly, "Napoleon" is repeated most in the file about Italy `WhereToItaly.txt`. In this case, I use the `-r` option in combination with `-c` to count the number of instances of "Napoleon" in `berlitz1`.

# Grep's File Matching Option

Grep's `-l` option allows you to only display the *names* of the files that contain the matching string.

```

```



```

```



# Grep's Inverse File Matching Option

Grep's `-L` option allows you to only display the *names* of the files that *do not* contain the matching string.

```

```



```

```

