{
  "integrity_matrix": {
    "integrity_domains": {
      "data_integrity": {
        "checks": ["schema_validation", "timestamp_consistency", "cross_module_match"],
        "threshold": 0.99,
        "severity": "high"
      },
      "priority_integrity": {
        "checks": ["priority_alignment", "override_justification", "risk_score_match"],
        "threshold": 0.97,
        "severity": "critical"
      },
      "decision_integrity": {
        "checks": ["rule_path_consistency", "audit_alignment", "supervisor_signoff"],
        "threshold": 1.0,
        "severity": "critical"
      },
      "resource_integrity": {
        "checks": ["allocation_balance", "service_equity", "crisis_resource_tracking"],
        "threshold": 0.95,
        "severity": "high"
      }
    },
    "integrity_scoring": {
      "metrics": ["data_integrity", "priority_integrity", "decision_integrity", "resource_integrity"],
      "weights": {
        "data_integrity": 0.25,
        "priority_integrity": 0.35,
        "decision_integrity": 0.25,
        "resource_integrity": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "override_risk_model": {
      "risk_factors": ["override_frequency", "missing_justification", "priority_conflict"],
      "severity_map": {
        "override_frequency": "medium",
        "missing_justification": "critical",
        "priority_conflict": "high"
      },
      "auto_flag": true
    },
    "crisis_mode": {
      "enhanced_integrity_checks": ["override_integrity", "resource_tracking", "decision_consistency"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "integrity_report": {
        "fields": ["case_id", "integrity_score", "violations", "recommendations"],
        "routing": "reporting_layer"
      },
      "integrity_alert": {
        "fields": ["case_id", "violation_type", "severity"],
        "routing": "notification_layer"
      },
      "corrective_integrity_action": {
        "fields": ["case_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integr
