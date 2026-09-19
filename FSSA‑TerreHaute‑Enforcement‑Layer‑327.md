{
  "enforcement_layer": {
    "enforcement_types": {
      "operational": {
        "actions": ["retraining_required", "process_correction", "data_fix"],
        "severity": "low",
        "initiated_by": "supervisor"
      },
      "compliance": {
        "actions": ["audit_review", "mandatory_reverification", "override_investigation"],
        "severity": "medium",
        "initiated_by": "division_manager"
      },
      "governance": {
        "actions": ["priority_reset", "case_reassignment", "decision_reversal"],
        "severity": "high",
        "initiated_by": "governance_kernel"
      },
      "crisis": {
        "actions": ["forced_override", "resource_reallocation", "emergency_directive"],
        "severity": "critical",
        "initiated_by": "routing_director"
      }
    },
    "trigger_conditions": {
      "data_mismatch": {
        "severity": "medium",
        "auto_enforce": true
      },
      "priority_conflict": {
        "severity": "high",
        "auto_enforce": true
      },
      "missed_deadline": {
        "severity": "medium",
        "auto_enforce": false
      },
      "override_abuse": {
        "severity": "critical",
        "auto_enforce": true
      }
    },
    "corrective_actions": {
      "worker_level": ["retraining", "process_review", "case_reassignment"],
      "supervisor_level": ["override_audit", "compliance_meeting"],
      "division_level": ["policy_update", "workflow_adjustment"],
      "governance_level": ["rule_rewrite", "decision_path_modification"]
    },
    "crisis_mode": {
      "enhanced_enforcement": ["forced_override", "emergency_directive"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "override_logging"],
      "required_for": ["all_supervisors", "routing_director", "governance_kernel"]
    }
  }
}
