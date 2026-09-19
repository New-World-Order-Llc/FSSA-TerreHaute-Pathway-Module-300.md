{
  "data_schema": {
    "intake": {
      "applicant_id": "string",
      "name": "string",
      "dob": "string",
      "program_requested": "string",
      "documents": ["string"]
    },
    "eligibility": {
      "program": "string",
      "status": "string",
      "verification_flags": ["string"]
    },
    "disability_services": {
      "assessment_level": "string",
      "service_plan_id": "string",
      "resources_assigned": ["string"]
    },
    "employment_support": {
      "skills_profile": ["string"],
      "job_match_score": "number",
      "assistive_tech": ["string"]
    },
    "routing": {
      "assigned_worker": "string",
      "priority": "string",
      "crisis_mode": "boolean"
    }
  }
}
