## List Alchemist

Simple web tool for converting a list of strings using Regular Expressions and custom templates.

### Parameters

| Parameter | Description | Example |
| :--- | :--- | :--- |
| **Items List** | The raw text to transform. One item per line. | `http://site.com/123` |
| **Regex Rule** | The pattern to find data. Use `(?<pname>...)`. | `(?<id>\d+)` |
| **Template** | The output format. Use `{pname}` or `%s` for the full line. | `<div id="{id}">%s</div>` |

### URL Interface

* `list`: Pre-fills the source text.
* `regex`: Sets the extraction rule.
* `template`: Sets the composition format.

**Example:** `index.html?regex=(?<id>\d+)&template=ID:{id}&list=123`

Live sample: [Transform some bookstore's URLS to another](https://tcoppex.github.io/list-alchemist/?regex=%28%3F%3Ahttps%3F%3A%2F%2F%29%3F%28%3F%3Awww%5C.%29%3Fbookstore%5C.%5Ba-z%5D%7B2%2C3%7D%28%3F%3A%2F%5B%5E%2F%5D%2B%29%3F%2Fdp%2F%28%3F%3Cisbn%3E%5B%5E%2F%5Cs%3F%5D%2B%29&template=https%3A%2F%2Fan-archive.gl%2Fsearch%3Fq%3D%7Bisbn%7D&list=https%3A%2F%2Fwww.bookstore.com%2Fpassport_to_somewhere%2Fdp%2F0987422480%0Ahttp%3A%2F%2Fbookstore.de%2Fdp%2F019069288X)

### QRCode Generation

The `Generate configuration URL` button will update the URL with the current configuration (without the item list), copy it to the clipboard, and generate a QRcode to share it easily.
