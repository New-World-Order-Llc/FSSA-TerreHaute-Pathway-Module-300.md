{
  "sync_map": {
    "internal_agencies": {
      "DFR": ["intake_sync", "eligibility_sync", "routing_sync"],
      "BDS": ["assessment_sync", "plan_sync", "resource_sync"],
      "VR": ["skills_sync", "job_sync", "case_sync"]
    },
    "shared_channels": {
      "intake_sync": {
        "data": ["applicant_id", "program_requested"],
        "frequency": "real_time"
      },
      "verification_sync": {
        "data": ["identity_status", "document_flags"],
        "frequency": "hourly"
      },
      "routing_sync": {
        "data": ["priority", "assigned_worker", "crisis_mode"],
        "frequency": "real_time"
      }
    },
    "external_partners": {
      "housing_authority": ["case_status", "resource_need"],
      "county_health": ["medical_flags", "risk_scores"],
      "emergency_services": ["crisis_trigger", "priority_level"]
    },
    "token_hooks": ["LUCR_sync_compliance"]
  }
}
