{
  "harmonic_stability_grid": {
    "harmonic_domains": {
      "operational_harmony": {
        "checks": ["load_wave_balance", "queue_oscillation_dampening", "processing_rhythm_alignment"],
        "threshold": 0.93,
        "severity": "high"
      },
      "data_harmony": {
        "checks": ["sync_wave_integrity", "timestamp_phase_alignment", "schema_resonance"],
        "threshold": 0.97,
        "severity": "critical"
      },
      "decision_harmony": {
        "checks": ["rule_path_phase_match", "override_wave_consistency", "audit_resonance"],
        "threshold": 1.0,
        "severity": "critical"
      },
      "resource_harmony": {
        "checks": ["allocation_wave_balance", "crisis_pool_resonance", "priority_force_phase_control"],
        "threshold": 0.92,
        "severity": "high"
      }
    },
    "harmonic_patterns": {
      "pattern_alpha": {
        "modules": ["intake", "eligibility", "bds"],
        "alignment": "tri‑phase",
        "frequency": "continuous"
      },
      "pattern_beta": {
        "modules": ["vr", "routing"],
        "alignment": "dual‑phase",
        "frequency": "real_time"
      },
      "pattern_gamma": {
        "modules": ["all_divisions"],
        "alignment": "full‑system resonance",
        "frequency": "event_triggered"
      }
    },
    "oscillation_dampening": {
      "triggers": ["load_spike", "sync_variance", "override_anomaly"],
      "actions": ["priority_lock", "resource_freeze", "fallback_routing"],
      "auto_trigger": true
    },
    "harmonic_scoring": {
      "metrics": ["operational_harmony", "data_harmony", "decision_harmony", "resource_harmony"],
      "weights": {
        "operational_harmony": 0.25,
        "data_harmony": 0.3,
        "decision_harmony": 0.3,
        "resource_harmony": 0.15
      },
      "formula": "weighted_sum(metrics, weights)"
    },
    "harmonic_stages": {
      "stage_1_alignment": {
        "checks": ["phase_match", "sync_integrity", "load_wave_balance"],
        "frequency": "continuous"
      },
      "stage_2_resonance": {
        "actions": ["rule_path_alignment", "priority_phase_control", "resource_wave_balance"],
        "frequency": "real_time"
      },
      "stage_3_stabilization": {
        "actions": ["audit_resonance_repair", "integrity_rebuild", "module_phase_normalization"],
        "frequency": "post_event"
      }
    },
    "crisis_mode": {
      "enhanced_harmony": ["priority_force_mode", "governance_kernel_direct_control", "resource_emergency_pool"],
      "strictness": "maximum",
      "required_fields": ["override_reason", "risk_level", "resource_allocation"]
    },
    "outputs": {
      "harmonic_report": {
        "fields": ["event_id", "harmonic_score", "actions_taken", "lucr_alignment"],
        "routing": "reporting_layer"
      },
      "harmonic_alert": {
        "fields": ["event_id", "failure_type", "severity"],
        "routing": "notification_layer"
      },
      "harmonic_recovery_action": {
        "fields": ["event_id", "required_actions", "deadline"],
        "routing": "enforcement_layer"
      }
    },
    "lucr_alignment": {
      "checks": ["priority_integrity", "decision_consistency", "audit_logging"],
      "required_for": ["all_harmonic_events"]
    }
  }
}
