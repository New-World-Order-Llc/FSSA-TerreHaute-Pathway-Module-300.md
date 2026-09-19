{
  "review_board": {
    "board_structure": {
      "operational_panel": {
        "members": ["intake_supervisor", "eligibility_supervisor", "bds_supervisor"],
        "scope": ["process_review", "data_integrity", "priority_alignment"],
        "frequency": "weekly"
      },
      "compliance_panel": {
        "members": ["division_manager_dfr", "division_manager_bds", "division_manager_vr"],
        "scope": ["audit_results", "override_frequency", "rule_compliance"],
        "frequency": "monthly"
      },
      "governance_panel": {
        "members": ["routing_director", "governance_kernel"],
        "scope": ["lucr_alignment", "decision_consistency", "crisis_mode_actions"],
        "frequency": "quarterly"
      }
    },
    "review_cycles": {
      "standard": {
        "steps": ["case_selection", "document_review", "supervisor_interview", "final_report"],
        "duration_days": 7
      },
      "accelerated": {
        "conditions": ["high_priority", "time_sensitive"],
        "steps": ["document_review", "supervisor_interview"],
        "duration_days": 3
      },
      "crisis": {
        "conditions": ["public_safety_risk", "resource_overload"],
        "steps": ["immediate_review", "governance_kernel_decision"],
        "duration_hours": 12
      }
    },
    "evaluation_rules": {
      "checks": ["data_integrity", "priority_alignment", "override_logging", "audit_consistency"],
      "required_fields": ["case_id", "review_type", "timestamp"]
    },
    "escalation_paths": {
      "operational": ["operational_panel", "compliance_panel"],
      "compliance": ["compliance_panel", "governance_panel"],
      "critical": ["governance_panel"]
    },
    "outputs": {
      "review_summary": {
        "fields": ["case_id", "findings", "recommendations", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "corrective_action_request": {
        "fields": ["case_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      },
      "crisis_alert": {
        "fields": ["case_id", "risk_level", "override_required"],
        "routing": "notification_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_panels"]
    }
  }
}
