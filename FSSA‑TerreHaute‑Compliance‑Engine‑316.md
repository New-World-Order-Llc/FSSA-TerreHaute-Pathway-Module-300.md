{
  "compliance_engine": {
    "rules": {
      "intake": ["identity_verified", "documents_complete", "program_valid"],
      "eligibility": ["rule_validation_passed", "income_verified", "medical_need_confirmed"],
      "disability_services": ["assessment_valid", "plan_approved", "resources_assigned"],
      "employment_support": ["skills_profile_complete", "job_match_attempted"],
      "routing": ["priority_set", "worker_assigned", "override_logged"]
    },
    "validation": {
      "data_integrity_checks": ["schema_match", "field_presence", "type_validation"],
      "case_consistency": ["stage_alignment", "timestamp_order", "priority_logic"]
    },
    "audit_triggers": {
      "high_priority_cases": 40,
      "override_frequency": 0.10,
      "data_mismatch": true
    },
    "crisis_mode": {
      "enhanced_checks": ["override_reason_required", "resource_allocation_logged"],
      "strictness": "maximum"
    },
    "scoring": {
      "lucr_alignment": 0.0,
      "audit_score": 0.0,
      "integrity_score": 0.0,
      "formula": "weighted_sum(lucr_alignment, audit_score, integrity_score)"
    }
  }
}
