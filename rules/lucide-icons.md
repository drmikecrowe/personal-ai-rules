# Lucide-React Icon Validation via Memory Bank
- Last Updated: 2025-08-30
- Description: Lucide React icon usage and conventions
- Tags: react icons
- Version: 1.0


**Purpose:**  
Prevent the use of non-existent or misspelled Lucide React icons by requiring the LLM to check the authoritative icon list in the memory bank before generating or suggesting icon imports/usages.


**Rationale:**  
This ensures all icon usages are valid, prevents runtime errors, and maintains consistency with the project's icon set.


**How to apply:**  
Add this rule to your LLM prompt context or ruleset. When coding, the LLM will always cross-reference the icon list before suggesting or generating icon code.

- Verify icons against `memory-bank/reference/api_docs/lucide-react/0/llms-icons.md` before using or suggesting them.
- If missing, suggest a valid alternative or ask the user to choose from the list.

