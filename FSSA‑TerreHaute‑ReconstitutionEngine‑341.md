{
  "reconstitution_engine": {
    "reconstitution_domains": {
      "operational_reconstitution": {
        "actions": ["queue_rebuild", "worker_load_realignment", "processing_time_normalization"],
        "severity": "high"
      },
      "data_reconstitution": {
        "actions": ["schema_repair", "timestamp_rebuild", "cross_module_resync"],
        "severity": "critical"
      },
      "decision_reconstitution": {
        "actions": ["rule_path_rebuild", "override_integrity_restore", "audit_alignment_repair"],
        "severity": "critical"
      },
      "resource_reconstitution": {
        "actions": ["allocation_rebalance", "crisis_pool_recovery", "priority_force_normalization"],
        "severity": "high"
      }
    },
    "reconstitution_paths": {
      "standard": {
        "steps": ["assessment", "repair", "rebuild", "reintegration"],
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
    "reconstitution_scoring": {
      "metrics": ["operational_reconstitution", "data_reconstitution", "decision_reconstitution", "resource_reconstitution"],
      "weights": {
        "operational_reconstitution": 0.25,
        "data_reconstitution": 0.3,
        "decision_reconstitution": 0.3,
        "resource_reconstitution": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "reintegration_rules": {
      "checks": ["rule_path_realignment", "priority_normalization", "module_reactivation"],
      "required_fields": ["event_id", "reintegration_stage", "timestamp"]
    },
    "crisis_mode": {
      "enhanced_reconstitution": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "reconstitution_report": {
        "fields": ["event_id", "reconstitution_score", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "reconstitution_alert": {
        "fields": ["event_id", "failure_type", "severity"],
        "routing": "notification_layer"
      },
      "reconstitution_action": {
        "fields": ["event_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_reconstitution_events"]
    }
  }
}
