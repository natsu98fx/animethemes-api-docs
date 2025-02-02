---
title: Announcement Index
---

<Block>

# Announcement Index Endpoint

The announcement index endpoint returns a listing of announcement resources.

## URL

```sh
GET /api/announcement/
```

## Parameters

| Name         | Required | Description                                                                          |
| :----------: | :------: | :----------------------------------------------------------------------------------- |
| fields       | No       | Sparse fieldsets for resource types                                                  |
| include      | No       | Inclusion of related resources                                                       |
| filter       | No       | Filters for announcement resources & constraining the inclusion of related resources |
| sort         | No       | The list of fields to sort the announcement resources                                |
| page[size]   | No       | The number of announcement resources to display for the current page                 |
| page[number] | No       | The page of announcement resources to display                                        |

## Allowed Sort Fields

|    Name    | Description                                                         |
| :--------: | :------------------------------------------------------------------ |
| id         | Sort resources on the primary key                                   |
| content    | Sort resources on the announcement text                             |
| created_at | Sort resources on the resource creation date                        |
| updated_at | Sort resources on the resource last modified date                   |
| deleted_at | Sort resources on the resource deletion date                        |
| random     | Sort resources randomly. Ignored if other sort fields are provided. |

## Filters

|    Name    | Description                                                        |
| :--------: | :----------------------------------------------------------------- |
| id         | Filter resources on the primary key                                |
| content    | Filter resources on the announcement text                          |
| created_at | Filter resources on the resource creation date                     |
| updated_at | Filter resources on the resource last modified date                |
| deleted_at | Filter resources on the resource deletion date                     |
| trashed    | Filter resources on trashed (deleted) status {With, Without, Only} |

## Response

```json
{
    announcements: [
        {
            id: id,
            content: "content",
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
curl https://staging.animethemes.moe/api/announcement/
```
</CURL>

</Example>

</Block>