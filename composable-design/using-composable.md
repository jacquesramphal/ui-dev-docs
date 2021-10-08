## **Layouts/features included in Composable (at a high-level):**

- Homepage
- Navigation
- PRP
- Barebones Single SKU PDP
- Cart Drawer
- Authentication flows (login-create account only)
- Editorial templates
- Search

The components that Composable is based off of comes from the Harry Rosen site.

The Deploy team has supported the Product team in creating 
components for things like an immersive PDP but has not made it into the
 core Composable product. They’re currently waiting for things to be 
reviewed by the product team. [Jacques Ramphal](mailto:jacques.r@myplanet.com) **change request form / process.**

## **Toolchain**

There’s no specific tools you have to use as long as it 
gets the job done. Some folks use Webflow or LucidChart for Deploy 
projects. If you are experimenting with new tools, be sure that it’s 
approved by IT/Tim. There are some restrictions around using Figma in 
client-facing projects so be sure you adhere to those guidelines and 
ensure design/dev handoff is still possible if deciding to move forward 
with Figma (note: Deploy team developers don’t have access to Figma).

## **Component Mapping/Gap Analysis**

This exercise helps us understand what requirements can be 
fulfilled with Composable. You can use their existing product/designs to
 get a baseline of what is required if there are no concrete 
requirements collected.

You can reference this spreadsheet Lisa put together for House Key: [https://docs.google.com/spreadsheets/d/1WME8Bns_xhZVpaAROCHcdPRcud1ZGDeKUSj4hqn_tuo/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1WME8Bns_xhZVpaAROCHcdPRcud1ZGDeKUSj4hqn_tuo/edit?usp=sharing)

A leaner version can be found here: [[Figma Link](https://www.figma.com/file/pDI1pyn9hszJcDEcIdK03N?node-id=1019%3A0&fuid=907717025334482707#99147788)] [[Miro](https://miro.com/app/board/o9J_l5IibKc=/)]. You’ll first need access to Figma.

## **Styling Components (in Sketch)**

When setting up files for a new project, you’ll have to (at
 the very least) start by the Active Style Library and adjust the 
colours + typography primitives and tokens. Be sure to fill out the 
specifications for each token sheet after making your changes as 
developers will be setting up their library as you work on the various 
page designs.

The Base Component Library doesn’t contain all components 
in the core product so pull in what you need and add to the file. When 
doing so, consider optimizing the symbol for other Deploy members to 
edit the file as needed. Try to use the same naming conventions.

For Figma styling, Jacques has a [Notion document with Figma steps here](https://www.notion.so/DESIGNER-ONBOARDING-NOTES-34ce3e7a22724021b81a8a584d6b4cb6).

## **Icons**

Composable has been leveraging [Ionicons](https://ionic.io/ionicons) for utility icons. Try to continue using this icon framework unless it’s absolutely critical to deviate.