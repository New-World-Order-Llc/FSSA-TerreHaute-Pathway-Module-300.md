{
  "api_endpoints": {
    "intake": {
      "submit_application": "/api/fssa/intake/submit",
      "verify_identity": "/api/fssa/intake/verify"
    },
    "eligibility": {
      "check_snap": "/api/fssa/dfr/snap/check",
      "check_medicaid": "/api/fssa/dfr/medicaid/check",
      "check_tanf": "/api/fssa/dfr/tanf/check"
    },
    "disability_services": {
      "assessment": "/api/fssa/bds/assessment",
      "service_plan": "/api/fssa/bds/service-plan"
    },
    "employment_support": {
      "skills_assessment": "/api/fssa/vr/skills",
      "job_match": "/api/fssa/vr/job-match"
    },
    "routing": {
      "assign_worker": "/api/fssa/routing/assign",
      "crisis_override": "/api/fssa/routing/crisis"
    }
  }
}
