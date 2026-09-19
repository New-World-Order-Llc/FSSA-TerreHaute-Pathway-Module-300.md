{
  "workflow_spec": {
    "intake": {
      "steps": ["collect_data", "identity_check", "program_selection"],
      "modules": ["DFR", "BDS", "VR"]
    },
    "verification": {
      "steps": ["document_review", "eligibility_rules", "case_flagging"]
    },
    "routing": {
      "steps": ["assign_worker", "schedule_meeting", "resource_match"],
      "crisis_override": true
    },
    "case_management": {
      "steps": ["track_progress", "update_plan", "close_case"],
      "token_hooks": ["LUCR_compliance"]
    }
  }
}
