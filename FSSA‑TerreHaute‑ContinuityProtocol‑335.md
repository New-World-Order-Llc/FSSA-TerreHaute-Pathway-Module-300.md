{
  "continuity_protocol": {
    "continuity_domains": {
      "operational_flow": {
        "rules": ["no_dead_end_paths", "auto_retry_failed_actions", "fallback_worker_assignment"],
        "strictness": "high"
      },
      "data_continuity": {
        "rules": ["redundant_storage", "timestamp_repair", "cross_module_sync"],
        "strictness": "critical"
      },
      "decision_continuity": {
        "rules": ["rule_engine_failover", "supervisor_backup_path", "governance_kernel_override"],
        "strictness": "critical"
      },
      "resource_continuity": {
        "rules": ["dynamic_reallocation", "crisis_resource_pool", "priority_force_mode"],
        "strictness": "high"
      }
    },
    "failover_rules": {
      "module_failure": {
        "fallback": ["adjacent_module", "supervisor_review", "governance_kernel"],
        "auto_trigger": true
      },
      "worker_unavailable": {
        "fallback": ["routing_director_reassignment", "priority_rebalance"],
        "auto_trigger": true
      },
      "data_corruption": {
        "fallback": ["integrity_matrix_repair", "audit_log_restore"],
        "auto_trigger": true
      }
    },
    "continuity_stages": {
      "stage_1_prevention": {
        "checks": ["resource_load", "priority_alignment", "override_frequency"],
        "frequency": "real_time"
      },
      "stage_2_detection": {
        "checks": ["module_health", "data_integrity", "decision_consistency"],
        "frequency": "continuous"
      },
      "stage_3_failover": {
        "actions": ["fallback_routing", "rule_engine_switch", "resource_reallocation"],
        "frequency": "immediate"
      },
      "stage_4_recovery": {
        "actions": ["audit_repair", "integrity_rebuild", "priority_reconciliation"],
        "frequency": "post_event"
      }
    },
    "crisis_mode": {
        "enhanced_continuity": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
        "strictness": "maximum",
        "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "continuity_report": {
        "fields": ["event_id", "continuity_stage", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "continuity_alert": {
        "fields": ["event_id", "failure_type", "severity"],
        "routing": "notification_layer"
      },
      "continuity_recovery_action": {
        "fields": ["event_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_continuity_events"]
    }
  }
}
