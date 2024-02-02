
# 
# Understand the deployment process

The **Deployment Pipeline** tool enables users to manage the development lifecycle of content within their tenant. The feature is available within the Power BI Service with a Premium Capacity license.

Pipelines enable a continuous integration/continuous deployment (CI/CD) approach that ensures content is updated, well-tested, and regularly refreshed as needed.
Pipelines are an efficient and durable way to automate the movement of content (reports, paginated reports, dashboards, datasets, and dataflows) through the development, test, and production stages of the content development lifecycle:

- **Development** â design, review, and revise content in a development workspace.
	- Engage other creators on new content
	- Use minimal datasets. When itâs ready to be tested and reviewed, deploy the content to the test stage.
- **Test** â test and verify that the content is accurate in this preproduction workspace.
	- Share content with testers and reviewers
	- Load and run tests with larger volumes of data
	- Test your app to see how it will look for your end users. When itâs ready to be distributed to your users, deploy the content to the production stage.
- **Production** â the workspace content has been tested and is ready to be consumed by your users either in an app or by access to the production workspace.
	- Share the final version of your content with business users across the organization

## 
# Workflow

A workflow view is helpful to review.

> 
> [![Diagram representing workflow of deployment from development to test then production and Developer/Creators participation in each stage.](media/deployment-workflow.png)](media/deployment-workflow.png#lightbox)
> 
> 
> 

There are few key items to note about the above graphic:

- The content (workspace) can be different in each stage above. For example:
	- In this example, the data source size (table and data icons) is increased as it gets closer to production. However, itâs possible that between the development and test stages, the dataset could be made smaller to accommodate testing.
	- The reports (chart icon) change in each stage.
- Other creators and developers can work on stages separately.
- The pipeline is either built out of three workspaces that were created when the Deploy button was clicked for the first time, or by assigning a different workspace to each stage.
	- As a result, each of the three workspaces is an independent workspace, a standalone one, which can be managed as such in any workspace aspect (permissions, content, etc.)
	- By deploying a source stage to the target stage, the selected sourceâs content (specific dataset, reports or all items) overrides the equivalent one on the target workspace (stage).



