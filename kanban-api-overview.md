# Overview and user scenario

## What is Kanban API?

Our new Kanban API is a powerful tool empowering developers to seamlessly integrate Kanban boards directly into Miro boards. With this API, developers can create, manage, and optimize Kanban boards with self-contained items that consist of customizable columns and movable cards. These items provide an interactive and visual approach to tracking tasks and their workflow stages, enhancing workflow efficiency and collaboration within Miro.

## When do I need Kanban API?

Teams use Kanban boards to monitor the progress of work from start to finish. Imagine a development team that uses Miro for project management and collaboration. With Kanban API, the team can programmatically create Kanban items on a Miro board. For instance, when a new task is added to their project management system, the API can automatically create a corresponding Kanban item on their Miro board. Team members can then interact with these items, moving cards across columns as tasks progress, and making use of the visual representation to track the status of their work in a more engaging and efficient way.

---

# Changelog

## [yyyy-mm-dd] changelog

Introducing Kanban API in REST API 2.0

### What's new

Introducing Kanban API to enable programmatic creation, management, and optimization of Kanban items within Miro boards. This API enhances project management capabilities within Miro by integrating a visual and interactive Kanban workflow.

- POST endpoint for creating new Kanban items, specifying title, position, and columns.
- GET endpoint to retrieve detailed information about a Kanban item, including title, position, and columns.
- PUT endpoint for updating existing Kanban items, allowing modification of title, position, and columns.
- DELETE endpoint for removing Kanban items from the Miro board.

For more information, see [Kanban API](kanban-v2.json).

---

# Review and validation

The following process could take place from the moment when I receive the requirements up to when the API is released. The process largely depends on other teams working on the same release.

1. Collect the requirements
	- Meet the Product Manager to understand the objectives and goals of the API documentation.
	- Discuss the target audience and their needs.
2. Get to know the API
	- Get a grasp of endpoints, data structures, etc.
3. Design documentation architecture
	- Plan the structure of the documentation. Decide if it will be a single document or split into multiple sections or files.
4. Work on the API reference
	For each API endpoint, document:
		- Endpoint URL
		- Supported HTTP methods
		- Request parameters (query parameters, headers, path parameters, request body)
		- Response status codes and data structures
		- Authentication and authorization requirements
		- Rate limiting or usage restrictions
		- Add examples
		- Add error codes
5. Test endpoints
	- Test that all endpoints are working as documented.
6. Get feedback
	- Share the documentation with the API Product Manager, developers, and other stakeholders.
	- Iterate and make necessary corrections based on their feedback.
7. Prepare documentation for release
	- Include the changelog/release note
8. Publish documentation
9. Announce the release
	- Inform stakeholders about the availability of the new API documentation.
10. Maintenance stage

---

# Feedback, notes, questions

1. What’s the correct name: Kanban board or Kanban table?
2. What is the reason to use PUT instead of PATCH for updating a Kanban item? PATCH would make it more consistent with the rest of Miro APIs. This would also make it easier to update Kanban items that have multiple columns with dozens of cards.
3. Would it make sense to further add the `/cards` resource? This can make updating single cards on the Kanban board even easier.
4. What are the defaults? For example, for the `x` and `y` coordinates.
5. What is the max length for strings?
6. I’d rename `due_date` to `dueDate` to keep it consistent with the rest of APIs.
7. I’d use `title` for the name of the column on the Kanban board for consistency with the rest of APIs.
8. I’ve added HTTP error codes that are typical for corresponding methods. Alternatively, this could be aligned with the rest of Miro’s APIs.
9. Examples provided in the **examples.md** are built for cURL for simplicity. Examples for programming languages can be further generated, for example with Postman.
10. While working on the test, I've noticed that the API spec and the response example for [Create card item](https://developers.miro.com/reference/create-card-item) describes item `id` as a string and an integer accordingly. The example should probably contain `id` as a string.
