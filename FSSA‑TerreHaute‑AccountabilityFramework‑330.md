{
  "accountability_framework": {
    "responsibility_chains": {
      "intake": {
        "primary": "intake_specialist",
        "secondary": "intake_supervisor",
        "manager": "division_manager_dfr"
      },
      "eligibility": {
        "primary": "eligibility_worker",
        "secondary": "eligibility_supervisor",
        "manager": "division_manager_dfr"
      },
      "disability_services": {
        "primary": "disability_coordinator",
        "secondary": "bds_supervisor",
        "manager": "division_manager_bds"
      },
      "employment_support": {
        "primary": "employment_counselor",
        "secondary": "vr_supervisor",
        "manager": "division_manager_vr"
      },
      "routing": {
        "primary": "routing_director",
        "secondary": "governance_kernel",
        "manager": "executive_layer"
      }
    },
    "performance_metrics": {
      "timeliness": {
        "definition": "Completion of required actions within defined time windows",
        "thresholds": {
          "intake": 4,
          "eligibility": 6,
          "disability": 12,
          "employment": 8,
          "routing": 2
        }
      },
      "accuracy": {
        "definition": "Data integrity and correct rule execution",
        "threshold": 0.98
      },
      "priority_alignment": {
        "definition": "Correct assignment and maintenance of priority levels",
        "threshold": 0.95
      },
      "override_integrity": {
        "definition": "Proper justification and logging of overrides",
        "threshold": 1.0
      }
    },
    "escalation_routes": {
      "operational": ["supervisor", "division_manager"],
      "compliance": ["division_manager", "governance_kernel"],
      "critical": ["governance_kernel", "executive_layer"],
      "strictness": "maximum"
    },
    "corrective_obligations": {
      "worker": ["retraining", "process_review"],
      "supervisor": ["override_audit", "compliance_meeting"],
      "division_manager": ["policy_update", "workflow_adjustment"],
      "governance_kernel": ["rule_rewrite", "decision_path_modification"]
    },
    "crisis_mode": {
      "enhanced_accountability": ["forced_override_logging", "resource_allocation_tracking"],
      "required_fields": ["override_reason", "risk_level", "resource_allocation"],
      "strictness": "maximum"
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_roles"]
    }
  }
}
