{
  "authority_model": {
    "roles": {
      "intake_specialist": {
        "permissions": ["create_intake", "verify_identity", "request_documents"],
        "override": false,
        "reports_to": "intake_supervisor"
      },
      "intake_supervisor": {
        "permissions": ["approve_intake", "resolve_identity_conflicts"],
        "override": true,
        "reports_to": "division_manager_dfr"
      },
      "eligibility_worker": {
        "permissions": ["run_validation", "update_status"],
        "override": false,
        "reports_to": "eligibility_supervisor"
      },
      "eligibility_supervisor": {
        "permissions": ["approve_eligibility", "trigger_reverification"],
        "override": true,
        "reports_to": "division_manager_dfr"
      },
      "disability_coordinator": {
        "permissions": ["conduct_assessment", "assign_resources"],
        "override": false,
        "reports_to": "bds_supervisor"
      },
      "bds_supervisor": {
        "permissions": ["approve_plans", "authorize_resources"],
        "override": true,
        "reports_to": "division_manager_bds"
      },
      "employment_counselor": {
        "permissions": ["skills_assessment", "job_matching"],
        "override": false,
        "reports_to": "vr_supervisor"
      },
      "vr_supervisor": {
        "permissions": ["approve_matches", "assign_tech"],
        "override": true,
        "reports_to": "division_manager_vr"
      },
      "routing_director": {
        "permissions": ["assign_workers", "set_priority", "activate_crisis_mode"],
        "override": true,
        "reports_to": "governance_kernel"
      }
    },
    "hierarchy": {
      "division_manager_dfr": ["intake_supervisor", "eligibility_supervisor"],
      "division_manager_bds": ["bds_supervisor"],
      "division_manager_vr": ["vr_supervisor"],
      "governance_kernel": ["routing_director", "division_manager_dfr", "division_manager_bds", "division_manager_vr"]
    },
    "override_rules": {
      "standard": {
        "allowed_roles": ["intake_supervisor", "eligibility_supervisor", "bds_supervisor", "vr_supervisor"],
        "conditions": ["data_conflict", "priority_misalignment"]
      },
      "crisis": {
        "allowed_roles": ["routing_director", "governance_kernel"],
        "conditions": ["resource_overload", "public_safety_risk"],
        "strictness": "maximum"
      }
    },
    "lucr_alignment": {
      "required_for": ["all_supervisors", "routing_director", "governance_kernel"],
      "checks": ["priority_integrity", "override_logging", "decision_consistency"]
    }
  }
}
