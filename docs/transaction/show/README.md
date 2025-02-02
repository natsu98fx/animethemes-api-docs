---
title: Transaction Show
---

<Block>

# Transaction Show Endpoint

The transaction show endpoint returns a transaction resource.

## URL

```sh
GET /api/transaction/{id}
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
    transaction: {
        id: id,
        date: "date",
        service: "service",
        description: "description",
        amount: amount,
        external_id: external_id,
        created_at: "created_at",
        updated_at: "updated_at",
        deleted_at: "deleted_at"
    }
}
```

<Example>

<CURL>
```bash
curl https://staging.animethemes.moe/api/transaction/1
```
</CURL>

</Example>

</Block>