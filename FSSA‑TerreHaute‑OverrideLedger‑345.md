{
  "override_ledger": {
    "override_domains": {
      "priority_override": {
        "conditions": ["urgent_need", "risk_elevation", "public_safety"],
        "required_fields": ["override_reason", "priority_shift"],
        "severity": "high"
      },
      "routing_override": {
        "conditions": ["module_failure", "worker_unavailable", "complex_case"],
        "required_fields": ["override_reason", "new_route"],
        "severity": "critical"
      },
      "resource_override": {
        "conditions": ["allocation_collapse", "crisis_pool_activation"],
        "required_fields": ["override_reason", "resource_shift"],
        "severity": "high"
      },
      "decision_override": {
        "conditions": ["rule_path_break", "audit_mismatch"],
        "required_fields": ["override_reason", "decision_shift"],
        "severity": "critical"
      }
    },
    "override_record": {
      "fields": [
        "override_id",
        "case_id",
        "supervisor_id",
        "override_type",
        "override_reason",
        "timestamp",
        "pre_override_state",
        "post_override_state"
      ],
      "integrity_checks": ["audit_alignment", "priority_integrity", "decision_consistency"]
    },
    "override_scoring": {
      "metrics": ["override_frequency", "override_severity", "justification_quality", "impact_alignment"],
      "weights": {
        "override_frequency": 0.25,
        "override_severity": 0.3,
        "justification_quality": 0.3,
        "impact_alignment": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "override_stages": {
      "stage_1_request": {
        "checks": ["override_reason", "impact_assessment"],
        "frequency": "real_time"
      },
      "stage_2_execution": {
        "actions": ["priority_shift", "route_change", "resource_reallocation"],
        "frequency": "immediate"
      },
      "stage_3_logging": {
        "actions": ["ledger_entry", "audit_log_update"],
        "frequency": "continuous"
      },
      "stage_4_review": {
        "actions": ["supervisor_review", "audit_alignment", "priority_normalization"],
        "frequency": "post_event"
      }
    },
    "crisis_mode": {
      "enhanced_override": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "override_report": {
        "fields": ["override_id", "case_id", "override_type", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "override_alert": {
        "fields": ["override_id", "override_type", "severity"],
        "routing": "notification_layer"
      },
      "override_correction_action": {
        "fields": ["override_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_override_events"]
    }
  }
}
