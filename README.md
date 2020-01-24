# متن مذاکرات تصویب قانون اساسی جمهوری اسلامی ایران در سال 1358 و بازنگری در سال 1368

در این پروژه می‌خواهم متن مذاکرات تصویب قانون اساسی جمهوری اسلامی ایران در سال 1358 و بازنگری آن در سال 1368 را به صورت مرتب، برچسب‌خورده و قابل جستجو بر اساس اصل مورد بررسی، افراد و زمان بیاورم.

# Scheme
I use xml scheme for anootation in this project. Every part of each file, separates with **"section"** (if the part is block-line) or **"span"** (if the part is in-line) label. each section or span has one or many feature/value. **"type"** is a feature for all the sections and spans.

## Types of sesctions and spans.
- **session**: based on sessions of each parliment.
	* __number__: number of session on this parliment.
	* __title__: title of session based on that mentions on the book. normally persian number of session.
	* __date__: date of session based on Gregorian calendar with this format: "YYYY-MM-dd" (ex. 2020-01-17).
	* __start-time__: start time of session based on local time (Tehran time: GMT+3:30) with this format: "hh:mm" (ex. 13:00).
	* __end-time__: end time of session based on local time (Tehran time: GMT+3:30) with this format: "hh:mm" (ex. 13:00).
- **page**: based on pages of each book.
	* __number__: number of page in this book.
- **title**: title of book.
- **time-speaker**: description of date, time and speaker of this session.
	* __date__: date of session based on Gregorian calendar with this format: "YYYY-MM-dd" (ex. 2020-01-17).
	* __hijri-date__: date of session based on Islamic Hijri calendar with this format: "YYYY-MM-dd" (ex. 1399-07-20).
	* __solar-date__: date of session based on Solar Hijri calendar with this format: "YYYY-MM-dd" (ex. 1358-10-25).
	* __start-time__: start time of session based on local time (Tehran time: GMT+3:30) with this format: "hh:mm" (ex. 13:00).
	* __speaker-number__: the speaker number of this session.
	* __speaker__: the speaker name of this session that mentioned in the book.
- **list**: a list of headings on each session.
	* __number__: numbers of headings of this session.
- **list-title**: title of list.
- **list-item**: each item of this list.
	* __item-number__: the number of this item of list.
- **description**: description about other people (except main members of the parliment) that attended in session.
- **signature**: legal sign and confirmation of producer of book or the speaker of parliment.
- **heading**: heading of each part of this session.
- **event**: any event that happened in this session and normally mentioned in parantheses.
- **speech**: speech of any person on the parliment. 
	* __who-number__: if this speech has been talked by a member of parliment, number of member is written here. if not, 0 is written.
	* __who__: the name of speaker that mentioned in the book.
	* __role__: role of the speaker that has spoken. this feature contains this values: speaker, deputy-speaker, member, other.
		* speaker: the speaker of parliment (the Boss).
		* deputy-speaker: The deputy speaker of parliment.
		* member: every member of the parliment except ther speaker and the deputy speaker.
		* all-members: all members of parliment.
		* other: every person except members of parliment.
		* unknown
- **who-name**: this is the name of who speaks based on which mentioned in the book.
# Regex guideline
- Find paragraphs: ((\n|^).*?(?=\n|$))
- Regex for not all but many of events: (\n(\(.*?\))\r)