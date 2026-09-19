{
  "integration_map": {
    "systems": {
      "intake_module": {
        "inputs": ["applicant_data", "documents", "identity_status"],
        "outputs": ["intake_record"],
        "connected_to": ["eligibility_module", "event_bus"]
      },
      "eligibility_module": {
        "inputs": ["intake_record", "verification_flags"],
        "outputs": ["eligibility_status"],
        "connected_to": ["disability_module", "routing_module", "reporting_layer"]
      },
      "disability_module": {
        "inputs": ["eligibility_status", "assessment_data"],
        "outputs": ["service_plan"],
        "connected_to": ["employment_module", "governance_kernel"]
      },
      "employment_module": {
        "inputs": ["skills_profile", "service_plan"],
        "outputs": ["job_match_record"],
        "connected_to": ["routing_module", "notification_layer"]
      },
      "routing_module": {
        "inputs": ["priority_score", "job_match_record", "crisis_flags"],
        "outputs": ["routing_record"],
        "connected_to": ["case_management_module", "event_bus", "governance_kernel"]
      },
      "case_management_module": {
        "inputs": ["routing_record", "service_updates"],
        "outputs": ["case_status"],
        "connected_to": ["closure_module", "reporting_layer"]
      },
      "closure_module": {
        "inputs": ["case_status", "compliance_check"],
        "outputs": ["closed_case"],
        "connected_to": ["audit_log", "governance_kernel"]
      }
    },
    "shared_channels": {
      "event_bus": ["intake_events", "eligibility_events", "routing_events", "system_events"],
      "notification_layer": ["internal", "external", "crisis"],
      "reporting_layer": ["dashboards", "lifecycle_summary"],
      "governance_kernel": ["rule_engine", "decision_paths", "compliance_gates"]
    },
    "compliance": {
      "lucr_hooks": ["integration_integrity", "priority_alignment", "override_logging"],
      "audit_required": true
    }
  }
}
