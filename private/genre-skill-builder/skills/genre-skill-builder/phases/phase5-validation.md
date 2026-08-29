# Phase 5: Validation & Testing

You are executing Phase 5 of the genre-skill-builder workflow. Your goal is to verify the generated skill's quality and optionally test it with sample input.

## Why This Phase Matters

Validation catches errors before the skill is used. A skill with incorrect benchmarks, mismatched cluster definitions, or broken file references will mislead users. This phase ensures quality and builds confidence.

## Inputs

Before starting, read:
1. All files in `/output/plugins/[skill-name]/`
2. `/analysis/phase3-clusters/cluster-benchmarks.json` - Source data
3. `/analysis/phase4-generation/generation-log.md` - Generation decisions
4. The model skill (for comparison)

## Your Tasks

### 1. Syntax Validation

Check all files for correct formatting:

**YAML frontmatter**:
```bash
# Each SKILL.md must have valid YAML
---
name: skill-name
description: Description here
---
```

- [ ] SKILL.md has valid YAML frontmatter
- [ ] Name matches plugin.json
- [ ] Description is present and reasonable length

**JSON files**:
- [ ] plugin.json is valid JSON
- [ ] All required fields present (name, version, description, skills)

**Markdown structure**:
- [ ] All headers use consistent levels (# for title, ## for sections)
- [ ] All tables have valid markdown syntax
- [ ] All code blocks are properly fenced

### 2. Data Accuracy Validation

Verify benchmarks match analysis data:

```markdown
## Benchmark Verification

### SKILL.md Statistics
| Metric | In SKILL.md | In Analysis | Match? |
|--------|-------------|-------------|--------|
| Median word count | [X] | [Y] | [✓/✗] |
| Median paragraphs | [X] | [Y] | [✓/✗] |
| [Other metrics...] | ... | ... | ... |

### Cluster Prevalences
| Cluster | In SKILL.md | In Analysis | Match? |
|---------|-------------|-------------|--------|
| [Cluster 1] | [X]% | [Y]% | [✓/✗] |
| [Cluster 2] | [X]% | [Y]% | [✓/✗] |
```

Flag any discrepancies for correction.

### 3. Cluster Coverage Validation

Verify all clusters are properly documented:

```markdown
## Cluster Coverage

| Cluster | In SKILL.md | Has Profile | Has Exemplar | Complete? |
|---------|-------------|-------------|--------------|-----------|
| [Cluster 1] | ✓ | ✓ | ✓ | ✓ |
| [Cluster 2] | ✓ | ✓ | ✓ | ✓ |
```

- [ ] All clusters mentioned in SKILL.md have profile files
- [ ] All cluster profiles have benchmarks section
- [ ] All cluster profiles have signature moves
- [ ] All cluster profiles have exemplars
- [ ] Decision tree covers all clusters

### 4. Internal Consistency Validation

Check cross-file consistency:

**Naming consistency**:
- [ ] Cluster names match across SKILL.md and cluster profile filenames
- [ ] Skill name matches across all files
- [ ] Phase names match between SKILL.md and phase files

**Reference integrity**:
- [ ] All file references in SKILL.md point to existing files
- [ ] Technique guide references match actual technique files
- [ ] Cluster guide references match actual cluster files

**Phase flow**:
- [ ] Phase numbers are sequential
- [ ] Phase goals align with overall workflow
- [ ] Pause points are marked

### 5. Content Quality Validation

Assess the quality of generated content:

**SKILL.md quality**:
- [ ] Introduction clearly explains what the skill does
- [ ] Core principles are specific to this genre (not generic)
- [ ] Key statistics are prominently displayed
- [ ] Cluster decision tree is actionable
- [ ] Model recommendations are appropriate

**Cluster profile quality**:
- [ ] Each cluster has distinctive characteristics
- [ ] Signature moves include concrete examples
- [ ] Prohibited moves explain why to avoid
- [ ] Checklists are actionable

**Technique guide quality**:
- [ ] Techniques are specific to this section type
- [ ] Examples are from the corpus (not invented)
- [ ] Quick references are usable

### 6. Comparison to Model Skill

Compare generated skill to its model:

```markdown
## Model Skill Comparison

### Structure Match
| Component | Model Skill | Generated Skill | Match? |
|-----------|-------------|-----------------|--------|
| Phase count | [n] | [n] | [✓/✗] |
| Cluster count | [n] | [n] | [✓/✗] |
| Technique guides | [n] | [n] | [✓/✗] |

### Quality Comparison
- [ ] SKILL.md is similar length and depth
- [ ] Cluster profiles have comparable detail
- [ ] Phase files follow same structure
- [ ] Technique guides have similar comprehensiveness

### Intentional Differences
[Document any deliberate departures from model and why]
```

### 7. Marketplace Validation

Run the same validation that CI uses to ensure the plugin will pass automated checks:

```python
# Run this validation script before pushing
import json
from pathlib import Path

# Paths - adjust skill_name as needed
skill_name = "[skill-name]"
plugin_root = Path(f"output/plugins/{skill_name}")
manifest = plugin_root / ".claude-plugin" / "plugin.json"

# Check 1: plugin.json exists
if not manifest.exists():
    print(f"❌ CRITICAL: Missing {manifest}")
else:
    manifest_data = json.loads(manifest.read_text())

    # Check 2: Name matches
    if manifest_data.get("name") != skill_name:
        print(f"❌ CRITICAL: plugin.json name '{manifest_data.get('name')}' doesn't match '{skill_name}'")
    else:
        print(f"✓ Name matches: {skill_name}")

    # Check 3: Skills is a string path (NOT an array)
    skills_path = manifest_data.get("skills")
    if not skills_path:
        print("❌ CRITICAL: plugin.json missing 'skills' field")
    elif isinstance(skills_path, list):
        print("❌ CRITICAL: 'skills' must be a string path (e.g., './skills/'), not an array")
    elif not (plugin_root / skills_path).exists():
        print(f"❌ CRITICAL: skills path '{skills_path}' doesn't exist")
    else:
        print(f"✓ Skills path valid: {skills_path}")

# Check 4: Validate marketplace entry format
marketplace_entry = Path(f"analysis/phase4-generation/marketplace-entry.json")
if marketplace_entry.exists():
    entry = json.loads(marketplace_entry.read_text())
    if entry.get("strict") is not True:
        print("❌ CRITICAL: marketplace entry must have 'strict': true")
    else:
        print("✓ Marketplace entry has strict: true")
    if not entry.get("source", "").startswith("./plugins/"):
        print(f"❌ WARNING: source should be './plugins/{skill_name}'")
    else:
        print(f"✓ Source path correct")
```

**Checklist**:
- [ ] `plugin.json` exists at correct location
- [ ] `plugin.json` name matches skill name
- [ ] `plugin.json` has `"skills": "./skills/"` (string, not array)
- [ ] Skills directory exists at that path
- [ ] Marketplace entry has `"strict": true`
- [ ] Marketplace entry has correct source path

**Common Errors to Avoid**:
| Wrong | Correct |
|-------|---------|
| `"skills": [{"name": "...", "path": "..."}]` | `"skills": "./skills/"` |
| `"strict": false` or missing | `"strict": true` |
| `"source": "plugins/..."` | `"source": "./plugins/..."` |

### 8. Optional: Test Run

If the user provides a sample article or writing task, test the skill:

```markdown
## Test Run Results

### Test Input
- **Task**: [What user asked skill to help with]
- **User's draft/notes**: [What they provided]

### Skill Application
1. **Cluster identification**: Applied decision tree → [Cluster X]
2. **Benchmark check**: User's draft has [n] words vs. target [range]
3. **Guidance relevance**: [How well did cluster guidance apply?]

### Issues Identified
- [Any problems encountered during test]
- [Guidance that didn't quite fit]
- [Missing elements]

### Test Verdict
[Pass / Pass with notes / Needs revision]
```

### 9. Generate Validation Report

Compile all findings:

```markdown
# Validation Report: [Skill Name]

## Summary
- **Files generated**: [n]
- **Validation checks passed**: [n]/[total]
- **Critical issues**: [n]
- **Minor issues**: [n]
- **Overall status**: [Ready / Needs revision]

## Critical Issues (must fix)
1. [Issue description and location]
2. [Issue description and location]

## Minor Issues (should fix)
1. [Issue description and location]
2. [Issue description and location]

## Warnings (consider fixing)
1. [Issue description and location]

## Verified Components
- [x] plugin.json valid
- [x] plugin.json uses string skills path (not array)
- [x] Marketplace entry has strict: true
- [x] SKILL.md structure correct
- [x] All cluster profiles present
- [x] Benchmarks accurate
- [x] [etc.]

## Recommendations
[Final recommendations for the skill]
```

## Output Files to Create

Save all outputs to `/analysis/phase5-validation/`:

1. **validation-report.md** - Complete validation findings

2. **benchmark-verification.md** - Data accuracy checks

3. **consistency-check.md** - Cross-file consistency results

4. **test-run-results.md** - Test results (if test was run)

5. **corrections-needed.md** - List of issues to fix (if any)

## Issue Severity Definitions

**Critical** (must fix before use):
- Incorrect benchmarks that would mislead users
- Missing cluster profiles
- Broken file references
- Invalid JSON/YAML
- plugin.json uses array for skills (must be string path)
- Marketplace entry missing `strict: true`

**Minor** (should fix):
- Inconsistent capitalization
- Missing examples in technique guides
- Vague guidance in cluster profiles

**Warning** (consider fixing):
- Cluster with very low prevalence (<10%)
- Unusually long/short files compared to model
- Missing optional components

## Guiding Principles

1. **Accuracy over completeness**: Better to flag an issue than let errors through.

2. **User perspective**: Would a user following this skill get good results?

3. **Compare to model**: Significant departures from model skill need justification.

4. **Document everything**: Even minor issues should be noted for future reference.

5. **Test if possible**: Real-world testing reveals problems validation misses.

## When You're Done

Return a summary to the orchestrator that includes:
1. Overall validation status (Ready / Needs revision)
2. Critical issues count and description
3. Minor issues count
4. Files verified
5. Benchmark accuracy confirmed
6. Marketplace validation passed (plugin.json format, strict: true)
7. Test results (if tested)
8. Recommendations for improvement
9. Next steps (fix issues / finalize / publish)

If issues were found, provide specific guidance on what to fix before the skill is ready for use.
