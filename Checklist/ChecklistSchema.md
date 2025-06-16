## Checklist Schema
### Root Level: Work Item Types

  - **Type:** `object`
  - **Description:**  
    The root-level keys (e.g., `"Defect"`, `"Spike"`, `"User Story"`, `"Epic"`) represent different types of work items in your workflow.  
    Each key maps to an object describing the checklist structure for that work item type.
  
  ### `categories`
  
  - **Type:** `object`
  - **Description:**  
    Logical groupings of related checklist items within a work item type.  
    Categories help organize checklist items based on their purpose or workflow stage (e.g., `"Reproduction"`, `"Resolution"`).
  
    #### Category Object Properties
    
    ##### **`checklist`**
    - **Type:** `array` of strings
    - **Description:**  
      An array of specific actions or requirements that must be completed for a given category.  
      Each string is a checklist item (e.g., `"Steps to reproduce the issue are clearly documented"`).
    
    ##### **`phases`**
    - **Type:** `array` of strings
    - **Description:**  
      Workflow stages during which the checklist applies.  
      This maps checklist categories to relevant stages in the item’s lifecycle (e.g., `["New", "In Progress"]`).
