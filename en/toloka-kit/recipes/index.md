# Recipes for Toloka-Kit common tasks

Before you can start using Toloka-Kit, you need to [register with Toloka](../../guide/concepts/access.md), [get an API key](../registration.md), and [install the Toloka-Kit](../quick-start.md) Python library. After that, you can create projects, pools, upload tasks, and get results.

Use the list of recipes below to find out how to start working with Toloka-Kit.

## Projects

<div class="recipe_blocks">
    <div class="recipe_block">
        <p class="recipe_block_heading">Create project</p>
        <p class="recipe_block_description">Create a minimal working project using Toloka-Kit</p>
        <p class="recipe_steps">6 steps</p>
        <a class="recipe_button" href="./create-project">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Get list of projects</p>
        <p class="recipe_block_description">Get all the projects with a certain status created after a specified date</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./get-projects">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Get project details</p>
        <p class="recipe_block_description">Get the detailed information about the project with the ID specified in the request</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./get-project-by-id">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Edit project</p>
        <p class="recipe_block_description">Change the project public description using Toloka-Kit</p>
        <p class="recipe_steps">6 steps</p>
        <a class="recipe_button" href="./edit-project">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Archive project</p>
        <p class="recipe_block_description">Move the project which you no longer use into archive</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./archive-project">Go to recipe</a>
    </div>
</div>

## Pools

<div class="recipe_blocks">
    <div class="recipe_block">
        <p class="recipe_block_heading">Create pool</p>
        <p class="recipe_block_description">Create a pool in a project in Toloka</p>
        <p class="recipe_steps">5 steps</p>
        <a class="recipe_button" href="./create-pool">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Get list of pools</p>
        <p class="recipe_block_description">Get the list of the pools with the <code>CLOSED</code> status in your project</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./get-pools">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Get pool details</p>
        <p class="recipe_block_description">Get the detailed information about the pool with the ID specified in the request</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./get-pool-by-id">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Open pool</p>
        <p class="recipe_block_description">Open a closed pool in Toloka</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./open-pool">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Close pool</p>
        <p class="recipe_block_description">Close an opened pool in Toloka</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./close-pool">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Archive pool</p>
        <p class="recipe_block_description">Move the pool which you no longer use into archive</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./archive-pool">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Clone pool</p>
        <p class="recipe_block_description">Create a copy of an existing pool preserving the main parameters</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./clone-pool">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Change pool priority</p>
        <p class="recipe_block_description">Change the priority of the pool and offer it to Tolokers before other pools</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./change-pool-priority">Go to recipe</a>
    </div>
</div>

### Toloker selection

<div class="recipe_blocks">
    <div class="recipe_block">
        <p class="recipe_block_heading">Set overlap</p>
        <p class="recipe_block_description">Set overlap for tasks at pool, task suite, and task levels</p>
        <p class="recipe_steps">6 steps</p>
        <a class="recipe_button" href="./set-overlap">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Filter Tolokers</p>
        <p class="recipe_block_description">Use pool filters to specify the Toloker groups you want to pick your tasks</p>
        <p class="recipe_steps">5 steps</p>
        <a class="recipe_button" href="./filter-tolokers">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Filter Tolokers with confirmed language knowledge</p>
        <p class="recipe_block_description">Use pool filters to filter the Tolokers with various languages for which they passed the language test</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./filter-tolokers-languages">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Use quality control rules</p>
        <p class="recipe_block_description">Use quality control rules to restrict access to the tasks for the Tolokers who try and breach them</p>
        <p class="recipe_steps">9 steps</p>
        <a class="recipe_button" href="./use-quality-control-rules">Go to recipe</a>
    </div>
</div>

## Skills

<div class="recipe_blocks">
    <div class="recipe_block">
        <p class="recipe_block_heading">Get skills</p>
        <p class="recipe_block_description">Get all the skills available in your Toloka account</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./get-skills">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Create skill</p>
        <p class="recipe_block_description">Create a skill that you can assign to Tolokers</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./create-skill">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Assign skill to Toloker</p>
        <p class="recipe_block_description">Assign an existing skill to Tolokers an set its level</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./assign-skill">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Edit skill</p>
        <p class="recipe_block_description">Modify an existing skill</p>
        <p class="recipe_steps">6 steps</p>
        <a class="recipe_button" href="./edit-skill">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">List Tolokers with skills</p>
        <p class="recipe_block_description">Get all the skills assigned to the Toloker with the ID specified in the request</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./get-user-skills">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Remove skill from Toloker</p>
        <p class="recipe_block_description">Remove the skill from the Toloker using the ID of the "skill-Toloker" pair</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./delete-user-skill">Go to recipe</a>
    </div>
</div>

## Tasks and task suites

