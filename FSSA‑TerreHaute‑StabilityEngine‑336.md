{
  "stability_engine": {
    "stability_domains": {
      "operational_stability": {
        "checks": ["worker_load_balance", "queue_depth", "processing_time_variance"],
        "threshold": 0.95,
        "severity": "high"
      },
      "data_stability": {
        "checks": ["sync_integrity", "timestamp_alignment", "schema_consistency"],
        "threshold": 0.98,
        "severity": "critical"
      },
      "decision_stability": {
        "checks": ["rule_path_consistency", "override_frequency", "audit_alignment"],
        "threshold": 1.0,
        "severity": "critical"
      },
      "resource_stability": {
        "checks": ["allocation_balance", "crisis_pool_health", "priority_force_usage"],
        "threshold": 0.94,
        "severity": "high"
      }
    },
    "stability_scoring": {
      "metrics": ["operational_stability", "data_stability", "decision_stability", "resource_stability"],
      "weights": {
        "operational_stability": 0.25,
        "data_stability": 0.3,
        "decision_stability": 0.3,
        "resource_stability": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "cascading_failure_prevention": {
      "triggers": ["module_overload", "data_corruption", "priority_conflict"],
      "actions": ["fallback_routing", "integrity_matrix_repair", "governance_kernel_intervention"],
      "auto_trigger": true
    },
    "stability_stages": {
      "stage_1_monitoring": {
        "checks": ["load_balance", "sync_integrity", "rule_path_health"],
        "frequency": "real_time"
      },
      "stage_2_detection": {
        "checks": ["variance_spike", "override_anomaly", "resource_dip"],
        "frequency": "continuous"
      },
      "stage_3_intervention": {
        "actions": ["priority_rebalance", "resource_reallocation", "rule_engine_switch"],
        "frequency": "immediate"
      },
      "stage_4_recovery": {
        "actions": ["audit_repair", "integrity_rebuild", "stability_recalibration"],
        "frequency": "post_event"
      }
    },
    "crisis_mode": {
      "enhanced_stability": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "stability_report": {
        "fields": ["event_id", "stability_score", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "stability_alert": {
        "fields": ["event_id", "failure_type", "severity"],
        "routing": "notification_layer"
      },
      "stability_recovery_action": {
        "fields": ["event_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_stability_events"]
    }
  }
}
