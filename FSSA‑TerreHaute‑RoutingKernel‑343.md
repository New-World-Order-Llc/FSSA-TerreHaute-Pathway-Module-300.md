{
  "routing_kernel": {
    "routing_domains": {
      "intake_routing": {
        "rules": ["identity_verified_path", "document_complete_path", "priority_initialization"],
        "severity": "medium"
      },
      "eligibility_routing": {
        "rules": ["rule_engine_path", "verification_alignment_path", "priority_consistency_path"],
        "severity": "high"
      },
      "disability_services_routing": {
        "rules": ["assessment_integrity_path", "resource_alignment_path", "service_plan_path"],
        "severity": "high"
      },
      "employment_support_routing": {
        "rules": ["skills_profile_path", "job_match_path", "priority_alignment_path"],
        "severity": "medium"
      },
      "routing_director_path": {
        "rules": ["priority_assignment", "override_justification", "worker_load_balance"],
        "severity": "critical"
      }
    },
    "priority_channels": {
      "channel_alpha": {
        "conditions": ["high_risk", "urgent_need"],
        "actions": ["priority_lock", "accelerated_path"]
      },
      "channel_beta": {
        "conditions": ["standard_case"],
        "actions": ["normal_path"]
      },
      "channel_gamma": {
        "conditions": ["complex_case", "multi_division"],
        "actions": ["supervisor_review_path"]
      }
    },
    "routing_scoring": {
      "metrics": ["priority_integrity", "decision_consistency", "resource_balance", "override_frequency"],
      "weights": {
        "priority_integrity": 0.35,
        "decision_consistency": 0.3,
        "resource_balance": 0.2,
        "override_frequency": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "routing_stages": {
      "stage_1_initialization": {
        "checks": ["identity_verification", "document_completeness", "priority_initialization"],
        "frequency": "real_time"
      },
      "stage_2_path_selection": {
        "actions": ["priority_channel_selection", "rule_engine_path_match"],
        "frequency": "continuous"
      },
      "stage_3_execution": {
        "actions": ["module_routing", "worker_assignment", "override_integrity_check"],
        "frequency": "real_time"
      },
      "stage_4_reconciliation": {
        "actions": ["audit_alignment", "priority_normalization", "resource_rebalance"],
        "frequency": "post_event"
      }
    },
    "crisis_mode": {
      "enhanced_routing": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "routing_report": {
        "fields": ["case_id", "routing_path", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "routing_alert": {
        "fields": ["case_id", "routing_failure_type", "severity"],
        "routing": "notification_layer"
      },
      "routing_correction_action": {
        "fields": ["case_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_routing_events"]
    }
  }
}
