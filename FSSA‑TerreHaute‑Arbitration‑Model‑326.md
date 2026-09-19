{
  "arbitration_model": {
    "dispute_types": {
      "data_conflict": {
        "description": "Mismatch between intake, eligibility, or disability data",
        "severity": "medium",
        "auto_escalate": false
      },
      "priority_conflict": {
        "description": "Disagreement on case priority level",
        "severity": "high",
        "auto_escalate": true
      },
      "resource_allocation": {
        "description": "Conflict over service or support resource distribution",
        "severity": "high",
        "auto_escalate": true
      },
      "override_dispute": {
        "description": "Challenge to a supervisor or director override",
        "severity": "critical",
        "auto_escalate": true
      }
    },
    "resolution_paths": {
      "standard": {
        "steps": [
          "worker_review",
          "supervisor_review",
          "division_manager_review"
        ],
        "lucr_required": true
      },
      "accelerated": {
        "conditions": ["high_priority", "time_sensitive"],
        "steps": [
          "supervisor_review",
          "division_manager_review"
        ],
        "lucr_required": true
      },
      "crisis": {
        "conditions": ["public_safety_risk", "resource_overload"],
        "steps": [
          "routing_director_review",
          "governance_kernel_final_decision"
        ],
        "strictness": "maximum"
      }
    },
    "decision_rules": {
      "consistency_checks": ["data_integrity", "priority_alignment", "override_logging"],
      "required_fields": ["case_id", "dispute_type", "timestamp"]
    },
    "final_authority": {
      "standard": "division_manager",
      "accelerated": "division_manager",
      "crisis": "governance_kernel"
    },
    "lucr_alignment": {
      "checks": ["decision_consistency", "priority_integrity", "audit_logging"],
      "required_for": ["all_supervisors", "routing_director", "governance_kernel"]
    }
  }
}
