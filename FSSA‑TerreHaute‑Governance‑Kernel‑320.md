{
  "governance_kernel": {
    "core_logic": {
      "rule_engine": "deterministic",
      "execution_order": [
        "intake_rules",
        "eligibility_rules",
        "disability_rules",
        "employment_rules",
        "routing_rules",
        "closure_rules"
      ],
      "consistency_checks": ["schema_match", "priority_alignment", "timestamp_integrity"]
    },
    "decision_paths": {
      "standard": {
        "flow": ["INTAKE", "ELIGIBILITY", "DISABILITY_SERVICES", "EMPLOYMENT_SUPPORT", "ROUTING", "CASE_MANAGEMENT", "CLOSURE"],
        "lucr_required": true
      },
      "accelerated": {
        "flow": ["INTAKE", "ELIGIBILITY", "ROUTING", "CASE_MANAGEMENT"],
        "conditions": ["high_priority", "resource_availability"],
        "lucr_required": true
      },
      "crisis": {
        "flow": ["INTAKE", "ROUTING", "CASE_MANAGEMENT"],
        "override_points": ["INTAKE", "ROUTING"],
        "strictness": "maximum"
      }
    },
    "compliance_gates": {
      "lucr_alignment": ["INTAKE", "ELIGIBILITY", "ROUTING", "CLOSURE"],
      "audit_points": ["rule_execution", "override_logging", "data_integrity"]
    },
    "crisis_mode": {
      "enabled": true,
      "override_rules": ["priority_force_high", "worker_auto_assign", "enhanced_logging"],
      "required_fields": ["override_reason", "resource_allocation"]
    },
    "integration": {
      "event_bus": "connected",
      "notification_layer": "connected",
      "reporting_layer": "connected"
    }
  }
}
