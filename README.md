# VEXtension Repository

This repository serves as a central hub for storing **checklists** and **prompts** for **[VEXtenstion](https://github.com/the-sudheendra/VEXtenstion)** in JSON format. This allows for easy management and sharing across various projects and teams.

---

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
    ### Checklist Schema Example
    ```json
    {
      "Defect": {
        "categories": {
          "Reproduction": {
            "checklist": [
              "Steps to reproduce the issue are clearly documented",
              "Actual vs expected behavior is described",
              "Screenshots or logs are attached, if applicable"
            ],
            "phases": ["New", "In Progress"]
          },
          "Resolution": {
            "checklist": [
              "Root cause analysis is documented",
              "Solution has been tested and verified",
              "All relevant stakeholders are informed of the fix",
              "Test cases are updated to cover the issue"
            ],
            "phases": ["Done", "Resolved"]
          }
        }
      },
      "Spike": {
        "categories": {
          "Planning": {
            "checklist": [
              "Objective of the spike is clearly defined",
              "Expected deliverables are documented",
              "Team has agreed on a timebox for the spike"
            ],
            "phases": ["New", "In Progress"]
          },
          "Analysis": {
            "checklist": [
              "Relevant research and findings are documented",
              "Any discovered blockers or risks are noted",
              "Recommendations or next steps are provided"
            ],
            "phases": ["Done", "Resolved"]
          }
        }
      }
    }
  
---

## Aviator Prompts Template Schema

### Root Level

- **Array of prompt Template Objects**  
  Each object in the array represents a reusable template for generating content related to a ticket or work item.

  ### Template Object Properties
  
  #### **`name`**
  - **Type:** `string`
  - **Description:**  
    A short, descriptive label for the template.  
    **Example:** `"Summarize Ticket for Standup"`
  
  #### **`description`**
  - **Type:** `string`
  - **Description:**  
    Explains the purpose and function of the template.  
    **Example:** `"Generate a concise summary of the ticket suitable for a daily standup update."`
  
  #### **`template`**
  - **Type:** `string`
  - **Description:**  
    The text template containing placeholders (e.g., `{{title}}`, `{{description}}`) that will be filled with actual ticket data.
    #### **`variables`**
    - **Type:** `array` of objects
    - **Description:**  
    Lists all variables required by the template. Each variable object includes:
    - **`name`**: The variable’s identifier, matching a placeholder in the template.
    - **`selector`**: The Dom selector used to extract the variable’s value from the ValueEdge page.
  
### Aviator Prompts Template Example

```json
[
  {
    "name": "Summarize Ticket for Standup",
    "description": "Generate a concise summary of the ticket suitable for a daily standup update.",
    "template": "Create a 2-3 sentence summary of this ticket that I can share during standup. Include current status, any blockers, and what I'm working on next:\nTitle: {{title}}\nDescription: {{description}}\nStatus: {{status}}",
    "variables": [
      {
        "name": "title",
        "selector": ".entity-form-document-view-header-name-field-container"
      },
      {
        "name": "description",
        "selector": "[aria-label='Description textbox']"
      },
      {
        "name": "status",
        "selector": "[data-aid='entity-life-cycle-widget-phase']"
      }
    ]
  },
  {
    "name": "Generate Tasks for current ticket",
    "description": "Break down the current ticket into actionable tasks, each with a title, description, and estimated time.",
    "template": "Based on the following ticket, generate a list of development tasks. For each task, include:\n1. Task Title\n2. Task Description (1-2 sentences)\n3. Time Estimation (in hours)\n\nTicket Title: {{title}}\nTicket Description: {{description}}",
    "variables": [
      {
        "name": "title",
        "selector": ".entity-form-document-view-header-name-field-container"
      },
      {
        "name": "description",
        "selector": "[aria-label='Description textbox']"
      }
    ]
  }
]
```

---
❤️ We welcome contributions to expand and refine the collection of checklists and promps 😊
