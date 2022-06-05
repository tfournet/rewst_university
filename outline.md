### Introduction
_Audience: MSP Owners, managers, technicians, and consultants_
##### What is Rewst?
Rewst is a Robotics Process Automation built for the MSP Industry. Rewst aims to bring enterprise-level automation capabilities to organizations service small to medium-sized business.
##### Who is Rewst?
Rewst was founded by the founders of Perch Security, which brought SIEM and SOC services to the MSP space. It has also been joined by other veterans of the space including former MSP managers, automation engineers, and developers. 
###### What is Robotic Process Automation?
RPA is an industry term for software that is built to automate tasks, often interfacing between multiple applications in complex ways. Automation aims to save time, reduce error, and increase operational securty by reducing the amount of tools that workers need to interface with to perform tasks. 

Automation tasks are built using a graphical environment with little or no actual "coding" required. This is often referred to as _Low-Code / No-Code_ programming.
###### Is Rewst an RMM?
RMMs, Remote Monitoring and Management platforms, are designed for endpoint managment in an MSP environment, often providing automation capabilities for servers, workstations, and mobile devices. Rewst's automations are built to target automation between environments, often interfacing with RMMs in order to run tasks on endpoints. Rewst is not built to be an RMM, but can interface with RMMs to make use of, or augment their functions. 
###### What makes Rewst platform suitable for Managed Service Providers? 
Rewst was built with MSPs as the core use case. This means the application is natively multi-organization and multi-tenant, and integrates directly with the tools that Managed Service Providers use. Automations are built in Rewst to target multiple clients without needing to be rebuilt or copied.

Rewst also understands the pressures and talent shortages that MSPs face. Because of this, we provide MSPs with ready-built automations for common use cases. Within the Rewst platform, MSPs can "install" these automations into their environments using natural language configuration, and we will continually build new autoamtions to enable business efficiency and security. In addition, Rewst's Robotic Operations Center (ROC) assists MSPs who are building their own automations.
###### What is the ROC?
Rewst's Robotics Operation Center is its group of automation engineers who support and assist MSP partners with their automations. The ROC can monitor existing workflows for success, provide support to workflow builders, and ensure success in using the platform. 
###### What Can I Automate with Rewst?
Rewst can automate activities with any application it can integrate with, provided that such application provides such capabilities over its **API**. An API is an _application programming interface_ which is a way of 
interacting with multiple different types of applications in a standardized way. 
###### What is Low-Code / No-Code development?
Developing in environments such as Rewst is done (usually) without writing large blocks of code. Tasks which represent an action within an application are placed onto a canvas where they are linked together to provide the workings of an automated process. Where necessary, small blocks of code can be used to perform data transformations or other functions. Examples of this include reformatting text fields, or doing math or data comparisons.
### Rewst Overview
##### Integrations
Integrations are how Rewst makes connections with external applications. Rewst integrates natively with the most common applications that MSPs use, such as PSAs, RMMs, Microsoft, and other documentation and security tools. 

When Rewst builds an integration with another product, we build Actions for that application that match with the capabilities of the API they provide. For exampke, the ability to create a user account in an application would be symbolized by a `Create User` action in Rewst for that operation. A workflow developer would drag that action onto the canvas, and then entering data into the required fields, such as `username`, `password`, `email address`, etc. 

Setting up an integration largely depends on how it's configured within the third party's application settings. Typically this involves creating API keys, OAuth connections, or other means of authentication, along with service-specific URL information and permissions setup. 
##### Workflows
Workflows are the main "engine" of Rewst automations. This is where automation actions are brought onto a canvas, linked together, and configured to operate together towards the goal of a completely automated process. Workflows take inputs, create outputs, and are configured with triggering conditions so they know when and how to run. 

Within the workflow editor, we have Actions, which represent singular activities that we do within the platform or against integrated applications, transitions _from_ those actions that can be configured dependent upon the results of those actions, and transitions into other actions represented by arrows to depict the next steps in a flow. Workflows can branch to different sections of themselves based on results or conditions, and branches can either run separately or in parallel. 

