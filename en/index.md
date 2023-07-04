<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 50px;
}
.grid-item {
  display: flex;
  flex-direction: column;
}
h2 {
  padding-top: 32px !important;
  margin-top: 0 !important;
}
h3 {
  padding-top: 16px !important;
  margin-top: 0 !important;
}
</style>

# Toloka documentation

[Toloka]({{ toloka }}) lets you use crowdsourcing to analyze large volumes of data in a short time. You can ask users to group the wide variety of items in your online store into categories, find or verify information, translate texts, and much more.

<div class="grid-container">
    <div class="grid-item">
        <h2>Getting started</h2>
        <p><a href="guide/concepts/overview">How does Toloka work?</a></p>
        <p><a href="guide/concepts/unwanted">What tasks can't be placed in Toloka?</a></p>
        <p><a href="guide/concepts/access">Registration</a></p>
        <p><a href="guide/concepts/first-project">Your first project</a></p>
        <p><a href="guide/concepts/data-security">Data security</a></p>
    </div>
    <div class="grid-item">
        <h2>Tutorials</h2>
        <p><a href="guide/tutorials/image-classification">Images</a></p>
        <p><a href="guide/tutorials/video-moderation">Video</a></p>
        <p><a href="guide/tutorials/transcript-audio">Audio</a></p>
        <p><a href="guide/tutorials/content-moderation">Texts</a></p>
        <p><a href="guide/tutorials/internet-search">Data enrichment</a></p>
        <p><a href="guide/tutorials/questionnaire-toloka">Surveys</a></p>
        <p><a href="guide/tutorials/walk">Field tasks</a></p>
    </div>
    <div class="grid-item">
        <h2>Projects</h2>
        <p><a href="guide/concepts/project">Create projects</a></p>
        <p><a href="guide/concepts/pool-main">Manage pools</a></p>
        <p><a href="guide/concepts/task_upload">Post tasks</a></p>
        <p><a href="guide/concepts/result-of-eval">Get results</a></p>
    </div>
    <div class="grid-item">
        <h2>Task interface</h2>
        <p><a href="template-builder/">Template Builder</a></p>
        <p><a href="guide/concepts/spec">HTML/JS/CSS editor</a></p>
        <p></p>
        <h2>Toloka settings</h2>
        <p><a href="guide/concepts/users">Users</a></p>
        <p><a href="guide/concepts/nav">Skills</a></p>
        <p><a href="guide/concepts/budget">Profile</a></p>
    </div>
    <div class="grid-item">
        <h2>Tips and recommendations</h2>
        <p><a href="guide/concepts/sandbox">Sandbox</a></p>
        <p><a href="guide/concepts/cloud-storage">Data storage</a></p>
        <p><a href="guide/concepts/control">Quality control rules</a></p>
        <p><a href="guide/concepts/train">Training Tolokers</a></p>
    </div>
    <div class="grid-item">
        <h2>Troubleshooting and support</h2>
        <p><a href="guide/concepts/frequent-customer-errors">Common requesters' mistakes</a></p>
        <p><a href="guide/troubleshooting/troubleshooting">All questions on one page</a></p>
        <p><a href="glossary">Glossary</a></p>
        <p><a href="guide/troubleshooting/support">Support</a></p>
    </div>
</div>

## For developers

<div class="grid-container">
    <div class="grid-item">
        <h3>REST API</h3>
        <p><a href="https://toloka.ai/docs/api/api-reference/">Toloka API</a></p>
        <p><a href="https://toloka.ai/docs/api/apps-reference/">Apps API</a></p>
    </div>
    <div class="grid-item">
        <h3>Python SDK</h3>
        <p><a href="toloka-kit/">Toloka-Kit</a></p>
        <p><a href="crowd-kit/">Crowd-Kit</a></p>
    </div>
</div>

{% include [global-community](./_includes/global-community.md) %}

{% include [social-media](./_includes/social-media.md) %}