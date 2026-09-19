{
  "ethics_engine": {
    "ethical_domains": {
      "fairness": {
        "checks": ["priority_bias_detection", "resource_distribution_balance"],
        "threshold": 0.95,
        "severity": "high"
      },
      "integrity": {
        "checks": ["data_truthfulness", "override_justification", "audit_consistency"],
        "threshold": 1.0,
        "severity": "critical"
      },
      "conflict_of_interest": {
        "checks": ["role_conflict", "case_assignment_conflict", "external_influence"],
        "threshold": 0.98,
        "severity": "high"
      },
      "respect_and_dignity": {
        "checks": ["communication_quality", "service_equity"],
        "threshold": 0.9,
        "severity": "medium"
      }
    },
    "ethical_scoring": {
      "metrics": ["fairness", "integrity", "conflict_of_interest", "respect_and_dignity"],
      "weights": {
        "fairness": 0.3,
        "integrity": 0.4,
        "conflict_of_interest": 0.2,
        "respect_and_dignity": 0.1
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "violation_detection": {
      "triggers": ["priority_bias", "override_without_reason", "resource_inequity"],
      "auto_flag": true,
      "severity_map": {
        "priority_bias": "high",
        "override_without_reason": "critical",
        "resource_inequity": "medium"
      }
    },
    "crisis_mode": {
      "enhanced_checks": ["override_integrity", "resource_equity", "risk_impact_ethics"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "ethical_impact"]
    },
    "outputs": {
      "ethics_report": {
        "fields": ["case_id", "ethical_score", "violations", "recommendations"],
        "routing": "reporting_layer"
      },
      "violation_alert": {
        "fields": ["case_id", "violation_type", "severity"],
        "routing": "notification_layer"
      },
      "corrective_ethics_action": {
        "fields": ["case_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_ethics_reviews"]
    }
  }
}
