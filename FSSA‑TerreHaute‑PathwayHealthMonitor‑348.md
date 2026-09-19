{
  "pathway_health_monitor": {
    "health_domains": {
      "operational_health": {
        "metrics": ["queue_depth", "worker_load", "processing_variance"],
        "threshold": 0.93,
        "severity": "high"
      },
      "data_health": {
        "metrics": ["schema_integrity", "timestamp_alignment", "sync_accuracy"],
        "threshold": 0.98,
        "severity": "critical"
      },
      "decision_health": {
        "metrics": ["rule_path_integrity", "override_consistency", "audit_alignment"],
        "threshold": 1.0,
        "severity": "critical"
      },
      "resource_health": {
        "metrics": ["allocation_balance", "crisis_pool_status", "priority_force_usage"],
        "threshold": 0.92,
        "severity": "high"
      }
    },
    "health_indicators": {
      "indicator_alpha": {
        "modules": ["intake", "eligibility"],
        "checks": ["queue_depth", "identity_sync"],
        "frequency": "real_time"
      },
      "indicator_beta": {
        "modules": ["bds", "vr"],
        "checks": ["assessment_integrity", "service_alignment"],
        "frequency": "continuous"
      },
      "indicator_gamma": {
        "modules": ["routing", "supervisor", "governance_kernel"],
        "checks": ["priority_integrity", "override_frequency"],
        "frequency": "event_triggered"
      }
    },
    "health_scoring": {
      "metrics": ["operational_health", "data_health", "decision_health", "resource_health"],
      "weights": {
        "operational_health": 0.25,
        "data_health": 0.3,
        "decision_health": 0.3,
        "resource_health": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "health_stages": {
      "stage_1_detection": {
        "checks": ["variance_spike", "sync_failure", "priority_mismatch"],
        "frequency": "real_time"
      },
      "stage_2_diagnosis": {
        "actions": ["root_cause_analysis", "module_state_compare", "priority_alignment_check"],
        "frequency": "continuous"
      },
      "stage_3_stabilization": {
        "actions": ["load_balance", "sync_integrity_repair", "rule_path_rebuild"],
        "frequency": "immediate"
      },
      "stage_4_recovery": {
        "actions": ["audit_repair", "resource_rebalance", "override_integrity_restore"],
        "frequency": "post_event"
      }
    },
    "crisis_mode": {
      "enhanced_health": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "health_report": {
        "fields": ["event_id", "health_score", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "health_alert": {
        "fields": ["event_id", "health_failure_type", "severity"],
        "routing": "notification_layer"
      },
      "health_correction_action": {
        "fields": ["event_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_health_events"]
    }
  }
}
