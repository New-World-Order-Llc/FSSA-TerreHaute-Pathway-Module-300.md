{
  "program_matrix": {
    "DFR": {
      "SNAP": {
        "eligibility": ["income_check", "household_size", "citizenship"],
        "outputs": ["food_assistance"],
        "routing": "standard"
      },
      "TANF": {
        "eligibility": ["income_check", "dependent_children"],
        "outputs": ["cash_assistance"],
        "routing": "enhanced"
      },
      "Medicaid": {
        "eligibility": ["income_check", "medical_need"],
        "outputs": ["health_coverage"],
        "routing": "medical_priority"
      }
    },
    "BDS": {
      "Disability_Assessment": {
        "eligibility": ["diagnosis", "functional_limitations"],
        "outputs": ["assessment_report"],
        "routing": "specialist"
      },
      "Service_Plan": {
        "eligibility": ["assessment_required"],
        "outputs": ["plan_document"],
        "routing": "resource_allocation"
      }
    },
    "VR": {
      "Skills_Assessment": {
        "eligibility": ["employment_goal"],
        "outputs": ["skills_profile"],
        "routing": "training"
      },
      "Job_Placement": {
        "eligibility": ["skills_profile"],
        "outputs": ["job_match"],
        "routing": "employer_network"
      }
    }
  }
}
