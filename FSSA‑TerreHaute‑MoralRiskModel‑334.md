{
  "moral_risk_model": {
    "risk_vectors": {
      "priority_bias": {
        "description": "Unjustified priority elevation or suppression",
        "severity": "high",
        "auto_flag": true
      },
      "override_without_reason": {
        "description": "Supervisor or director override lacking justification",
        "severity": "critical",
        "auto_flag": true
      },
      "resource_inequity": {
        "description": "Uneven or unfair distribution of services or support",
        "severity": "medium",
        "auto_flag": false
      },
      "case_assignment_conflict": {
        "description": "Assignment influenced by personal, political, or external factors",
        "severity": "high",
        "auto_flag": true
      },
      "risk_impact_neglect": {
        "description": "Failure to consider downstream ethical or safety impacts",
        "severity": "critical",
        "auto_flag": true
      }
    },
    "moral_scoring": {
      "metrics": ["priority_bias", "override_without_reason", "resource_inequity", "case_assignment_conflict", "risk_impact_neglect"],
      "weights": {
        "priority_bias": 0.25,
        "override_without_reason": 0.3,
        "resource_inequity": 0.15,
        "case_assignment_conflict": 0.15,
        "risk_impact_neglect": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "detection_rules": {
      "checks": ["override_integrity", "priority_alignment", "resource_equity", "risk_impact_ethics"],
      "required_fields": ["case_id", "risk_type", "timestamp"]
    },
    "crisis_mode": {
      "enhanced_moral_checks": ["override_integrity", "resource_tracking", "risk_impact_ethics"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "ethical_impact"]
    },
    "outputs": {
      "moral_risk_report": {
        "fields": ["case_id", "moral_risk_score", "violations", "recommendations"],
        "routing": "reporting_layer"
      },
      "moral_risk_alert": {
        "fields": ["case_id", "risk_type", "severity"],
        "routing": "notification_layer"
      },
      "corrective_moral_action": {
        "fields": ["case_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_moral_risk_reviews"]
    }
  }
}
