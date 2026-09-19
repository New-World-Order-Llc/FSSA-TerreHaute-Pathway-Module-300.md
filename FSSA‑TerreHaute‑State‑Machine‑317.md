{
  "state_machine": {
    "states": {
      "INTAKE": {
        "entry_actions": ["collect_data", "verify_identity"],
        "exit_actions": ["generate_intake_record"]
      },
      "ELIGIBILITY": {
        "entry_actions": ["run_rule_validation"],
        "exit_actions": ["update_eligibility_status"]
      },
      "DISABILITY_SERVICES": {
        "entry_actions": ["perform_assessment"],
        "exit_actions": ["approve_service_plan"]
      },
      "EMPLOYMENT_SUPPORT": {
        "entry_actions": ["conduct_skills_assessment"],
        "exit_actions": ["generate_job_match"]
      },
      "ROUTING": {
        "entry_actions": ["assign_worker", "set_priority"],
        "exit_actions": ["record_routing"]
      },
      "CASE_MANAGEMENT": {
        "entry_actions": ["monitor_progress"],
        "exit_actions": ["update_case_status"]
      },
      "CLOSURE": {
        "entry_actions": ["final_review", "token_compliance_check"],
        "exit_actions": ["archive_case"]
      }
    },
    "transitions": {
      "INTAKE_TO_ELIGIBILITY": {
        "guard": "identity_verified && documents_complete",
        "crisis_override": true
      },
      "ELIGIBILITY_TO_DISABILITY": {
        "guard": "medical_need_confirmed || disability_flag",
        "crisis_override": true
      },
      "DISABILITY_TO_EMPLOYMENT": {
        "guard": "assessment_valid",
        "crisis_override": false
      },
      "EMPLOYMENT_TO_ROUTING": {
        "guard": "skills_profile_complete",
        "crisis_override": true
      },
      "ROUTING_TO_CASE_MANAGEMENT": {
        "guard": "worker_assigned",
        "crisis_override": true
      },
      "CASE_MANAGEMENT_TO_CLOSURE": {
        "guard": "case_resolved",
        "crisis_override": false
      }
    },
    "compliance": {
      "lucr_gates": ["INTAKE", "ELIGIBILITY", "ROUTING", "CLOSURE"],
      "audit_points": ["transition_validation", "override_logging"]
    },
    "crisis_mode": {
      "enabled": true,
      "override_points": ["INTAKE_TO_ELIGIBILITY", "ELIGIBILITY_TO_DISABILITY", "EMPLOYMENT_TO_ROUTING", "ROUTING_TO_CASE_MANAGEMENT"]
    }
  }
}
