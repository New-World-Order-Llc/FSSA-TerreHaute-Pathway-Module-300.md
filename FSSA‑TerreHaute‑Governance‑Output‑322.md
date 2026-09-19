{
  "governance_output": {
    "outputs": {
      "compliance_summary": {
        "fields": ["case_id", "lucr_alignment", "audit_score", "integrity_score"],
        "format": "structured_object",
        "routing": "reporting_layer"
      },
      "decision_record": {
        "fields": ["case_id", "decision_path", "stage", "timestamp", "priority"],
        "format": "deterministic_log",
        "routing": "audit_log"
      },
      "crisis_directive": {
        "fields": ["override_reason", "resource_allocation", "priority_force"],
        "format": "crisis_packet",
        "routing": "notification_layer"
      },
      "routing_outcome": {
        "fields": ["assigned_worker", "priority_level", "override_flag"],
        "format": "routing_record",
        "routing": "routing_module"
      },
      "closure_certificate": {
        "fields": ["case_id", "final_status", "token_compliance", "timestamp"],
        "format": "closure_object",
        "routing": "archive"
      }
    },
    "lucr_hooks": ["governance_integrity", "priority_alignment", "override_logging"],
    "validation": {
      "required_fields": ["case_id", "timestamp"],
      "schema": "governance_output_v1"
    },
    "crisis_mode": {
      "enhanced_outputs": ["crisis_directive"],
      "strictness": "maximum"
    }
  }
}
