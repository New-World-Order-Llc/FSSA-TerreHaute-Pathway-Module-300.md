{
  "crisis_routing_engine": {
    "activation": {
      "trigger": ["system_flag", "manual_override", "external_alert"],
      "priority_levels": ["low", "medium", "high", "critical"]
    },
    "resource_allocation": {
      "dfr": ["expedited_eligibility", "emergency_food_support"],
      "bds": ["urgent_assessment", "rapid_service_plan"],
      "vr": ["immediate_job_support", "assistive_tech_fasttrack"]
    },
    "coordination": {
      "agencies": ["DFR", "BDS", "VR"],
      "shared_channels": ["intake_sync", "verification_sync", "routing_sync"],
      "external_partners": ["local_housing", "county_health", "emergency_services"]
    },
    "override_logic": {
      "case_lock": true,
      "worker_reassignment": "auto",
      "token_hooks": ["LUCR_emergency_compliance"]
    }
  }
}
