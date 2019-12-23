# متن مذاکرات تصویب قانون اساسی جمهوری اسلامی ایران در سال 1358 و بازنگری در سال 1368

در این پروژه می‌خواهم متن مذاکرات تصویب قانون اساسی جمهوری اسلامی ایران در سال 1358 و بازنگری آن در سال 1368 را به صورت مرتب، برچسب‌خورده و قابل جستجو بر اساس اصل مورد بررسی، افراد و زمان بیاورم.

# Scheme
I use xml scheme for anootation in this project. Every part of each file, separates with **"section"** (if the part is block-line) or **"span"** (if the part is in-line) label. each section or span has one or many feature/value. **"type"** is a feature for all the sections and spans.

## Type of sesctions and spans.
- **session**: based on sessions of each parliment.
	* __number__: number of session on this parliment.
	* __title__: title of session based on that mentions on the book. normally persian number of session.
- **page**: based on pages of each book.
	* __number__: number of page in this book.
- **title**: title of book.
- **time-leadership**: description of date, time and speaker of this session.
- **list**: a list of headings on each session.
	* __number__: numbers of headings of this session.
- **description**: description about other people (except main members of the parliment) that attended in session.
- **signature**: legal sign and confirmation of producer of book or the speaker of parliment.
- **heading**: heading of each part of this session.
- **event**: any event that happened in this session and normally mentioned in parantheses.
- **speech**: speech of any person on the parliment. 
	* __speaker-number__: if this speech has been talked by a member of parliment, number of member is written here. if not, 0 is written.
	* __speaker__: the name of speaker that mentioned in the book.
	* __role__: role of the speaker that has spoken. this feature contains this values: speaker, deputy-speaker, member, other.

# Regex guideline
- Find paragraphs: ((\n|^).*?(?=\n|$))
- Regex for not all but many of events: (\n(\(.*?\))\r)