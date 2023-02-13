## Lab Report 3

In this report, I will be covering 4 different options of Linux's `grep` command. For all 4 of these options, I used Linux's built-in manual `man` to learn about them [Grep Manual](https://linux.die.net/man/1/grep).

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
(other files...)
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
[cs15lwi23zzz@ieng6-203]:skill-demo1-data:263$ grep -l "Eiffel Tower" written_2/travel_guides/berlitz1/HistoryFrance.txt written_2/travel_guides/berlitz1/IntroFrance.txt 
written_2/travel_guides/berlitz1/HistoryFrance.txt
```

In this case, I use `-l` to see which of `IntroFrance.txt` and `HistoryFrance.txt` contains mention of "Eiffel Tower". In this case, it displays only `HistoryFrance.txt` as output since it contains "Eiffel Tower". It's useful to use `-l` when I'm grepping multiple files and only care to see the paths of the files, not all the lines where the pattern is used.

```
[cs15lwi23zzz@ieng6-203]:skill-demo1-data:274$ grep -l "Winged Hussar" written_2/travel_guides/berlitz2/Poland-History.txt

```

In this example, I use `-l` to see if a single file `Poland-History.txt` contains "Winged Hussar". As seen however, there is no output, meaning that `Poland-History.txt` does not contain "Winged Hussar". If used as a bash command, `grep -l` could be used in the same way to check different files for a match.

# Grep's Inverse Line Matching Option

Grep's `-v` option allows you to only display the lines of a file that *do not* contain the matching string.

```
[cs15lwi23zzz@ieng6-203]:skill-demo1-data:285$ grep -v "the" written_2/travel_guides/berlitz2/California-History.txt  
A Brief History
The Spanish Missions
The Mexicans
The American Pioneers
The Gold Rush
Statehood
The Great Earthquake
Reform, Progress, and Oil
Hollywood
Depression and Boom

Beatniks, Hippies, and Modern Times
```

Here, I use `-v` to display all the lines in `California-History` that don't contain "the". As seen, it only prints the Section Headers, omitting all sentences. This is useful, particularly in this case, to see all non-sentences (perhaps I want to see what topics `California-History.txt` covers). Then, I could do this for other History files to compare and contrast.

```
[cs15lwi23zzz@ieng6-203]:skill-demo1-data:292$ grep -v "a" written_2/non-fiction/OUP/Abernathy/ch2.txt
Development of the Progressive Bundle System
Textiles: From Fiber to Cloth to Finished Product
```

Here, `-v` allows me to find which lines don't use "a" in `ch2.txt`. As shown, neither of the outputted lines have "a" in them. This grep option is particularly useful in this way by bounding the contents of the file. I can use it to help find a particular line, or maybe I want to save this output back into the original file to overwrite without the presence of a particular word or phrase.
