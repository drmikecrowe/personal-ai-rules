# React Component Architecture - Zero Mapping Logic
- Last Updated: 2025-08-30
- Description: Keeping business logic for data transformation out of React components.
- Tags: react effect
- Version: 1.0


- Components MUST NOT contain business logic for mapping or transforming data.
- Data transformation and mapping should be handled in the `Effect` service layer before being passed to the UI or sent to a state machine.
