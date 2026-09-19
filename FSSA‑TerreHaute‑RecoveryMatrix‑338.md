{
  "recovery_matrix": {
    "recovery_domains": {
      "operational_recovery": {
        "checks": ["queue_normalization", "worker_load_rebalance", "processing_time_stabilization"],
        "threshold": 0.9,
        "severity": "high"
      },
      "data_recovery": {
        "checks": ["schema_repair", "timestamp_rebuild", "cross_module_resync"],
        "threshold": 0.97,
        "severity": "critical"
      },
      "decision_recovery": {
        "checks": ["rule_path_rebuild", "override_integrity_repair", "audit_alignment_recovery"],
        "threshold": 1.0,
        "severity": "critical"
      },
      "resource_recovery": {
        "checks": ["allocation_rebalance", "crisis_pool_recovery", "priority_force_normalization"],
        "threshold": 0.92,
        "severity": "high"
      }
    },
    "recovery_paths": {
      "standard": {
        "steps": ["containment", "repair", "rebuild", "reintegration"],
        "duration_hours": 48
      },
      "accelerated": {
        "conditions": ["high_priority", "time_sensitive"],
        "steps": ["repair", "rebuild"],
        "duration_hours": 12
      },
      "crisis": {
        "conditions": ["public_safety_risk", "resource_collapse"],
        "steps": ["governance_kernel_intervention", "priority_force_mode", "emergency_rebuild"],
        "duration_hours": 6
      }
    },
    "recovery_scoring": {
      "metrics": ["operational_recovery", "data_recovery", "decision_recovery", "resource_recovery"],
      "weights": {
        "operational_recovery": 0.25,
        "data_recovery": 0.3,
        "decision_recovery": 0.3,
        "resource_recovery": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "reintegration_rules": {
      "checks": ["rule_path_realignment", "priority_normalization", "module_reactivation"],
      "required_fields": ["event_id", "reintegration_stage", "timestamp"]
    },
    "crisis_mode": {
      "enhanced_recovery": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "recovery_report": {
        "fields": ["event_id", "recovery_score", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "recovery_alert": {
        "fields": ["event_id", "shock_type", "severity"],
        "routing": "notification_layer"
      },
      "recovery_action": {
        "fields": ["event_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_recovery_events"]
    }
  }
}
