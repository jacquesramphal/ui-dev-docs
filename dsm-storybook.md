## What is DSM?
Design System Manager, or DSM is a feature built into the Craft plugin, that makes it easy to access, document, and evolve your design system from sketch
A DSM library is a grouping of documentation and patterns for a given product or set of products.

[See Example Library](https://dsmexample.invisionapp.com/dsm/in-vision-dsm/example-library)

## Resources
### Getting Started
[DSM Walkthrough](https://www.invisionapp.com/inside-design/design-system-manager-walkthrough/)<br>
[DSM](https://www.invisionapp.com/design-system-manager)<br>
[Getting Started with Live Components](https://support.invisionapp.com/hc/en-us/articles/360028509991)<br>
[Comprehensive Guide to Design Systems](https://www.invisionapp.com/inside-design/guide-to-design-systems/)<br>
[Introduction to DSM](https://support.invisionapp.com/hc/en-us/articles/115005685166)<br>
[What Are Live Components?](https://support.invisionapp.com/hc/en-us/articles/115005685166)<br>
### Storybook
[Configuring Storybook](https://support.invisionapp.com/hc/en-us/articles/360028510211-Configuring-the-Storybook-DSM-Integration)<br>
[Storybook Tutorial](https://www.learnstorybook.com/)<br>
### Workflow & Collaboration
[Managing Roles and Permissions](https://www.invisionapp.com/design-system-manager/learn/adding-removing-people-roles-permissions)<br>
[Integrating Jira with Invision Cloud](https://support.invisionapp.com/hc/en-us/articles/213306066-Integrating-InVision-with-Jira-Cloud)<br>
[How to Test Your Design System](https://www.invisionapp.com/inside-design/storybook-excerpt/?utm_campaign=Weekly%20Digest&utm_source=hs_email&utm_medium=email&utm_content=77757586&_hsenc=p2ANqtz-8GpNyEJF6ZrnLf7jz4vGanGpigyU_lvI7sXJ1_dn_o-8JYRBzBEtLdPyb8HqeoiRfX7Ke7w4F8XXkwSJgSRfGRpGed-g&_hsmi=77860449)<br>
[Design Systems for Developers](https://www.learnstorybook.com/design-systems-for-developers/?utm_campaign=storybook-inv-promo&utm_source=hs_email&utm_medium=email&utm_content=77578436&_hsenc=p2ANqtz-9oW5R8oxI-nGsL1JC7HOLYxO2dQHMamrV7e5ljtg8FTVBzlF-xU_uB-42zCV7VIvYcRy-e2uekazjcMOzMYE3TP29wjw&_hsmi=77581262)<br>
[Versioning DSM Live Components](https://support.invisionapp.com/hc/en-us/articles/360033358051)<br>
[How to sync designer-developer tools for easy collaboration](https://www.invisionapp.com/inside-design/syncing-inspect-jira/?itm_campaign=default&itm_source=homefeatured&itm_medium=website&itm_content=default)<br>
### React
[React For Designers](https://reactfordesigners.com/)<br>

---
## What are Live Components?
DSM Live Components are interactive coded components that you can embed in your design system to create a single source of truth for your product teams across design and development.
The embedded code is built directly from your code component library and is showcased via an integration with the popular component development framework Storybook.

[Read more](https://support.invisionapp.com/hc/en-us/articles/360028214732)

---
## Getting Started with Live Components
Before creating live components, there are a few things you’ll need:
1. **A code component library**. DSM currently supports live components implemented in React, Vue, Angular, and HTML. Soon support will be added for even more popular frameworks. Need help thinking through your design system implementation? Check out our expert advice page.
1. **Familiarity with Storybook**. Storybook is a development environment for UI components. DSM integrates with Storybook to bring interactive components directly into your DSM library. If you’re not familiar with Storybook, here’s a great tutorial to get you started.
1. **Familiarity with a development environment and NPM**. You can always add people for the task to your DSM organization.
1. **Access to the DSM Sketch tool.** You’ll need to create a component container with the DSM Sketch tool. This enables DSM to embed the live component in its proper place.
1. Admin or editor access in the DSM organization. To learn more about DSM roles, check out this article: Roles and Permissions in DSM

[Read more](https://support.invisionapp.com/hc/en-us/articles/360028509991)

---
# Configuring Live Components
Adding live components to DSM consists of 4 steps:

## 0. Asset Creation

https://www.invisionapp.com/inside-design/guide-to-design-systems/

* Establish a simple naming convention to allow for scalability and improve communication
* Use a logical naming convention for your pages and symbols
> Eg. Atomic Design naming conventions: control/definingproperty-state
* sometimes overly nested designs will break in practice so be intentional when creating atomic symbols
* Leverage native features and plugins to make symbols dynamic
* When creating symbols Size like symbols consistently and they will be available as overrides


## 1. Configuring the Storybook DSM integration (a one-time setup)
https://support.invisionapp.com/hc/en-us/articles/360028510211-Configuring-the-Storybook-DSM-Integration

### Installing Storybook
the DSM Live Components feature requires that you first create a Storybook story for the component you want to embed in DSM.

> If you're using Storybook v4, the Live Components feature supports version 4.0.0 and later. If you're using Storybook v5, the Live Components feature supports version 5.1.1 and later.

### Installing the DSM CLI
First, you will need to install the DSM command-line interface (CLI) in your project. In your development environment, run the following command:
`npm install @invisionapp/dsm-storybook`

### Peer dependencies
Before configuring Storybook with DSM, there are a few peer dependencies you will need to install:

`@storybook/addon-options`<br>
`@storybook/addons`

### Adding CLI shortcuts
Optionally, you can create CLI shortcuts to more easily publish and preview live components in the future. Add the following CLI shortcuts to the scripts section of the package.json file of your Storybook component library project:

`"scripts": {
  "dsm-storybook:publish": "dsm-storybook publish",
  "dsm-storybook:preview": "dsm-storybook preview"
}`

### Adding a DSM configuration file
To obtain the code for the `.dsmrc` configuration file:

1. Open your library in the DSM web view.
1. At the top right of the page, click the code icon **(</>)** and select **Live components setup**.
1. Scroll to **Integration details** and, next to **DSM configuration file**, click **Open**.
1. Copy the code and add it to a `.dsmrc` configuration file in your Storybook component library project.
1. Place the .dsmrc configuration file in the root of your Storybook component library project. The root of the project is the same folder where the package.json file lives.

> You’ll notice that in the code, there is a placeholder for an authentication token. The section “Generating an authentication token” covers how to generate a token for your `.dsmrc` file.

<!-- ![adding-dsmrc-file](https://support.invisionapp.com/hc/article_attachments/360029788032/obtain-dsm-configuration-file.gif) -->

---
## 2. Adding a component container via the DSM Sketch tool
To create a component container:

1. In Sketch, open the DSM Sketch tool.
2. If you already have symbols uploaded to your DSM library, select the symbols you’d like to include in the new component.
3. Right-click and choose **Create a Component**.

https://support.invisionapp.com/hc/en-us/articles/360028385992

## 3. Adding a code tab in the DSM web view
After creating a component in Sketch, you will need to add a code tab to the component in the DSM web view.

To add a code tab:

1. In the Sketch DSM tool, select the appropriate component
1. In the right panel, click the Open in web icon (open-in-web-icon.png).
1. dsm-open-component-in-web.png
1. In the DSM web view, to the right of the Links tab, click Add tab.
1. Under the Code section, click the appropriate framework (React, Vue, Angular, or HTML).

---
## 4. Publishing Storybook to DSM
https://support.invisionapp.com/hc/en-us/articles/360028388192

---
## 5. Invision plugin installed on Jira
