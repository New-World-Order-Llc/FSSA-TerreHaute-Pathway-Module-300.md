{
  "case_lifecycle": {
    "stages": {
      "intake": {
        "actions": ["collect_data", "verify_identity", "program_selection"],
        "outputs": ["intake_record"]
      },
      "eligibility": {
        "actions": ["income_check", "document_review", "rule_validation"],
        "outputs": ["eligibility_status"]
      },
      "disability_services": {
        "actions": ["assessment", "plan_creation", "resource_assignment"],
        "outputs": ["service_plan"]
      },
      "employment_support": {
        "actions": ["skills_assessment", "job_matching", "tech_assignment"],
        "outputs": ["employment_support_record"]
      },
      "routing": {
        "actions": ["assign_worker", "set_priority", "crisis_override"],
        "outputs": ["routing_record"]
      },
      "case_management": {
        "actions": ["monitor_progress", "update_plan", "resolve_case"],
        "outputs": ["case_status"]
      },
      "closure": {
        "actions": ["final_review", "token_compliance_check"],
        "outputs": ["closed_case"]
      }
    },
    "token_hooks": ["LUCR_lifecycle_compliance"],
    "crisis_mode": {
      "enabled": true,
      "override_points": ["eligibility", "routing", "case_management"]
    }
  }
}
