# credits.json

credits.json is a file for keeping track of various blobs and files and who originally authored them.

This file is intended to be used in community driven development where files such as audio clips, textures and so forth are tracked.

## Structure

```json
{
  "authors": {
    "<AuthorName>": {
      "urls": [
        "link-to-author"
      ]
    }
  },
  "files": {
    "path/to/file": {
      "authors": ["<AuthorName>"],
      "modified_by": ["<AuthorName>"],
      "references": [
        {
          "url": "link-to-a-reference"
        }
      ]
    }
  }
}
```

## Schema

__Root Document__

| Field | Description | 
| ----- | ----------- |
| `authors` | A map containing the name of various people or entities that authored the original files |
| `files` | A map containing the relative path from the credits.json file to file in question |

__Author__

| Field | Description |
| ----- | ----------- |
| `urls` | A list of urls where the author or entity can be found |

__File__

| Field | Description |
| ----- | ----------- |
| `authors` | A list containing the names of the authors related to the file, the name should be the same as the one used in the authors map |
| `modified_by` | If a file was modified from its original this field can be populated with additional author names to say who did the modifications |
| `references` | A list of additional links, this can be used in conjuction with modified_by to link to the original file |

__Reference__

| Field | Description |
| ----- | ----------- |
| `url` | A link to anything, usually the original file before it was modified |

## Example

```json
{
  "authors": {
    "@IceDragon": {
      "url": "https://github.com/IceDragon200"
    }
  },
  "files": {
    "README.md": {
      "authors": ["@IceDragon200"]
    }
  }
}
```
