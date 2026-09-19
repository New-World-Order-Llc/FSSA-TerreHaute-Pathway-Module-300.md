{
  "resilience_model": {
    "resilience_domains": {
      "operational_resilience": {
        "checks": ["worker_load_recovery", "queue_normalization", "processing_time_rebound"],
        "threshold": 0.9,
        "severity": "high"
      },
      "data_resilience": {
        "checks": ["schema_repair", "timestamp_recovery", "cross_module_resync"],
        "threshold": 0.97,
        "severity": "critical"
      },
      "decision_resilience": {
        "checks": ["rule_path_rebuild", "override_integrity_recovery", "audit_alignment_repair"],
        "threshold": 1.0,
        "severity": "critical"
      },
      "resource_resilience": {
        "checks": ["allocation_rebalance", "crisis_pool_recovery", "priority_force_normalization"],
        "threshold": 0.92,
        "severity": "high"
      }
    },
    "shock_types": {
      "module_failure": {
        "impact": "high",
        "auto_trigger": true,
        "recovery_actions": ["fallback_routing", "rule_engine_switch", "integrity_matrix_repair"]
      },
      "data_corruption": {
        "impact": "critical",
        "auto_trigger": true,
        "recovery_actions": ["audit_log_restore", "schema_repair", "timestamp_rebuild"]
      },
      "priority_cascade": {
        "impact": "high",
        "auto_trigger": true,
        "recovery_actions": ["priority_rebalance", "override_integrity_check"]
      },
      "resource_collapse": {
        "impact": "critical",
        "auto_trigger": true,
        "recovery_actions": ["crisis_pool_activation", "resource_reallocation"]
      }
    },
    "resilience_scoring": {
      "metrics": ["operational_resilience", "data_resilience", "decision_resilience", "resource_resilience"],
      "weights": {
        "operational_resilience": 0.25,
        "data_resilience": 0.3,
        "decision_resilience": 0.3,
        "resource_resilience": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "recovery_stages": {
      "stage_1_detection": {
        "checks": ["variance_spike", "sync_failure", "override_anomaly"],
        "frequency": "real_time"
      },
      "stage_2_containment": {
        "actions": ["fallback_routing", "priority_lock", "resource_freeze"],
        "frequency": "immediate"
      },
      "stage_3_recovery": {
        "actions": ["audit_repair", "integrity_rebuild", "resource_rebalance"],
        "frequency": "continuous"
      },
      "stage_4_reintegration": {
        "actions": ["rule_path_realignment", "priority_normalization", "module_reactivation"],
        "frequency": "post_event"
      }
    },
    "crisis_mode": {
      "enhanced_resilience": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "resilience_report": {
        "fields": ["event_id", "resilience_score", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "resilience_alert": {
        "fields": ["event_id", "shock_type", "severity"],
        "routing": "notification_layer"
      },
      "resilience_recovery_action": {
        "fields": ["event_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_resilience_events"]
    }
  }
}
