# Overlap Map

Controls which agent owns which files. Three states: exclusive | shared | contested

| File | Owner | State |
|------|-------|-------|
| src/SUMMARY.md | editor_in_chief | exclusive |
| _agent_config/overlap_map.md | editor_in_chief | exclusive |
| src/README.md | editor_in_chief | exclusive |
| src/01-Introduction.md | consultant_ceo | exclusive |
| src/02-AI_Inputs.md | lead_researcher | exclusive |
| src/03-AI_Outputs.md | lead_researcher | exclusive |
| src/04-AI_Incarnations.md | consultant_ceo | exclusive |
| src/05-AI_Creators.md | lead_researcher | exclusive |
| src/06-History_Information_Privacy.md | lead_researcher | exclusive |
| src/07-Industry_specific_advice.md | lead_researcher | exclusive |

## Rules
- exclusive: agent writes directly to main
- shared: all owners must coordinate; branch + PR required
- contested: Editor-in-Chief arbitrates; branch + PR required