<div class="recipe_blocks">
    <div class="recipe_block">
        <p class="recipe_block_heading">Group tasks in task suites</p>
        <p class="recipe_block_description">Create tasks and group them into task suites</p>
        <p class="recipe_steps">6 steps</p>
        <a class="recipe_button" href="./create-task-suite">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Upload tasks</p>
        <p class="recipe_block_description">Create and upload control and general tasks to the pool</p>
        <p class="recipe_steps">6 steps</p>
        <a class="recipe_button" href="./upload-tasks">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Get list of tasks</p>
        <p class="recipe_block_description">Get all the tasks in the pool with the ID specified in the request</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./get-tasks">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Get task details</p>
        <p class="recipe_block_description">Get the detailed information about the task with the ID specified in the request</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./get-task-by-id">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Change task overlap</p>
        <p class="recipe_block_description">Increase the overlap of a task when you need more Tolokers to complete it</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./change-task-overlap">Go to recipe</a>
    </div>
</div>

## Responses

<div class="recipe_blocks">
    <div class="recipe_block">
        <p class="recipe_block_heading">Get list of responses</p>
        <p class="recipe_block_description">Get all the Toloker responses present in the pool with the ID specified in the request</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./get-responses">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Aggregate responses in pool</p>
        <p class="recipe_block_description">Aggregate the responses from Tolokers for all completed tasks in a pool</p>
        <p class="recipe_steps">5 steps</p>
        <a class="recipe_button" href="./aggregate-responses">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Accept responses from Tolokers</p>
        <p class="recipe_block_description">Accept Toloker responses with the IDs specified in the request</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./accept-responses">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Reject responses from Tolokers</p>
        <p class="recipe_block_description">Reject Toloker responses with the IDs specified in the request</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./reject-responses">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Get list of files in responses</p>
        <p class="recipe_block_description">List all the files attached to the Toloker responses in a pool</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./get-attachments">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Download attachments</p>
        <p class="recipe_block_description">Download the files attached to the Toloker responses</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./download-attachment">Go to recipe</a>
    </div>
</div>

## Bonuses

<div class="recipe_blocks">
    <div class="recipe_block">
        <p class="recipe_block_heading">Issue bonuses to Tolokers</p>
        <p class="recipe_block_description">Additionally reward Tolokers who completed their tasks better than others</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./assign-reward">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Get list of all bonuses issued</p>
        <p class="recipe_block_description">Get all the bonuses you issued in Toloka</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./get-rewards">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Get bonus details</p>
        <p class="recipe_block_description">Get the detailed information about the bonus with the ID specified in the request</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./get-reward-by-id">Go to recipe</a>
    </div>
</div>

## Banning Tolokers

<div class="recipe_blocks">
    <div class="recipe_block">
        <p class="recipe_block_heading">Ban Tolokers</p>
        <p class="recipe_block_description">Restrict the access to tasks for Tolokers</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./ban-tolokers">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Get list of bans</p>
        <p class="recipe_block_description">Get the list of all the Toloker bans</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./get-restrictions">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Remove ban from Toloker</p>
        <p class="recipe_block_description">Remove restriction from Tolokers and restore their access to tasks</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./delete-restriction">Go to recipe</a>
    </div>
</div>

## Messages

<div class="recipe_blocks">
    <div class="recipe_block">
        <p class="recipe_block_heading">Send messages</p>
        <p class="recipe_block_description">Compose and send messages to single or multiple recipients in Toloka</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./send-messages">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Get list of message threads</p>
        <p class="recipe_block_description">Get the list of all the message threads present in a specific folder in your account</p>
        <p class="recipe_steps">3 steps</p>
        <a class="recipe_button" href="./get-message-threads">Go to recipe</a>
    </div>
    <div class="recipe_block">
        <p class="recipe_block_heading">Reply to message thread</p>
        <p class="recipe_block_description">Send a reply to a message thread in Toloka</p>
        <p class="recipe_steps">4 steps</p>
        <a class="recipe_button" href="./reply-to-message-thread">Go to recipe</a>
    </div>
</div>

## Advanced Toloka-Kit user?

If you feel rather confident as a Toloka-Kit user and want to try a more complex scenario, refer to the following pages:

- [your first complete project](learn-basics.md)
- [more usage examples](use-cases.md)

<style scoped>
.recipe_blocks {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(190px, 1fr));
    gap: 30px;
    text-align: center;
}
.recipe_block {
    box-shadow: 1px 1px 15px rgba(30,33,38,.12);
    padding: 20px;
    border-radius: 6px;
    display: grid;
}
.recipe_block_heading {
    font-size: 17px;
    line-height: 21px;
    align-self: start;
}
.recipe_block_description {
    font-size: 14px;
    align-self: start;
}
.recipe_steps {
    font-size: 14px;
    color: rgba(30,33,38,.7);
    align-self: end;
}
.recipe_button {
    margin: 10px auto 0;
    padding: 8px 0;
    display: block;
    color: #fff !important;
    background-color: #1e2126 !important;
    text-decoration: none;
    border-radius: 6px;
    align-self: end;
    width: 100%;
    transition: background-color 0.3s;
}
.recipe_button:hover {
    text-decoration: none;
    background-color: #0f1013 !important;
}
</style>