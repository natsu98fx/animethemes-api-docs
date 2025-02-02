---
title: Studio Show
---

<Block>

# Studio Show Endpoint

The studio show endpoint returns a studio resource.

For example, the `/api/studio/shaft` endpoint will return the studio resource for the production company Shaft.

## URL

```sh
GET /api/studio/{slug}
```

## Parameters

| Name    | Required | Description                                             |
| :-----: | :------: | :------------------------------------------------------ |
| fields  | No       | Sparse fieldsets for resource types                     |
| include | No       | Inclusion of related resources                          |
| filter  | No       | Filters to constrain the inclusion of related resources |

## Response

```json
{
    studio: {
        id: id,
        name: "name",
        slug: "slug",
        created_at: "created_at",
        updated_at: "updated_at",
        deleted_at: "deleted_at"
    }
}
```

<Example>

<CURL>
```bash
curl https://staging.animethemes.moe/api/studio/shaft
```
</CURL>

</Example>

</Block>