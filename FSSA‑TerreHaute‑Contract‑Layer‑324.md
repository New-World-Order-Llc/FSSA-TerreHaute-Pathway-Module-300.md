{
  "contract_layer": {
    "contracts": {
      "DFR_to_BDS": {
        "obligations": ["provide_eligibility_status", "forward_disability_flags"],
        "response_time_hours": 4,
        "data_fields": ["case_id", "eligibility_status", "medical_flags"],
        "crisis_override": true
      },
      "BDS_to_VR": {
        "obligations": ["deliver_assessment", "provide_service_plan"],
        "response_time_hours": 6,
        "data_fields": ["case_id", "assessment_score", "service_plan"],
        "crisis_override": false
      },
      "VR_to_Routing": {
        "obligations": ["submit_job_match", "update_skills_profile"],
        "response_time_hours": 2,
        "data_fields": ["case_id", "job_match_score", "priority_recommendation"],
        "crisis_override": true
      },
      "Routing_to_CaseManagement": {
        "obligations": ["assign_worker", "set_priority"],
        "response_time_hours": 1,
        "data_fields": ["case_id", "assigned_worker", "priority_level"],
        "crisis_override": true
      }
    },
    "external_partner_contracts": {
      "county_health": {
        "obligations": ["provide_medical_flags", "risk_scores"],
        "response_time_hours": 12,
        "crisis_override": true
      },
      "housing_authority": {
        "obligations": ["resource_availability", "case_support_status"],
        "response_time_hours": 24,
        "crisis_override": false
      }
    },
    "escalation_clauses": {
      "trigger_conditions": ["missed_deadline", "data_mismatch", "priority_conflict"],
      "path": ["division_manager", "routing_director", "governance_kernel"],
      "strictness": "maximum"
    },
    "compliance": {
      "lucr_hooks": ["contract_integrity", "priority_alignment", "override_logging"],
      "audit_required": true
    }
  }
}
