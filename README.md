## ⚗ List Alchemist

Simple web tool for converting a list of strings using Regular Expressions and custom templates.

### Parameters

| Name |  URL Interface | Description | Example |
| :--- | :--- | :--- | :--- |
| **Items List** | `list` | The raw text to transform. One item per line. | `http://site.com/123` |
| **Regex Rule** | `regex` | The pattern to find data. Use `(?<pname>...)`. | `(?<id>\d+)` |
| **Template** | `template` | The output format. Use `{pname}` or `%s` for the full line. | `<div id="{id}">%s</div>` |

#### URL Interface

You can specify parameters directly in the URL:

* `list`: Pre-fills the source text.
* `regex`: Sets the extraction rule.
* `template`: Sets the composition format.

**Sample:** 
- [Transform books URLs from one bookstore to another, with direct link.](https://tcoppex.github.io/list-alchemist/?regex=%28%3F%3Ahttps%3F%3A%2F%2F%29%3F%28%3F%3Awww%5C.%29%3Fbookstore%5C.%5Ba-z%5D%7B2%2C3%7D%28%3F%3A%2F%5B%5E%2F%5D%2B%29%3F%2Fdp%2F%28%3F%3Cisbn%3E%5B%5E%2F%5Cs%3F%5D%2B%29&template=<a+href%3D"https%3A%2F%2Fan-archive.gl%2Fsearch%3Fq%3D{isbn}">{isbn}<%2Fa>&list=https%3A%2F%2Fwww.bookstore.com%2Fpassport_to_somewhere%2Fdp%2F0987422480%0Ahttp%3A%2F%2Fbookstore.de%2Fdp%2F019069288X)

### QRCode Generation

The `Generate configuration URL` button will update the URL with the current configuration (without the item list), copy it to the clipboard, and generate a QRcode to share it easily.
