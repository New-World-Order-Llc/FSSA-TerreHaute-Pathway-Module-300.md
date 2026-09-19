{
  "reporting_layer": {
    "dashboards": {
      "intake": {
        "metrics": ["processing_time", "verification_accuracy", "document_rate"],
        "refresh_rate": "real_time"
      },
      "eligibility": {
        "metrics": ["validation_accuracy", "error_rate", "reverification_cycle"],
        "refresh_rate": "hourly"
      },
      "disability_services": {
        "metrics": ["assessment_time", "plan_accuracy", "resource_speed"],
        "refresh_rate": "daily"
      },
      "employment_support": {
        "metrics": ["skills_accuracy", "job_match_score", "placement_rate"],
        "refresh_rate": "daily"
      },
      "routing": {
        "metrics": ["assignment_speed", "priority_alignment", "crisis_efficiency"],
        "refresh_rate": "real_time"
      }
    },
    "aggregation_rules": {
      "method": "deterministic",
      "weighting": {
        "intake": 0.15,
        "eligibility": 0.20,
        "disability_services": 0.20,
        "employment_support": 0.20,
        "routing": 0.25
      }
    },
    "lifecycle_summary": {
      "fields": ["case_id", "stage", "timestamp", "priority", "crisis_mode"],
      "output_format": "structured_object"
    },
    "crisis_indicators": {
      "flags": ["high_priority_cases", "resource_overload", "override_frequency"],
      "thresholds": {
        "high_priority_cases": 50,
        "resource_overload": 0.85,
        "override_frequency": 0.10
      }
    },
    "compliance": {
      "lucr_alignment": "boolean",
      "audit_score": "number",
      "data_integrity": "number"
    }
  }
}