The Rewst workflow editor has several features and functions that will be discussed in detail in this series. Some important points to note are that workflows can be called by other workflows (as "sub-workflows") and that they can built to be extremely simple or extremely powerful. Just like a program or script, they can vary in scope and complexity.
##### Forms
Forms provide an easy way to kick off a workflow for a technician or even an end-user. Rewst forms are similar to forms you would see in other applications, with the distinction that they have access to the power of the rest of the Rewst platform. Forms can use Integrations to query live data from external applications, or even use embedded workflows to take complex sets of data and present them to the user to make choices that reflect live, dynamic environments. For example, a Rewst form could be built to present a list of _User accounts with Exchange Online mailboxes of a size larger than `[__]` Gigabytes_, and then allow the form submitter to select certain accounts from that list to perform some activities. 
##### Templates
When building workflows, it is often necessary to include operations that would have some messaging component, such as an email, or a ticket body, or a chat message. Rewst has a Template system that allows the use of Markdown or HTML to build out messages that can be used and re-used in multiple instances or across multiple clients for communications. The Template system utilizes the same low-code / no-code programming capabilities so that they can be dynamic and customized to the cases they are used for. For example, an email greeing could being with "Dear `{{ CTX.first_name }}`," injecting the user's first name into the message.  
##### Scripts
Scripts are a special type of Template that are used to hold programming code for use in platforms where we might have the ability to run these. For example, a 'Script' may contain Microsoft PowerShell code that we would like to execute on a server to create a user account. The Scripts feature in Rewst includes a source code editor with syntax highlighting so that scripts can easily be read and modified.
##### Crates
When Workflows, Forms, Templates, Scripts, and their associated configuration options are bundled all together, Rewst calls this a **Crate**. Crates are self-contained automations built to fulfill a certain purpose. When crates are built, they are packaged to be able to be used between completely different organizations within Rewst, and published in Rewst's _Crate Marketplace_. Crates in the marketplace are installed and configured by managing organizations (MSPs), specifying preferences and parameters to fit within that organization's infrastructure, standards, and practices. Over time, the Crate Marketplace will be expanded as the Robotics Operations Center builds more and more crates that enable MSP automation.

### Building With Rewst

_Audience: Advanced MSP Engineers, Automation engineers, or MSP Automation Consultants who have not extensively used Rewst. Previous experience automating processes with technologies such as PowerShell, RMMs, or enterprise tools will be useful._
##### Getting Started

###### Logging in
Access to the Rewst platform is from the main URL at https://app.rewst.io. Rewst uses Microsoft Azure AD as its authenticator, so your own Azure Active Directory log in will allow you into the platform. If you do not have access, either someone from your organization must invite your account, or you will need to be set up with Rewst. Contact us if you need help getting in.
###### Integration Setup
Working with Rewst starts with Integrations. These really need to be set up in order to unlock the power of automating processes that work between multiple systems. Configuring an integration is usually fairly simple: Choose the integration you want to configure, set up an API account within that application, and then provide the details in the Rewst Integrations page. 

Often these integrations will require permissions configuration. What these permissions should be configured to are usually completely up to the MSP. When we build an integration, we usually include every available function provided by its API into our workflow editor. Whether you want your workflow builders to have the ability to use these would be up to your own discretion. Typically a minimal set of permissions is required to successfully authenticate and test an integration within Rewst and then the rest is up to you.

Begin with setting up Integrations for your PSA, RMM, and Microsoft accounts. As an MSP and (typically) a Microsoft CSP (Cloud Service Provider), these are the foundational items. Later on, you can configure integrations with Cybersecurity tools, hardware and licensing vendors, documentation platforms, and more. 

###### Your first workflow
Let's start off by building a very simple example workflow that uses the Microsoft Graph integrations to list the members of a group in Azure Active Directory. This assumes that you have configured the _Microsoft Graph_ integration at least for your organization. 

Steps for the *List Group Members* Workflow:
1. Log into Rewst, click **Workflows** and press the `Create` button to create a new Workflow. 
2. Name the workflow `List Group Members` 
3. On the left-hand side of the screen, find the group of Actions for `Microsoft Graph` and find the `List Group Members` action. Drag that onto the workflow canvas.
4. Click on the action, and for the `Select` field, type in `displayName` and `id`. Press Enter after typing each of these in and they will add to the list of items to select.
5. For the Group ID, select a group (The integration should find all of the groups in your Azure Active Directory.).
6. Press the `Test` button at the top right corner of the editor. This will run the workflow in a test mode, displaying information about how it is executing on the screen. In the results, you should see under `results -> data -> value` an expandable list of user names and IDs which are members of that group.

