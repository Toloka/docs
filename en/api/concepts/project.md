# Overview

Set the properties of tasks and responses in the project:

- Input data parameters. Describe the objects to display in the task, such as images or text.

- Output data parameters. These parameters describe Tolokers' responses. They are used for validating the responses entered: the data type (integer, string, etc.), range of values, string length, and so on.

- Task interface. Defines the appearance of the task for Tolokers and the logic for processing responses.

## Methods {#methods}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#tag--project):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

Method | Endpoint | Overview
----- | ----- | -----
POST | [/projects](create-prj.md) | Creates a project.
PUT | [/projects/<project_id>](edit-prj.md) | Edits a project.
GET | [/projects](get-prj-list.md) | Gets the list of projects.
GET | [/projects/<project_id>](get-prj.md) | Gets project properties.
POST | [/projects/<project_id>/archive](archive-prj.md) | Sends a project to the archive.

## Learn more {#links}

- [More information about projects](../../guide/concepts/project.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}