# Researching Command: grep
[source](https://chat.openai.com/chat)

## 1. grep -r
- -r: search in all files under each directory, recursively

**example1**
```
angelawang@Angelas-MacBook-Air skill-demo1-data % grep -r "Lucayans" ./written_2                             
./written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
./written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```

I use `grep -r` to search "Lucayans" under `skill-demo-data/written_2`, it searches not only in the specified files, but also in all files under the directory

**example2**
```
angelawang@Angelas-MacBook-Air skill-demo1-data % grep -r "Italy has" ./written_2
./written_2/travel_guides/berlitz1/HistoryItaly.txt:        Italy has only existed as a nation since 1871. Before then,
./written_2/travel_guides/berlitz1/HistoryItaly.txt:        the European Union, Italy has more than held its own in heavy industry,
./written_2/travel_guides/berlitz1/WhereToItaly.txt:        economy, Italy has an elaborate network of information offices.
./written_2/travel_guides/berlitz1/WhereToItaly.txt:        Try to vary the kind of places that you stay in. Italy has
./written_2/travel_guides/berlitz1/WhereToItaly.txt:        Italy has no more magnificent testimony of its Greek
```

I use `grep -r` to search "Italy has" under `skill-demo-data/written_2`, instead of manually searching through each file, I can use `grep -r` to automate the process and quickly find the information I need.

- Base on examples, `grep -r` can be particularly useful when you need to search for a pattern in a large number of files or when you don't know in which file the pattern might be located. If you have a directory containing many files and subdirectories and you want to find all instances of the word "XXX" in those files, you can use the command `grep -r` 

## 2. grep -c
- -c: only print a count of matching lines

**example1**
```
angelawang@Angelas-MacBook-Air skill-demo1-data % grep -c "Italy" ./written_2/travel_guides/berlitz1/*.txt
./written_2/travel_guides/berlitz1/HandRHawaii.txt:0
./written_2/travel_guides/berlitz1/HandRHongKong.txt:0
./written_2/travel_guides/berlitz1/HandRIbiza.txt:0
./written_2/travel_guides/berlitz1/HandRIsrael.txt:0
./written_2/travel_guides/berlitz1/HandRIstanbul.txt:0
./written_2/travel_guides/berlitz1/HandRJamaica.txt:0
./written_2/travel_guides/berlitz1/HandRJerusalem.txt:0
./written_2/travel_guides/berlitz1/HandRLakeDistrict.txt:0
./written_2/travel_guides/berlitz1/HandRLasVegas.txt:0
./written_2/travel_guides/berlitz1/HandRLisbon.txt:0
./written_2/travel_guides/berlitz1/HandRLosAngeles.txt:0
./written_2/travel_guides/berlitz1/HandRMadeira.txt:0
./written_2/travel_guides/berlitz1/HandRMadrid.txt:0
./written_2/travel_guides/berlitz1/HandRMallorca.txt:0
./written_2/travel_guides/berlitz1/HistoryDublin.txt:0
./written_2/travel_guides/berlitz1/HistoryEdinburgh.txt:0
./written_2/travel_guides/berlitz1/HistoryEgypt.txt:0
./written_2/travel_guides/berlitz1/HistoryFWI.txt:0
./written_2/travel_guides/berlitz1/HistoryFrance.txt:3
./written_2/travel_guides/berlitz1/HistoryGreek.txt:1
./written_2/travel_guides/berlitz1/HistoryHawaii.txt:0
./written_2/travel_guides/berlitz1/HistoryHongKong.txt:0
./written_2/travel_guides/berlitz1/HistoryIbiza.txt:0
./written_2/travel_guides/berlitz1/HistoryIndia.txt:0
./written_2/travel_guides/berlitz1/HistoryIsrael.txt:0
./written_2/travel_guides/berlitz1/HistoryIstanbul.txt:2
./written_2/travel_guides/berlitz1/HistoryItaly.txt:44
./written_2/travel_guides/berlitz1/HistoryJamaica.txt:0
./written_2/travel_guides/berlitz1/HistoryJapan.txt:0
./written_2/travel_guides/berlitz1/HistoryJerusalem.txt:0
./written_2/travel_guides/berlitz1/HistoryLakeDistrict.txt:0
./written_2/travel_guides/berlitz1/HistoryLasVegas.txt:0
./written_2/travel_guides/berlitz1/HistoryMadeira.txt:1
./written_2/travel_guides/berlitz1/HistoryMadrid.txt:0
./written_2/travel_guides/berlitz1/HistoryMalaysia.txt:0
./written_2/travel_guides/berlitz1/HistoryMallorca.txt:1
./written_2/travel_guides/berlitz1/IntroDublin.txt:0
./written_2/travel_guides/berlitz1/IntroEdinburgh.txt:0
./written_2/travel_guides/berlitz1/IntroEgypt.txt:0
./written_2/travel_guides/berlitz1/IntroFWI.txt:0
./written_2/travel_guides/berlitz1/IntroFrance.txt:0
./written_2/travel_guides/berlitz1/IntroGreek.txt:0
./written_2/travel_guides/berlitz1/IntroHongKong.txt:0
./written_2/travel_guides/berlitz1/IntroIbiza.txt:0
./written_2/travel_guides/berlitz1/IntroIndia.txt:0
./written_2/travel_guides/berlitz1/IntroIsrael.txt:0
./written_2/travel_guides/berlitz1/IntroIstanbul.txt:0
./written_2/travel_guides/berlitz1/IntroItaly.txt:8
./written_2/travel_guides/berlitz1/IntroJamaica.txt:0
./written_2/travel_guides/berlitz1/IntroJapan.txt:0
./written_2/travel_guides/berlitz1/IntroJerusalem.txt:0
./written_2/travel_guides/berlitz1/IntroLakeDistrict.txt:0
./written_2/travel_guides/berlitz1/IntroLasVegas.txt:1
./written_2/travel_guides/berlitz1/IntroLosAngeles.txt:0
./written_2/travel_guides/berlitz1/IntroMadeira.txt:0
./written_2/travel_guides/berlitz1/IntroMadrid.txt:0
./written_2/travel_guides/berlitz1/IntroMalaysia.txt:0
./written_2/travel_guides/berlitz1/IntroMallorca.txt:0
./written_2/travel_guides/berlitz1/JungleMalaysia.txt:0
./written_2/travel_guides/berlitz1/WhatToDublin.txt:0
./written_2/travel_guides/berlitz1/WhatToEdinburgh.txt:0
./written_2/travel_guides/berlitz1/WhatToEgypt.txt:0
./written_2/travel_guides/berlitz1/WhatToFWI.txt:0
./written_2/travel_guides/berlitz1/WhatToFrance.txt:0
./written_2/travel_guides/berlitz1/WhatToGreek.txt:0
./written_2/travel_guides/berlitz1/WhatToHawaii.txt:0
./written_2/travel_guides/berlitz1/WhatToHongKong.txt:0
./written_2/travel_guides/berlitz1/WhatToIbiza.txt:0
./written_2/travel_guides/berlitz1/WhatToIndia.txt:0
./written_2/travel_guides/berlitz1/WhatToIsrael.txt:0
./written_2/travel_guides/berlitz1/WhatToIstanbul.txt:0
./written_2/travel_guides/berlitz1/WhatToItaly.txt:8
./written_2/travel_guides/berlitz1/WhatToJamaica.txt:0
./written_2/travel_guides/berlitz1/WhatToJapan.txt:0
./written_2/travel_guides/berlitz1/WhatToLakeDistrict.txt:0
./written_2/travel_guides/berlitz1/WhatToLasVegas.txt:0
./written_2/travel_guides/berlitz1/WhatToLosAngeles.txt:0
./written_2/travel_guides/berlitz1/WhatToMadeira.txt:0
./written_2/travel_guides/berlitz1/WhatToMalaysia.txt:0
./written_2/travel_guides/berlitz1/WhatToMallorca.txt:0
./written_2/travel_guides/berlitz1/WhereToDublin.txt:0
./written_2/travel_guides/berlitz1/WhereToEdinburgh.txt:0
./written_2/travel_guides/berlitz1/WhereToEgypt.txt:1
./written_2/travel_guides/berlitz1/WhereToFWI.txt:1
./written_2/travel_guides/berlitz1/WhereToFrance.txt:1
./written_2/travel_guides/berlitz1/WhereToGreek.txt:2
./written_2/travel_guides/berlitz1/WhereToHawaii.txt:0
./written_2/travel_guides/berlitz1/WhereToHongKong.txt:0
./written_2/travel_guides/berlitz1/WhereToIbiza.txt:0
./written_2/travel_guides/berlitz1/WhereToIndia.txt:0
./written_2/travel_guides/berlitz1/WhereToIsrael.txt:0
./written_2/travel_guides/berlitz1/WhereToIstanbul.txt:2
./written_2/travel_guides/berlitz1/WhereToItaly.txt:78
./written_2/travel_guides/berlitz1/WhereToJapan.txt:0
./written_2/travel_guides/berlitz1/WhereToJerusalem.txt:0
./written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt:0
./written_2/travel_guides/berlitz1/WhereToLosAngeles.txt:0
./written_2/travel_guides/berlitz1/WhereToMadeira.txt:0
./written_2/travel_guides/berlitz1/WhereToMadrid.txt:2
./written_2/travel_guides/berlitz1/WhereToMalaysia.txt:0
./written_2/travel_guides/berlitz1/WhereToMallorca.txt:0
```
I use the `grep -c` to count the number of lines that match "Italy" under `skill-demo-data/written_2/travel_guides/berlitz1/*.txt`, it shows HistoryFrance.txt has 3 matched lines, HistoryGreek.txt has 1 matched line, and so on

**example2**
```
angelawang@Angelas-MacBook-Air skill-demo1-data % grep -c "Lucayans" ./written_2/travel_guides/berlitz2/*.txt
./written_2/travel_guides/berlitz2/Algarve-History.txt:0
./written_2/travel_guides/berlitz2/Algarve-Intro.txt:0
./written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Algarve-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Amsterdam-History.txt:0
./written_2/travel_guides/berlitz2/Amsterdam-Intro.txt:0
./written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Athens-History.txt:0
./written_2/travel_guides/berlitz2/Athens-Intro.txt:0
./written_2/travel_guides/berlitz2/Athens-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Athens-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Bahamas-History.txt:2
./written_2/travel_guides/berlitz2/Bahamas-Intro.txt:0
./written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Bali-History.txt:0
./written_2/travel_guides/berlitz2/Bali-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Bali-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Barcelona-History.txt:0
./written_2/travel_guides/berlitz2/Barcelona-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Barcelona-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Beijing-History.txt:0
./written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Beijing-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Berlin-History.txt:0
./written_2/travel_guides/berlitz2/Berlin-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Berlin-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Bermuda-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Bermuda-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Bermuda-history.txt:0
./written_2/travel_guides/berlitz2/Boston-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Budapest-History.txt:0
./written_2/travel_guides/berlitz2/Budapest-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Budapest-WhereoGo.txt:0
./written_2/travel_guides/berlitz2/California-History.txt:0
./written_2/travel_guides/berlitz2/California-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/California-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Canada-History.txt:0
./written_2/travel_guides/berlitz2/Canada-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/CanaryIslands-History.txt:0
./written_2/travel_guides/berlitz2/CanaryIslands-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/CanaryIslands-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Cancun-History.txt:0
./written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/China-History.txt:0
./written_2/travel_guides/berlitz2/China-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/China-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Costa-History.txt:0
./written_2/travel_guides/berlitz2/Costa-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Costa-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/CostaBlanca-History.txt:0
./written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Crete-History.txt:0
./written_2/travel_guides/berlitz2/Crete-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Crete-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/CstaBlanca-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Cuba-History.txt:0
./written_2/travel_guides/berlitz2/Cuba-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Cuba-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Nepal-History.txt:0
./written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Nepal-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/NewOrleans-History.txt:0
./written_2/travel_guides/berlitz2/Paris-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Paris-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Poland-History.txt:0
./written_2/travel_guides/berlitz2/Poland-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Portugal-History.txt:0
./written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/PuertoRico-History.txt:0
./written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Vallarta-History.txt:0
./written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:0
```
I use the `grep -c` to count the number of lines that match "Lucayans" under `skill-demo-data/written_2/travel_guides/berlitz1/*.txt`, it shows only Bahamas-History.txt has 2 matched lines.

- Base on examples, `grep -c`can be useful when you only need to know how many instances of a pattern exist in a file or set of files, without needing to see the actual lines that match.

## 3. grep -w
- -w: only match whole words

**example1**
```
angelawang@Angelas-MacBook-Air skill-demo1-data % grep -w "sainthood" ./written_2/travel_guides/berlitz2/*.txt
./written_2/travel_guides/berlitz2/Portugal-History.txt:Portugal suffered several years of political confusion, but stable democracy finally took hold. With its entry into the European Union (formerly the European Economic Community) in 1986, the pace of development suddenly quickened. With aid from the EU, Portugal became one of the fastest-growing countries in Europe. In 1998, Portugal hosted the World Expo in Lisbon, and in 1999, further consolidated its European membership by accepting the gradual introduction of the Euro, the single currency also adopted by Spain, Italy, Germany, France, and others. Pope John Paul II paid his third visit to the shrine of Fátima in 2000 and beatified (the final step before sainthood) the shepherd boy and girl who claimed to be visited by the Virgin Mary over a period of six months in 1913. 
```
I use the `grep -w` to match the whole word "sainthood" under `skill-demo-data/written_2/travel_guides/berlitz2/*.txt`, it shows the whole word in the last sentense.

**example2**
```
angelawang@Angelas-MacBook-Air skill-demo1-data % grep -w "Lucayans" ./written_2/travel_guides/berlitz2/*.txt
./written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
./written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
I use the `grep -w` to match the whole word "Lucayans" under `skill-demo-data/written_2/travel_guides/berlitz2/*.txt`, it shows that Bahamas-history has two paragraphs mention the whole word "Lucayans".

- Base on examples, `grep -w` can be useful in situations where you only want to match complete words, rather than partial words that might appear as part of other words.

## 4. grep -n
- -n: print line numbers

**example1**
```
angelawang@Angelas-MacBook-Air skill-demo1-data % grep -n "sainthood" ./written_2/travel_guides/berlitz2/*.txt
./written_2/travel_guides/berlitz2/Portugal-History.txt:48:Portugal suffered several years of political confusion, but stable democracy finally took hold. With its entry into the European Union (formerly the European Economic Community) in 1986, the pace of development suddenly quickened. With aid from the EU, Portugal became one of the fastest-growing countries in Europe. In 1998, Portugal hosted the World Expo in Lisbon, and in 1999, further consolidated its European membership by accepting the gradual introduction of the Euro, the single currency also adopted by Spain, Italy, Germany, France, and others. Pope John Paul II paid his third visit to the shrine of Fátima in 2000 and beatified (the final step before sainthood) the shepherd boy and girl who claimed to be visited by the Virgin Mary over a period of six months in 1913.
```
I use the `grep -n` to find the lines that match the word "sainthood" under `skill-demo-data/written_2/*.txt`, it shows the word is in the line 48 in Portugal-history.

**example2**
```
angelawang@Angelas-MacBook-Air skill-demo1-data % grep -n "Lucayans" ./written_2/travel_guides/berlitz2/*.txt
./written_2/travel_guides/berlitz2/Bahamas-History.txt:6:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
./written_2/travel_guides/berlitz2/Bahamas-History.txt:7:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
I use the `grep -n` to find the lines that match the word "Lucayans" under `skill-demo-data/written_2/*.txt`, it shows the word is in the line 6 and 7 in Bahamas-history.

- Base on examples, `grep -n` can be useful when you need to know the exact line number where a pattern appears, for example when debugging code or analyzing log files.
