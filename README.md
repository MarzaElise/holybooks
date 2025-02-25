# holybooks

An Api Wrapper for extracting info from: quran api and bible api. I didn\'t made the document for this so for now read the file to find all functions there. I will add more holybooks in the future!

## Installation

Find the module in here [Module](https://pypi.org/project/holybooks/)

```bash
pip install holybooks
```

## Usage

```python
# To return a verse(s) info inside the surah(Chapter)
from holybooks import Surah

surah=Surah.request(112) #'112' is the chapter and request is for sync function to make it async replace request to async_request()
print(surah.request_ayahs())
#return the verses in a list 

#===============================================================================================================================

# To return a bible verse's info
from holybooks import Bible

bible_verses=Bible.request(  #request is for sync function to make it async replace request to async_request()
    "2 Corinthians", chapter=4,
    starting_verse=16, ending_verse=18
)  # this gets the info of 2 Corinthians 4:16-18

for verse in bible_verses.verses:
    print(
        verse.citation,  # The citation of the current verse
        verse  # executes the __str__ method of the ChapterVerse class (it returns the verse itself)
    ) 

#===============================================================================================================================

from holybooks import Torah

torah_verses=Torah.request(  #request is for sync function to make it async replace request to async_request()
    "Genesis", chapter=1,
    starting_verse=1, ending_verse=10
)  # this gets the info of Genesis 1:1-10

for verse in torah_verses.verses:
    print(
        verse.citation,  # The citation of the current verse
        verse  # executes the __str__ method of the ChapterVerse class (it returns the verse itself)
    ) 
```

## API That I Used

[Qur'an](https://alquran.cloud/api)

[Bible](https://bible-api.com/)

[Torah](https://bible-api.com/)

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)
