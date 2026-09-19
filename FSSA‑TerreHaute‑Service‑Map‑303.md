{
  "service_map": {
    "DFR": {
      "programs": ["SNAP", "TANF", "Medicaid"],
      "core_functions": ["eligibility", "verification", "case_routing"]
    },
    "BDS": {
      "programs": ["Disability Services", "Service Plans", "Long-Term Support"],
      "core_functions": ["assessment", "resource_allocation", "monitoring"]
    },
    "VR": {
      "programs": ["Employment Support", "Skills Assessment", "Assistive Tech"],
      "core_functions": ["job_matching", "training", "case_management"]
    },
    "coordination": {
      "shared_nodes": ["intake", "verification", "routing"],
      "crisis_mode": true
    }
  }
}
