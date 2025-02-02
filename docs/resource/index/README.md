---
title: Resource Index
---

<Block>

# Resource Index Endpoint

The resource index endpoint returns a listing of external resources.

## URL

```sh
GET /api/resource/
```

## Parameters

| Name         | Required | Description                                                                      |
| :----------: | :------: | :------------------------------------------------------------------------------- |
| fields       | No       | Sparse fieldsets for resource types                                              |
| include      | No       | Inclusion of related resources                                                   |
| filter       | No       | Filters for external resources & constraining the inclusion of related resources |
| sort         | No       | The list of fields to sort the external resources                                |
| page[size]   | No       | The number of external resources to display for the current page                 |
| page[number] | No       | The page of external resources to display                                        |

## Allowed Sort Fields

|    Name     | Description                                                           |
| :--------:  | :-------------------------------------------------------------------- |
| id          | Sort resources on the primary key                                     |
| link        | Sort resources on the URL of the resource                             |
| external_id | Sort resources on the identifier of the resource on the external site |
| site        | Sort resources on the premiere year of the anime                      |
| created_at  | Sort resources on the resource creation date                          |
| updated_at  | Sort resources on the resource last modified date                     |
| deleted_at  | Sort resources on the resource deletion date                          |
| random      | Sort resources randomly. Ignored if other sort fields are provided.   |

## Filters

|    Name     | Description                                                             |
| :--------:  | :---------------------------------------------------------------------- |
| id          | Filter resources on the primary key                                     |
| link        | Filter resources on the URL of the resource                             |
| external_id | Filter resources on the identifier of the resource on the external site |
| site        | Filter resources on the premiere year of the anime                      |
| created_at  | Filter resources on the resource creation date                          |
| updated_at  | Filter resources on the resource last modified date                     |
| deleted_at  | Filter resources on the resource deletion date                          |
| trashed     | Filter resources on trashed (deleted) status {With, Without, Only}      |

## Response

```json
{
    resources: [
        {
            id: id,
            link: "link",
            external_id: external_id,
            site: "site",
            created_at: "created_at",
            updated_at: "updated_at",
            deleted_at: "deleted_at",
            link: "link"
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
curl https://staging.animethemes.moe/api/resource/
```
</CURL>

</Example>

</Block>