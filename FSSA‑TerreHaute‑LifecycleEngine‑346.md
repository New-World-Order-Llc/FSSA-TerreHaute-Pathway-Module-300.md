{
  "case_lifecycle_engine": {
    "lifecycle_stages": {
      "stage_1_intake": {
        "checks": ["identity_verification", "document_completeness", "initial_priority"],
        "outputs": ["intake_record"],
        "severity": "medium"
      },
      "stage_2_eligibility": {
        "checks": ["rule_engine_evaluation", "verification_alignment", "priority_consistency"],
        "outputs": ["eligibility_determination"],
        "severity": "high"
      },
      "stage_3_assessment": {
        "checks": ["needs_assessment", "service_alignment", "resource_availability"],
        "outputs": ["assessment_record"],
        "severity": "high"
      },
      "stage_4_service_delivery": {
        "checks": ["service_plan_execution", "worker_assignment", "priority_integrity"],
        "outputs": ["service_delivery_record"],
        "severity": "medium"
      },
      "stage_5_outcome_evaluation": {
        "checks": ["goal_alignment", "service_effectiveness", "audit_consistency"],
        "outputs": ["outcome_report"],
        "severity": "high"
      },
      "stage_6_closure": {
        "checks": ["final_priority_check", "audit_alignment", "resource_rebalance"],
        "outputs": ["closure_record"],
        "severity": "medium"
      }
    },
    "lifecycle_transitions": {
      "intake_to_eligibility": {
        "conditions": ["identity_verified", "documents_complete"],
        "auto_trigger": true
      },
      "eligibility_to_assessment": {
        "conditions": ["eligibility_confirmed"],
        "auto_trigger": true
      },
      "assessment_to_service_delivery": {
        "conditions": ["assessment_complete", "resources_available"],
        "auto_trigger": true
      },
      "service_delivery_to_outcome": {
        "conditions": ["service_plan_executed"],
        "auto_trigger": true
      },
      "outcome_to_closure": {
        "conditions": ["evaluation_complete"],
        "auto_trigger": true
      }
    },
    "lifecycle_scoring": {
      "metrics": ["stage_integrity", "transition_accuracy", "priority_alignment", "audit_consistency"],
      "weights": {
        "stage_integrity": 0.3,
        "transition_accuracy": 0.3,
        "priority_alignment": 0.25,
        "audit_consistency": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "lifecycle_exceptions": {
      "priority_override": {
        "conditions": ["urgent_need", "public_safety"],
        "actions": ["priority_shift", "accelerated_transition"]
      },
      "routing_override": {
        "conditions": ["module_failure", "worker_unavailable"],
        "actions": ["alternate_path", "supervisor_review"]
      }
    },
    "crisis_mode": {
      "enhanced_lifecycle": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "lifecycle_report": {
        "fields": ["case_id", "current_stage", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "lifecycle_alert": {
        "fields": ["case_id", "stage_failure_type", "severity"],
        "routing": "notification_layer"
      },
      "lifecycle_correction_action": {
        "fields": ["case_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_lifecycle_events"]
    }
  }
}
