
# 
# Assign a workspace

After creating a pipeline, you need to add the content you want to manage to the pipeline. Adding content to the pipeline is done by assigning a workspace with the content (reports, paginated reports, dashboards, datasets, and dataflows) to the pipeline stage. You can assign a workspace to any stage, however, for this instruction we will start with assigning the workspace to the Development stage, and from there deploy some or all of the workspace items to Test and Production.

Note

Not only can you assign a workspace to any stage, you can assign different workspaces to different stages, although there is a limitation of one workspace per stage.

## 
# Create a Premium workspace

Ensure you have a Premium workspace created already to ensure this workspace can be used to create a pipeline. Choosing one of the premium license modes will enable this.

[![Screenshot highlighting License mode selected as Premium per user in creation of workspace.](media/create-workspace.png)](media/create-workspace.png#lightbox)

Once created, these workspaces are denoted by the diamond icon appearing on them.

[![Screenshot highlighting Diamond icon appearing on page that denote workspaces.](media/diamond-icon-workspace.png)](media/diamond-icon-workspace.png#lightbox)

## 
# Assign a workspace to a stage

To assign a workspace to a pipeline stage, follow these steps:

1. Open the pipeline.

[![Screenshot highlighting Sales and Marketing workspace in Deployment pipelines. ](media/deployment-pipelines.png)](media/deployment-pipelines.png#lightbox)
2. In the stage to which you want to assign a workspace, expand the dropdown titled **Choose a workspace to assign to this stage**. Again, it is most common to start with the Development stage.

[![Screenshot highlighting to choose a workspace to assign to this stage and select workspace.](media/choose-workpace.png)](media/choose-workpace.png#lightbox)

Note

To assign a workspace to a pipeline, the pipeline stage you want to assign the workspace to has to be empty.

3. From the dropdown menu, select the workspace you want to assign to this stage.

[![Screenshot highlighting dropdown for choosing a workspace that you want to assign to the current state.](media/workspace-dropdown.png)](media/workspace-dropdown.png#lightbox)

Note

On the drop-down list, the user will only see premium capacity workspaces 1) that are not assigned to any other pipeline, 2) where the user is their admin, and 3) where the user is a member of their adjacent stages.

4. Select **Assign a workspace**.

[![Screenshot highlighting Assign a workspace option after selecting workspace in current stage.](media/assign-workspace.png)](media/assign-workspace.png#lightbox)



