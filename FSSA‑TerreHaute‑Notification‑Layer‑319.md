{
  "notification_layer": {
    "channels": {
      "internal": ["email", "system_alert", "dashboard_banner"],
      "external": ["sms", "email", "partner_api"],
      "crisis": ["priority_alert", "emergency_broadcast"]
    },
    "message_types": {
      "INTAKE": ["INTAKE_RECEIVED", "IDENTITY_PENDING", "DOCUMENTS_REQUIRED"],
      "ELIGIBILITY": ["ELIGIBILITY_COMPLETE", "VERIFICATION_FAILED", "REVIEW_REQUIRED"],
      "DISABILITY": ["ASSESSMENT_READY", "PLAN_APPROVED", "RESOURCE_ASSIGNED"],
      "EMPLOYMENT": ["SKILLS_COMPLETE", "JOB_MATCH_FOUND", "TECH_ASSIGNED"],
      "ROUTING": ["WORKER_ASSIGNED", "PRIORITY_UPDATED", "CRISIS_OVERRIDE"],
      "SYSTEM": ["TOKEN_CHECK", "DATA_MISMATCH", "AUDIT_TRIGGERED"]
    },
    "delivery_rules": {
      "priority_levels": {
        "low": "email",
        "medium": "system_alert",
        "high": "sms",
        "critical": "priority_alert"
      },
      "retry_policy": {
        "max_attempts": 3,
        "interval_minutes": 5
      }
    },
    "escalation": {
      "trigger_conditions": ["CRISIS_OVERRIDE", "VERIFICATION_FAILED", "RESOURCE_OVERLOAD"],
      "path": ["internal", "crisis", "external"],
      "strictness": "maximum"
    },
    "payload_format": {
      "notification_id": "string",
      "timestamp": "string",
      "agency": "string",
      "case_id": "string",
      "message": "string",
      "priority": "string",
      "crisis_mode": "boolean"
    },
    "compliance": {
      "lucr_hooks": ["notification_integrity", "priority_alignment", "override_logging"],
      "audit_required": true
    }
  }
}
