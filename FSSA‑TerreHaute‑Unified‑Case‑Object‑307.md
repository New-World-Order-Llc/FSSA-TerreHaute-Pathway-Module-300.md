{
  "case_object": {
    "case_id": "string",
    "applicant": {
      "id": "string",
      "name": "string",
      "dob": "string",
      "contact": {
        "phone": "string",
        "email": "string"
      }
    },
    "intake": {
      "program_requested": "string",
      "documents": ["string"],
      "timestamp": "string"
    },
    "eligibility": {
      "program": "string",
      "status": "string",
      "verification_flags": ["string"]
    },
    "disability_services": {
      "assessment_level": "string",
      "service_plan_id": "string"
    },
    "employment_support": {
      "skills_profile": ["string"],
      "job_match_score": "number"
    },
    "routing": {
      "assigned_worker": "string",
      "priority": "string",
      "crisis_mode": "boolean"
    },
    "audit": {
      "created_at": "string",
      "updated_at": "string",
      "token_hooks": ["LUCR_compliance"]
    }
  }
}
