---
title: Resources
icon: fas fa-cog
order: 4
---

A few resources I regularly refer to. Collected here for ease of personal access

- <a target="_blank" href="https://books.google.co.in/advanced_book_search">Advanced Book Search - Google</a>
- <a target="_blank" href="https://aksharamukha.appspot.com/converter">Aksharamukha</a>
- <a target="_blank" href="https://ancientvoice.wikidot.com/">Ancient Voice</a>
- <a target="_blank" href="https://www.cfd-online.com/">CFD Online</a>
- <a target="_blank" href="https://ctext.org/">Chinese Text Project</a>
- <a target="_blank" href="https://www.f1technical.net/">F1 Technical</a>
- <a target="_blank" href="https://www.youtube.com/channel/UCcqQi9LT0ETkRoUu8eYaEkg">Fluid Mechanics 101</a>
- <a target="_blank" href="https://translate.google.co.in/">Google Translate</a>
- <a target="_blank" href="https://gretil.sub.uni-goettingen.de/gretil.html">GRETIL</a>
- <a target="_blank" href="https://sites.google.com/site/harshalarajesh/">harshala_rajesh</a>
- <a target="_blank" href="https://www.gitasupersite.iitk.ac.in/">IITK Scriptures</a>
- <a target="_blank" href="https://archive.org/">Internet Archive</a>
- <a target="_blank" href="https://www.jstor.org/">jstor</a>
- <a target="_blank" href="https://www.kamakotimandali.com/">Kamakotimandali</a>
- <a target="_blank" href="https://kirtimukha.com/">Kirtimukha</a>
- <a target="_blank" href="https://koyil.org/">Koyil</a>
- <a target="_blank" href="https://www.learnsanskrit.cc/">Learn Sanskrit - Dictionary</a>
- <a target="_blank" href="https://www.libgen.is/">Libgen</a>
- <a target="_blank" href="https://madhwaprameyamahodadhi.blogspot.com/">Madhwaprameya Mahodadhi</a>
- <a target="_blank" href="https://sites.google.com/site/madhwaprameyaqa/">Madhwaprameya Mahodadhi Q&A</a>
- <a target="_blank" href="https://www.sanskrit-lexicon.uni-koeln.de/scans/MWScan/2020/web/webtc/indexcaller.php">Monier Williams</a>
- <a target="_blank" href="https://narayanastra.blogspot.com/p/home-page.html">Narayanastra</a>
- <a target="_blank" href="https://www.onlinegdb.com/online_python_compiler">Online GDB</a>
- <a target="_blank" href="https://www.perseus.tufts.edu/hopper/">Perseus Digital Library</a>
- <a target="_blank" href="https://ramanuja.org/sri/Web/Index">Ramanuja.org</a>
- <a target="_blank" href="https://sacred-texts.com/">Sacred Texts</a>
- <a target="_blank" href="https://www.sadagopan.org/">Sadagopan</a>
- <a target="_blank" href="https://sanskritdocuments.org/">Sanskrit Documents</a>
- <a target="_blank" href="https://sanskrit.jnu.ac.in/sandhi/viccheda.jsp?itext=%E0%A4%AE%E0%A4%A6%E0%A5%8D%E0%A4%AF%E0%A4%BE%E0%A4%9C%E0%A4%BF%E0%A4%A8%E0%A4%83&itrans=&lastChar=#results">Sanskrit Sandhi Splitter - JNU</a>
- <a target="_blank" href="https://greenmesg.org/sanskrit_online_tools/sanskrit_sandhi_tool.php">Sanskrit Sandhi Tool - Greenmesg</a>
- <a target="_blank" href="https://anandamakaranda.in/">Sarvamoola Grantha</a>
- <a target="_blank" href="https://srimadhvyasa.wordpress.com/">Srimadhvyasa</a>
- <a target="_blank" href="https://www.team-bhp.com/">Team BHP</a>
- <a target="_blank" href="https://en.wikisource.org/wiki/Wikisource:Books">Wikisource</a>
- <a target="_blank" href="https://www.wisdomlib.org/">Wisdomlib</a>

# To-Do

- [ ] <a target="_blank" href="https://aurvadahana.github.io/posts/buddhavatara-madhva-perspective/#prasantavidya">Praśāntavidyā</a>
- [ ] BSB

# HTML hyperlink

```python
pip install pyperclip
import pyperclip

strr = '<a target="_blank" href=""></a>'

lin = ''
name = ''

fl = '"'.join(strr.split('"')[:3]) + '"' + lin + '">' + name + '</a>'
print(fl)
pyperclip.copy(fl)
```

# VS Post - HTML name list

```python
listt = ['Sarvaḥ', 'Śarvaḥ', 'Śivaḥ', 'Sthāṇuḥ', 'Bhūtādiḥ', 'Nidhiravyayaḥ', 'Sambhavaḥ', 'Bhāvanaḥ', 'Bhartā', 'Prabhavaḥ', 'Prabhuḥ', 'Īśvaraḥ']
n_start = 25

for numm, name in enumerate(listt):
    numm += n_start
    itemm = '<li>' + name + f' (<a href="#tr{numm}">tr</a>, <a href="#ot{numm}">ot</a>)</li>'
    print(itemm)
```

# VS Post - HTML Content

```python
listt = ['Sarvaḥ', 'Śarvaḥ', 'Śivaḥ', 'Sthāṇuḥ', 'Bhūtādiḥ', 'Nidhiravyayaḥ', 'Sambhavaḥ', 'Bhāvanaḥ', 'Bhartā', 'Prabhavaḥ', 'Prabhuḥ', 'Īśvaraḥ']
listt_dev = ['सर्वः', 'शर्वः', 'शिवः', 'स्थाणुः', 'भूतादिः', 'निधिरव्ययः', 'सम्भवः', 'भावनः', 'भर्ता', 'प्रभवः', 'प्रभुः', 'ईश्वरः']
n_start = 25


for numm, name in enumerate(listt):
    numm += n_start
    print(f'<div id="tr{numm}" style="position: absolute; left: -9999px;">;</div>\n')
    print(f'### {numm}. {listt_dev[numm - n_start]} / {name} [[ot]](#ot{numm})\n')
    
print('## Original Text with References\n')

for numm, name in enumerate(listt):
    numm += n_start
    print(f'<div id="ot{numm}" style="position: absolute; left: -9999px;">;</div>\n')
    print(f'### {numm}. {listt_dev[numm - n_start]} / {name} [[tr]](#tr{numm})\n')
```
