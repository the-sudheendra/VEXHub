# VEXtension Repository

This repository serves as a central hub for storing **checklists** and **prompts** for **[VEXtenstion](https://github.com/the-sudheendra/VEXtenstion)** in JSON format. This allows for easy management and sharing across various projects and teams.

---

#### [Checklist Schema Explanation](https://github.com/the-sudheendra/VEXHub/blob/main/Checklist/ChecklistSchema.md)
#### Example
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
  ```
---
#### [PromptTemplate Schema Explanation](https://github.com/the-sudheendra/VEXHub/blob/main/AviatorPrompts/AviatorPromptsTemplateSchema.md)
#### Example

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
