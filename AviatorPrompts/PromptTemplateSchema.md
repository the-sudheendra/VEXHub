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
