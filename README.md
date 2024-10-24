# zeotap
Project Overview
This project is a simple 3-tier rule engine application that determines user eligibility based on attributes such as age, department, income, spend, etc. The system uses an Abstract Syntax Tree (AST) to represent conditional rules and allows for dynamic creation, combination, and modification of these rules.

Features
Dynamic Rule Creation: Create rules using a string and convert them into an AST.
Rule Combination: Combine multiple rules into a single AST for complex logic.
Rule Evaluation: Evaluate the rules against user data and determine eligibility.
Error Handling: Handles invalid rules and malformed data inputs.
Extendable: The system can be extended with user-defined functions and additional rule types.
Architecture
The project is divided into three key layers:

UI Layer: A simple interface where users can input rules.
API Layer: Exposes endpoints to create, combine, and evaluate rules.
Backend Layer: Manages data storage and processing of rules.
Data Structure
The AST is represented by a Node class that contains the following attributes:

type: A string representing the node type (e.g., 'operator' for AND/OR, 'operand' for conditions).
left: A reference to the left child node (used for operators).
right: A reference to the right child node (used for operators).
value: The actual condition for operand nodes (e.g., ("age", ">", 30)).

{
  "type": "AND",
  "left": {
    "type": "OR",
    "left": {
      "type": "AND",
      "left": {"type": "operand", "value": {"attribute": "age", "operator": ">", "value": 30}},
      "right": {"type": "operand", "value": {"attribute": "department", "operator": "=", "value": "Sales"}}
    },
    "right": {
      "type": "AND",
      "left": {"type": "operand", "value": {"attribute": "age", "operator": "<", "value": 25}},
      "right": {"type": "operand", "value": {"attribute": "department", "operator": "=", "value": "Marketing"}}
    }
  },
  "right": {
    "type": "OR",
    "left": {"type": "operand", "value": {"attribute": "salary", "operator": ">", "value": 50000}},
    "right": {"type": "operand", "value": {"attribute": "experience", "operator": ">", "value": 5}}
  }
}