This should illustrate a small example of the possibilities when creating a workflow. In a more complex scenario, we likely would have had first had steps to identify a group by its name or ID, and then we would pass that list onto another task to possibly perform some actions on its members. Rewst has functionality to iterate over or manipulate lists, which we will cover later.

###### Expanding into Forms and Templates
Forms can have options that are generated with real-time queries into infrastructure services. For queries that are more complicated or rely on previous selections, we can use workflow-generated options for forms. Let's explore how this can work:
1. Return to the `List Group Members` workflow. We are going to convert this workflow into an _Option Generator_ and we are going to make it accept a group identifier as an input. 
2. On the top-right of the screen, click the _Pencil_-shaped icon to edit the Workflow properties
3. Change the `Workflow Type` to `Option Generator`
4. Click the `+` icon next to `Input Configuration` and add a varialbe named `group_id`
5. Click Submit
6. In the workflow, find the `microsoft_graph_list_group_members` action you created earlier, click it and click the _code editor_ icon next to the `Group ID` field. 
7. Type in `{{ CTX.group_id }}` - You should notice the editor colorize and auto-complete as you type
8. Click `Close` and click `Publish` on the top right of the screen to save the changes
9. On the left navigation bar, click Forms, and then click the `+` icon to create a new form
10. Name the form `Email Group Member`
11. Drag a **Dropdown** field from the selector on the left to the main window where it says "Drop items here"
12. Click on the field, name the *Field Name* `group_id`, set the _Field Label_ to `Group` and click the slider for _Dynamic Options_ to turn that on. Select _Microsoft Graph_ for the Integration and _Security Groups_ for the Resource.
13. Drag another **Dropdown** to the window. This time set the _Field Name_ to `user_id` and _Field Label_ to User. Select _Dynamic Options_ but also select **Workflow Generated**. For the _Workflow_ select the `List Group Members` workflow we created earlier. Leave the _value_ at `id` but change the _Label Field_ to `displayName`. In the _Workflow Inputs_ field, select _Populate from Form Field_ and choose `group_id` from the selector.
14. Save the Form, then click the Templates link on the left navigation, and press `Create` to create a new template. 
15. Give the Template a Name, and some content. Let's start the template with "Dear `{{ CTX.givenName }}`, but enter any other words you'd like. Save the template when you're ready.
16. Go back to Workflows, and we will `Create` a new workflow named `Email User` which will perform the automation actions.
17. Click the Pencil icon on the top right to configure variables, and click the `+` to create an Input Configuration variable, and name that variable `user_id`. Click Submit to save, then Cancel to get back to the main editor window.
18. Find the Action named `Get User` under the _Microsoft Graph_ section in the Actions list, and drag that to the canvas.
19. Click the action, and edit the _User ID_ field by clicking the Code icon. Type in `{{ CTX.user_id }}` - Notice that the editor should auto-fill this based on you entering it as an input variable.
20. Find the `sendmail` action in the _Core_ section and drag it to the workflow editor canvas. Click the action to set the parameters for it.
21. For the **to** field, click the Code editor button, and in the editor type in `{{ TASKS.microsoft_graph_get_user.result.result.data.value.mail }}` -- Notice that the editor will autocomplete most of this for you
22. For the **message** field, choose the Template you created earlier. Enter whatever you like for the **subject** and **title** fields.
23. Draw a connecting arrow from dot below `Success` on the `microsoft_graph_get_user` action to the top of the `core_sendmail` action.
24. Create a Trigger by clicking the **Add Trigger** button on the top of the workflow editor screen.
    - Name: `Form Trigger`
    - Organizations: (choose your organization)
    - Trigger Type: choose `Core - Form Submission` from the drop-down list
    - Form: choose the `Email Group Member` form that you created earlier
26. Click the "Gear" icon next to the Form Trigger you created, and there will be a button to `View Form URLs` to see the URL for the form. Click this and click the URL to open the form.
27. 