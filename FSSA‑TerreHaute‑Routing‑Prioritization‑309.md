{
  "routing_prioritization": {
    "priority_levels": ["low", "medium", "high", "critical"],
    "scoring": {
      "income_risk": 25,
      "health_risk": 30,
      "disability_need": 20,
      "employment_gap": 15,
      "crisis_trigger": 50
    },
    "calculation": {
      "formula": "sum(scores) + crisis_bonus",
      "crisis_bonus": {
        "enabled": true,
        "value": 40
      }
    },
    "assignment": {
      "mode": "deterministic",
      "worker_selection": "highest_capacity",
      "override": "crisis_mode"
    },
    "token_hooks": ["LUCR_priority_compliance"]
  }
}
