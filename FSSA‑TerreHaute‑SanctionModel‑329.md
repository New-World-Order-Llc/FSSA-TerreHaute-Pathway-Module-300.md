{
  "sanction_model": {
    "sanction_tiers": {
      "tier_1_operational": {
        "conditions": ["minor_data_error", "missed_deadline_low"],
        "actions": ["retraining", "process_review"],
        "severity": "low",
        "initiated_by": "supervisor"
      },
      "tier_2_compliance": {
        "conditions": ["data_mismatch", "priority_misalignment"],
        "actions": ["audit_review", "mandatory_reverification"],
        "severity": "medium",
        "initiated_by": "division_manager"
      },
      "tier_3_governance": {
        "conditions": ["override_abuse", "decision_inconsistency"],
        "actions": ["case_reassignment", "priority_reset", "decision_reversal"],
        "severity": "high",
        "initiated_by": "governance_kernel"
      },
      "tier_4_crisis": {
        "conditions": ["public_safety_risk", "resource_overload"],
        "actions": ["forced_override", "emergency_directive"],
        "severity": "critical",
        "initiated_by": "routing_director"
      }
    },
    "escalation_logic": {
      "paths": {
        "operational": ["supervisor", "division_manager"],
        "compliance": ["division_manager", "governance_kernel"],
        "critical": ["governance_kernel", "executive_layer"]
      },
      "strictness": "maximum"
    },
    "required_fields": ["case_id", "sanction_tier", "timestamp", "reason"],
    "review_requirements": {
      "tier_1": "operational_panel",
      "tier_2": "compliance_panel",
      "tier_3": "governance_panel",
      "tier_4": "governance_kernel"
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "override_logging"],
      "required_for": ["all_sanctions"]
    }
  }
}
