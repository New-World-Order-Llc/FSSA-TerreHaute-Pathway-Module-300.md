{
  "audit_log_spec": {
    "event_types": {
      "INTAKE": ["INTAKE_CREATED", "IDENTITY_VERIFIED", "PROGRAM_SELECTED"],
      "ELIGIBILITY": ["ELIGIBILITY_CHECKED", "VERIFICATION_FAILED", "STATUS_UPDATED"],
      "BDS": ["ASSESSMENT_COMPLETED", "PLAN_CREATED", "RESOURCE_ASSIGNED"],
      "VR": ["SKILLS_ASSESSED", "JOB_MATCHED", "TECH_ASSIGNED"],
      "ROUTING": ["WORKER_ASSIGNED", "PRIORITY_SET", "CRISIS_OVERRIDE_TRIGGERED"],
      "SYSTEM": ["TOKEN_CHECK", "DATA_SCHEMA_VALIDATED", "CASE_OBJECT_UPDATED"]
    },
    "fields": {
      "event_id": "string",
      "timestamp": "string",
      "actor": "string",
      "agency": "string",
      "case_id": "string",
      "details": "object",
      "lucr_compliance": "boolean"
    },
    "crisis_mode": {
      "enhanced_logging": true,
      "required_fields": ["priority_level", "override_reason", "resource_allocation"]
    },
    "retention": {
      "policy": "permanent",
      "backup_frequency": "daily"
    }
  }
}
