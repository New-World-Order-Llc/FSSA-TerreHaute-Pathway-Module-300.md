{
  "notification_cascade_engine": {
    "cascade_domains": {
      "operational_alerts": {
        "triggers": ["worker_overload", "queue_spike", "processing_variance"],
        "channels": ["division_ops", "routing_director"],
        "severity": "high"
      },
      "data_alerts": {
        "triggers": ["schema_break", "timestamp_corruption", "sync_failure"],
        "channels": ["data_integrity_team", "audit_layer"],
        "severity": "critical"
      },
      "decision_alerts": {
        "triggers": ["override_spike", "rule_path_break", "audit_mismatch"],
        "channels": ["supervisor", "governance_kernel"],
        "severity": "critical"
      },
      "resource_alerts": {
        "triggers": ["allocation_collapse", "crisis_pool_depletion", "priority_force_overuse"],
        "channels": ["resource_manager", "routing_director"],
        "severity": "high"
      }
    },
    "cascade_sequence": {
      "tier_1": ["division_ops", "supervisor"],
      "tier_2": ["audit_layer", "resource_manager"],
      "tier_3": ["governance_kernel"],
      "rules": ["no_skip", "strict_order", "auto_escalate"]
    },
    "alert_channels": {
      "channel_alpha": {
        "type": "real_time",
        "methods": ["system_popup", "priority_flag"]
      },
      "channel_beta": {
        "type": "continuous",
        "methods": ["dashboard_update", "audit_log_entry"]
      },
      "channel_gamma": {
        "type": "event_triggered",
        "methods": ["supervisor_notification", "kernel_escalation"]
      }
    },
    "cascade_scoring": {
      "metrics": ["alert_speed", "cascade_integrity", "routing_accuracy", "escalation_consistency"],
      "weights": {
        "alert_speed": 0.3,
        "cascade_integrity": 0.3,
        "routing_accuracy": 0.25,
        "escalation_consistency": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "cascade_stages": {
      "stage_1_detection": {
        "checks": ["variance_spike", "sync_failure", "override_anomaly"],
        "frequency": "real_time"
      },
      "stage_2_alert_generation": {
        "actions": ["alert_classification", "channel_selection", "priority_flag"],
        "frequency": "immediate"
      },
      "stage_3_cascade_execution": {
        "actions": ["tier_1_notify", "tier_2_notify", "tier_3_notify"],
        "frequency": "continuous"
      },
      "stage_4_resolution": {
        "actions": ["audit_alignment", "priority_normalization", "resource_rebalance"],
        "frequency": "post_event"
      }
    },
    "crisis_mode": {
      "enhanced_alerting": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "cascade_report": {
        "fields": ["event_id", "cascade_score", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "cascade_alert": {
        "fields": ["event_id", "alert_type", "severity"],
        "routing": "notification_layer"
      },
      "cascade_correction_action": {
        "fields": ["event_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_cascade_events"]
    }
  }
}
