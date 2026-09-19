{
  "governance_anchor_node": {
    "anchor_domains": {
      "operational_anchor": {
        "functions": ["queue_stabilization", "worker_load_grounding", "processing_variance_control"],
        "severity": "high"
      },
      "data_anchor": {
        "functions": ["schema_lock", "timestamp_grounding", "sync_integrity_hold"],
        "severity": "critical"
      },
      "decision_anchor": {
        "functions": ["rule_path_lock", "override_integrity_hold", "audit_alignment_lock"],
        "severity": "critical"
      },
      "resource_anchor": {
        "functions": ["allocation_lock", "crisis_pool_grounding", "priority_force_control"],
        "severity": "high"
      }
    },
    "anchor_points": {
      "point_alpha": {
        "modules": ["intake", "eligibility"],
        "mode": "strict",
        "frequency": "real_time"
      },
      "point_beta": {
        "modules": ["bds", "vr"],
        "mode": "balanced",
        "frequency": "continuous"
      },
      "point_gamma": {
        "modules": ["routing", "supervisor", "governance_kernel"],
        "mode": "critical",
        "frequency": "event_triggered"
      }
    },
    "anchor_locking": {
      "lock_types": ["priority_lock", "rule_path_lock", "resource_lock"],
      "auto_trigger_conditions": ["variance_spike", "sync_failure", "override_anomaly"]
    },
    "anchor_scoring": {
      "metrics": ["anchor_integrity", "anchor_stability", "anchor_consistency", "anchor_resilience"],
      "weights": {
        "anchor_integrity": 0.35,
        "anchor_stability": 0.3,
        "anchor_consistency": 0.2,
        "anchor_resilience": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "anchor_stages": {
      "stage_1_detection": {
        "checks": ["priority_mismatch", "timestamp_drift", "rule_path_variance"],
        "frequency": "real_time"
      },
      "stage_2_locking": {
        "actions": ["priority_lock", "rule_path_lock", "resource_lock"],
        "frequency": "immediate"
      },
      "stage_3_stabilization": {
        "actions": ["audit_alignment", "sync_integrity_repair", "resource_balance"],
        "frequency": "continuous"
      },
      "stage_4_recovery": {
        "actions": ["override_integrity_restore", "rule_path_rebuild", "allocation_rebalance"],
        "frequency": "post_event"
      }
    },
    "crisis_mode": {
      "enhanced_anchor": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "anchor_report": {
        "fields": ["event_id", "anchor_score", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "anchor_alert": {
        "fields": ["event_id", "anchor_failure_type", "severity"],
        "routing": "notification_layer"
      },
      "anchor_correction_action": {
        "fields": ["event_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_anchor_events"]
    }
  }
}
