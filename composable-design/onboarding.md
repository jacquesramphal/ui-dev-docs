*Adapted from DEV onboarding*

## Steps for self-serve onboarding (WIP)

1. Watch [tutorial videos](https://drive.google.com/drive/folders/108Dj5t0iDlPj624dcPBydBZjUtcmi7jN)
2. Get access to Composable ~~Repo~~ **Figma Design Repo (tim)**
3. Create up a new instance of the **Foundations and Design Patterns files**
4. Access [~~Composable Doc~~](https://composable-docs.netlify.app/) **Composable Design Docs →** 
5. Familiarize yourself with [Composable UI storybook](https://composable-ui.netlify.app/) *(delta between figma and storybook)*

Ask questions you may have in Composable [issue queue](https://github.com/myplanetdigital/composable/issues) or ask-composable channel

## Exercise

1. Clone the FOUNDATIONS and DESIGN PATTERNS files 
    1. **TBD - who is in charge of duplicating and making a new project folder? TIM?**
    2. duplicate project folder, rename files to be project specific
    3. test library connections are retained
    4. push an update to a component
    5. create a new component using base elements and name it using the naming conventions
    6. **review readme and install recommended plugins**
    7. 
    8. *TBD steps for resolving library conflicts, new features in figma should allow users to copy lib and retain connections.*
    9. *Reach out to Yvonne for help*
    10. **~~Styling Components (in Sketch)~~**
        
        ~~When setting up files for a new project, you’ll have to (at
         the very least) start by the Active Style Library and adjust the 
        colours + typography primitives and tokens. Be sure to fill out the 
        specifications for each token sheet after making your changes as 
        developers will be setting up their library as you work on the various 
        page designs.~~
        
        ~~The Base Component Library doesn’t contain all components 
        in the core product so pull in what you need and add to the file. When 
        doing so, consider optimizing the symbol for other Deploy members to 
        edit the file as needed. Try to use the same naming conventions.~~
        
        ***For Figma styling, Jacques has a [Notion document with Figma steps here](https://www.notion.so/DESIGNER-ONBOARDING-NOTES-34ce3e7a22724021b81a8a584d6b4cb6).***
        
        [https://www.youtube.com/watch?v=GQ2jztKpxLk](https://www.youtube.com/watch?v=GQ2jztKpxLk)
        
        - OLD FIGMA STEPS
            
            Goal:
            
            Designer will have a starter template DESIGN PATTERNS and FOUNDATIONS library to work from
            
            > Until we can effectively duplicate a template project and retain links from design patterns to foundations then we need a manual process for starting a new project and relinking instances
            > 
            
            1. Duplicate latest version of composable starter kit or a newer project instance to work from
                1. include foundations and design patterns
            2. Publish styles from new library
            3. Enable in new design file
            4. Using the DSOrganizer plugin, repeat this process for each tab (colours, type, layer styles, grids)
                1. From the new foundations file, DSO plugin and in the selected tab, highlight all styles,
                2. select SET AS TARGET from the options menu
                    
                    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/32d5ab2b-0b8d-4057-b0aa-eb2172abe091/Screen_Shot_2021-07-23_at_5.13.30_PM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/32d5ab2b-0b8d-4057-b0aa-eb2172abe091/Screen_Shot_2021-07-23_at_5.13.30_PM.png)
                    
                3. in the design patterns file, open the DSO plugin and in the applicable tab, select "relink styles" 
                4. relinking may take a few minutes
                5. delete local styles once you confirm instances are relinked to the foundations library
    
    1. (Use Composable
    Doc and ask-composable channel if you run into any blockers)
2. Replicate this [page](https://www.coravin.com/) within Starter Demo site
    1. ~~Update the theme to match the theme of the page (color, fonts)~~
    2. ~~Use variant, composable ui components, block to recreate the page.~~
    3. Assemble page using composable components.
    4. Test connection to new library files by making and publishing updates

Note: This is just an exercise, not a test. Do whatever you can with recreating the page even if it is just a few components.