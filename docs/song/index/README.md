---
title: Song Index
---

<Block>

# Song Index Endpoint

The song index endpoint returns a listing of song resources.

## URL

```sh
GET /api/song/
```

## Parameters

| Name         | Required | Description                                                                   |
| :----------: | :------: | :---------------------------------------------------------------------------- |
| fields       | No       | Sparse fieldsets for resource types                                           |
| include      | No       | Inclusion of related resources                                                |
| filter       | No       | Filters for song resources & constraining the inclusion of related resources  |
| sort         | No       | The list of fields to sort the resources                                      |
| q            | No       | The query to search for matching song resources                               |
| page[size]   | No       | The number of song resources to display for the current page                  |
| page[number] | No       | The page of song resources to display                                         |

## Allowed Sort Fields

|    Name    | Description                                                         |
| :--------: | :------------------------------------------------------------------ |
| id         | Sort resources on the primary key                                   |
| title      | Sort resources on the title of the song                             |
| created_at | Sort resources on the resource creation date                        |
| updated_at | Sort resources on the resource last modified date                   |
| deleted_at | Sort resources on the resource deletion date                        |
| random     | Sort resources randomly. Ignored if other sort fields are provided. |

## Filters

|    Name    | Description                                                        |
| :--------: | :----------------------------------------------------------------- |
| id         | Filter resources on the primary key                                |
| title      | Filter resources on the title of the song                          |
| created_at | Filter resources on the resource creation date                     |
| updated_at | Filter resources on the resource last modified date                |
| deleted_at | Filter resources on the resource deletion date                     |
| trashed    | Filter resources on trashed (deleted) status {With, Without, Only} |

## Response

```json
{
    songs: [
        {
            id: id,
            title: "title",
            created_at: "created_at",
            updated_at: "updated_at",
            deleted_at: "deleted_at"
        },
        ...
    ],
    links: {
        first: "first",
        last: "last",
        prev: "prev",
        next: "next"
    },
    meta: {
        current_page: current_page,
        from: from,
        path: "path",
        per_page: per_page,
        to: to
    }
}
```

<Example>

<CURL>
```bash
curl https://staging.animethemes.moe/api/song/
```
</CURL>

</Example>

</Block>