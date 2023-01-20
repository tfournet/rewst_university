## Training Session 1
In this session, we will learn about: 

- Actions
- Transitions
- Data Aliases
- Forms
- Triggers
- Viewing Results


### Starting Off in the Workflow Builder

_We will create a new workflow for adding and removing Azure Active Directory users to groups. This will be a form to choose the user and group with a workflow to complete the task. Have the user share their screen / browser and guide them through all of the steps._

* Open up the Workflows tab in Rewst, and create a new workflow named "Add User to Group" or whatever they like.
* Talk about the Canvas: This is where workflow actions live. Workflow actions are listed on the left side of the screen. Each integration they have installed comes with a collection of actions, as well as built-in ones provided by Rewst. Any Workflows that are already built are also listed as possible actions, so that they can become sub-workflows of a larger workflow. 
* Find the **Microsoft Graph** integration section, and drag the **Add Group Member** action to the canvas.
* Click into the Action
  * Starting at the top, go through each field: 
    * Task Name: This can be whatever they want. It's recommended to keep with the snake_case naming convention, but anything here is technically valid. 
    * Description: This is just for documentation purposes, this has no technical effects.
    * Publish Results As: This will create a variable (in Rewst we also refer to this as a _Data Alias_ ) from the output of the action.
    * Parameters: These are the inputs for the action. In the case of *Add Group Member*, we need to supply a *User ID* and a *Group ID*. Have the user click the Refresh buttons and see that the drop-downs will pull live data from Microsoft to list users and groups.
  * Show Task Transitions
    * These are the small rectangles below the "main" part of the task. 
    * 
