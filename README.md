# Checklists Repository

This repository serves as a central hub for storing Definition of Done (DoD) checklists for **[VE Checklist](https://github.com/the-sudheendra/VE-Checklist/#)** in JSON format. This allows for easy management and sharing across various projects and teams.

Example Checklist
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
## Properties Explanation
Value-Edge Work Item Types
The root-level keys (e.g. "Defect", "Spike", "User Story", "Epic") represent different types of work items.

### Categories
Logical groupings of related checklist items within a work item type. Categories help organize checklist items based on purpose or workflow stage.

### Checklist
An array of strings representing specific actions or requirements that must be completed for a given category.

### Phases
Workflow stages during which the checklist applies. This maps checklist categories to relevant stages in the item’s lifecycle.

❤️ We welcome contributions to expand and refine the collection of DoD checklists 😊
