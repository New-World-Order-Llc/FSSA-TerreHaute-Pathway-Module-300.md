{
  "event_bus": {
    "channels": {
      "intake_events": ["INTAKE_CREATED", "IDENTITY_VERIFIED", "PROGRAM_SELECTED"],
      "eligibility_events": ["ELIGIBILITY_CHECKED", "VERIFICATION_FAILED", "STATUS_UPDATED"],
      "disability_events": ["ASSESSMENT_COMPLETED", "PLAN_CREATED", "RESOURCE_ASSIGNED"],
      "employment_events": ["SKILLS_ASSESSED", "JOB_MATCHED", "TECH_ASSIGNED"],
      "routing_events": ["WORKER_ASSIGNED", "PRIORITY_SET", "CRISIS_OVERRIDE_TRIGGERED"],
      "system_events": ["TOKEN_CHECK", "DATA_SCHEMA_VALIDATED", "CASE_OBJECT_UPDATED"]
    },
    "payload_format": {
      "event_id": "string",
      "timestamp": "string",
      "agency": "string",
      "case_id": "string",
      "details": "object",
      "priority": "string",
      "crisis_mode": "boolean"
    },
    "subscriptions": {
      "DFR": ["intake_events", "eligibility_events", "routing_events"],
      "BDS": ["disability_events", "system_events"],
      "VR": ["employment_events", "routing_events"],
      "external_partners": ["system_events", "routing_events"]
    },
    "crisis_escalation": {
      "trigger_events": ["CRISIS_OVERRIDE_TRIGGERED", "VERIFICATION_FAILED"],
      "escalation_path": ["routing_events", "system_events", "external_partners"],
      "strictness": "maximum"
    },
    "compliance": {
      "lucr_hooks": ["event_integrity", "priority_alignment", "override_logging"],
      "audit_required": true
    }
  }
}
