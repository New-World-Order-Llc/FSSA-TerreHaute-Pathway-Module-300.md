{
  "shock_absorption_model": {
    "shock_domains": {
      "operational_shock": {
        "triggers": ["worker_overload", "queue_spike", "processing_variance"],
        "buffers": ["load_smoothing", "fallback_worker_assignment"],
        "severity": "high"
      },
      "data_shock": {
        "triggers": ["schema_break", "timestamp_corruption", "sync_failure"],
        "buffers": ["audit_log_restore", "integrity_matrix_repair"],
        "severity": "critical"
      },
      "decision_shock": {
        "triggers": ["override_spike", "rule_path_break", "audit_mismatch"],
        "buffers": ["supervisor_backup", "governance_kernel_intervention"],
        "severity": "critical"
      },
      "resource_shock": {
        "triggers": ["allocation_collapse", "crisis_pool_depletion", "priority_force_overuse"],
        "buffers": ["emergency_reallocation", "resource_freeze"],
        "severity": "high"
      }
    },
    "absorption_channels": {
      "primary": ["fallback_routing", "priority_lock", "resource_freeze"],
      "secondary": ["module_bridge", "division_manager_bridge"],
      "tertiary": ["governance_kernel_override"]
    },
    "shock_scoring": {
      "metrics": ["operational_shock", "data_shock", "decision_shock", "resource_shock"],
      "weights": {
        "operational_shock": 0.25,
        "data_shock": 0.3,
        "decision_shock": 0.3,
        "resource_shock": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "shock_stages": {
      "stage_1_detection": {
        "checks": ["variance_spike", "sync_failure", "override_anomaly"],
        "frequency": "real_time"
      },
      "stage_2_absorption": {
        "actions": ["fallback_routing", "priority_lock", "resource_freeze"],
        "frequency": "immediate"
      },
      "stage_3_stabilization": {
        "actions": ["load_balance", "sync_integrity", "rule_path_repair"],
        "frequency": "continuous"
      },
      "stage_4_recovery": {
        "actions": ["audit_repair", "integrity_rebuild", "resource_rebalance"],
        "frequency": "post_event"
      }
    },
    "crisis_mode": {
      "enhanced_absorption": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "shock_report": {
        "fields": ["event_id", "shock_score", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "shock_alert": {
        "fields": ["event_id", "shock_type", "severity"],
        "routing": "notification_layer"
      },
      "shock_recovery_action": {
        "fields": ["event_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_shock_events"]
    }
  }
}
