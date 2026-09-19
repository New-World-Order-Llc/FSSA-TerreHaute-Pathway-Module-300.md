{
  "compliance_grid": {
    "compliance_domains": {
      "intake": {
        "checks": ["identity_verification", "document_completeness", "timestamp_integrity"],
        "threshold": 0.97,
        "severity": "medium"
      },
      "eligibility": {
        "checks": ["rule_execution_accuracy", "verification_alignment", "priority_consistency"],
        "threshold": 0.98,
        "severity": "high"
      },
      "disability_services": {
        "checks": ["assessment_integrity", "resource_alignment", "service_plan_accuracy"],
        "threshold": 0.96,
        "severity": "high"
      },
      "employment_support": {
        "checks": ["skills_profile_accuracy", "job_match_integrity", "priority_alignment"],
        "threshold": 0.95,
        "severity": "medium"
      },
      "routing": {
        "checks": ["priority_assignment", "override_justification", "worker_load_balance"],
        "threshold": 0.99,
        "severity": "critical"
      }
    },
    "compliance_matrix": {
      "rows": ["intake", "eligibility", "disability_services", "employment_support", "routing"],
      "columns": ["data_integrity", "priority_integrity", "decision_integrity", "resource_integrity"],
      "scoring_method": "domain_weighted_sum"
    },
    "lifecycle_compliance": {
      "stages": {
        "INTAKE": ["identity_verification", "document_completeness"],
        "ELIGIBILITY": ["rule_execution_accuracy", "priority_consistency"],
        "DISABILITY": ["assessment_integrity", "resource_alignment"],
        "EMPLOYMENT": ["job_match_integrity", "skills_profile_accuracy"],
        "ROUTING": ["priority_assignment", "override_justification"]
      },
      "required_fields": ["case_id", "stage", "timestamp"]
    },
    "crisis_mode": {
      "enhanced_compliance": ["override_integrity", "resource_tracking", "priority_force_validation"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "compliance_report": {
        "fields": ["case_id", "compliance_score", "violations", "recommendations"],
        "routing": "reporting_layer"
      },
      "compliance_alert": {
        "fields": ["case_id", "violation_type", "severity"],
        "routing": "notification_layer"
      },
      "corrective_compliance_action": {
        "fields": ["case_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_compliance_reviews"]
    }
  }
}
