# zeotap
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
