## POST Kanban Item

```bash
curl --request POST \
     --url https://api.miro.com/v2/boards/{board_id}/kanbans \
     --header 'accept: application/json' \
     --header "content-type: application/json" \
     --data '
{
  "title": "Kanban item",
  "position": {
    "x": 100,
    "y": 100
  },
  "columns": [
    {
      "name": "To Do",
      "cards": [
        {
          "title": "Task 1. Create API docs for Kanban API",
          "assignee": "Ruslan Kotowski",
          "due_date": "2023-08-31 12:00:00+00.00"
        },
        {
          "title": "Task 2. Create examples for Kanban API",
          "assignee": "Ruslan Kotowski",
          "due_date": "2023-09-15 15:30:00+00.00"
        }
      ]
    },
    {
      "name": "In Progress"
    }
  ]
}
'
```

## GET Kanban Item

```bash
curl --request GET \
     --url https://api.miro.com/v2/boards/{board_id}/kanbans/{item_id} \
     --header "accept: application/json"
```

## PUT Kanban Item

```bash
curl --request PUT \
     --url https://api.miro.com/v2/boards/{board_id}/kanbans/{item_id} \
     --header 'accept: application/json' \
     --header "content-type: application/json" \
     --data '
{
  "title": "Kanban item",
  "position": {
    "x": 100,
    "y": 100
  },
  "columns": [
    {
      "name": "To Do",
      "cards": [
        {
          "title": "Task 1. Create API docs for Kanban API",
          "assignee": "Ruslan Kotowski",
          "due_date": "2023-08-31 12:00:00+00.00"
        },
        {
          "title": "Task 2. Create examples for Kanban API",
          "assignee": "Ruslan Kotowski",
          "due_date": "2023-09-15 15:30:00+00.00"
        }
      ]
    },
    {
      "name": "In Progress",
      "cards": [
        {
          "title": "Task 3. Create overview for Kanban API",
          "assignee": "Ruslan Kotowski",
          "due_date": "2023-08-25 12:00:00+00.00"
        }
      ]
    }
  ]
}
'
```

## DELETE Kanban Item

```bash
curl --request DELETE \
     --url https://api.miro.com/v2/boards/{board_id}/kanbans/{item_id} \
     --header 'accept: application/json'
```

