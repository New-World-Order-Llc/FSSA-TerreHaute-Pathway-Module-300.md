{
  "oversight_engine": {
    "monitoring_layers": {
      "operational": {
        "checks": ["processing_time", "priority_alignment", "worker_load"],
        "frequency": "real_time",
        "escalates_to": "supervisory_layer"
      },
      "supervisory": {
        "checks": ["override_frequency", "data_mismatch", "rule_compliance"],
        "frequency": "hourly",
        "escalates_to": "governance_layer"
      },
      "governance": {
        "checks": ["lucr_alignment", "audit_integrity", "decision_consistency"],
        "frequency": "daily",
        "escalates_to": "executive_layer"
      }
    },
    "escalation_rules": {
      "triggers": ["missed_deadline", "priority_conflict", "resource_overload"],
      "paths": {
        "low": ["operational"],
        "medium": ["operational", "supervisory"],
        "high": ["operational", "supervisory", "governance"],
        "critical": ["governance", "executive_layer"]
      },
      "strictness": "maximum"
    },
    "compliance_scoring": {
      "metrics": ["lucr_alignment", "audit_score", "integrity_score"],
      "weights": {
        "lucr_alignment": 0.5,
        "audit_score": 0.3,
        "integrity_score": 0.2
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "crisis_mode": {
      "enhanced_checks": ["override_logging", "resource_allocation", "priority_force"],
      "frequency": "continuous",
      "required_fields": ["override_reason", "risk_level"]
    },
    "reporting": {
      "outputs": ["oversight_summary", "compliance_report", "crisis_alert"],
      "routes": {
        "oversight_summary": "reporting_layer",
        "compliance_report": "audit_log",
        "crisis_alert": "notification_layer"
      }
    },
    "lucr_hooks": ["oversight_integrity", "priority_alignment", "decision_consistency"]
  }
}
