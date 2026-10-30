# MBHC tutoring history comparison materials

Data and code for *History Selection and Teacher Judgments in LLM Mathematics
Tutoring With Matched Input Budgets* by Tangfu Cen. The package contains teacher
judgment tables, four system prompts and scripts for the reported analyses.

Version 1.0.2 consolidates the declarations. Research data, prompts and code are
unchanged from version 1.0.1.

Download [version 1.0.2](mbhc-tutoring-history-v1.0.2.zip) and extract the archive
before running the commands below. The declarations are also available in
[DECLARATIONS.md](DECLARATIONS.md).

## Reproduce the analyses

Use Python 3.10 or later. Point estimates require only the standard library.
Run these commands from the package directory:

    python code/test_synthetic.py
    python code/reproduce.py --out replay

For the exploratory percentile intervals, install the NumPy version listed in
requirements-bootstrap.txt, then run:

    python code/reproduce.py --out replay_bootstrap --bootstrap

Choose output directories that do not already exist. The scripts run locally
without network access, model calls or access to the original project. Check
file integrity with `python code/verify_manifest.py`.

## Files and coverage

| Directory | Contents |
| --- | --- |
| data/ | Teacher judgments, paired contrasts, coverage counts and diagnostic codes |
| prompts/ | Four frozen system prompts |
| code/ | History selector, analysis scripts and synthetic tests |
| expected/ | Archived numerical values checked during reproduction |
| LICENSES/ | MIT and CC BY 4.0 licence texts |

The analyses cover Tables 2-7, Figure 4 student-level and leave-one-out values,
the 18-conversation distinct-input subset, all 24 follow-up contrasts, and the
attribution and evidence-support counts. Figure 3 is represented by disposition
counts. Figures 1 and 2 are conceptual; Figure 5 uses case excerpts excluded
from this package. Table 1 defines the rating dimensions.

DATA_DICTIONARY.md describes each file and field. All teachers, seeds, uncertain
labels and negative or zero contrasts are retained. Aliases identify conditions
that used the same generated output.

## Interpretation

S/C/O/T codes replace the original identifiers. Teacher A/B match the manuscript.
The original actual-input, common-reference and follow-up rating rounds remain
separate. Prior exposure, revisions and manual transcription from handwritten
judgments limit comparisons across rounds. Numerical reproduction cannot
establish rating independence, transcription accuracy or pedagogical validity.
Labels were not changed for release.

The diagnostic tables contain post-review categorical coding without independent
teacher validation. Categories may overlap. The workflow and assistance are
disclosed in DECLARATIONS.md. The private source mapping is
omitted, so the per-action table alone cannot reconstruct transitions across
seeds. Source text is also needed to assess cutpoints and support semantics or
reconstruct complete model inputs. The synthetic selector tests use invented
strings and costs; these are not study observations or native token counts.

Repeated outputs do not add independent participants. Bootstrap intervals are
exploratory and assume independent conversations despite missing student
identities. The checks were run in separate local processes, without independent
replication by another research team.

## Privacy and access

The package excludes raw dialogue, question text, model answers, teacher
explanations, handwriting, personal names, original source identifiers,
personal timestamps, filesystem paths and the private identifier mapping.
Pseudonymization reduces disclosure risk but does not guarantee irreversible
anonymity. The original datasets remain subject to their providers' terms.
The author confirmed sharing of these de-identified materials. No institutional
ethics review or waiver was obtained for the reported study.

## Citation and licences

Creator: Tangfu Cen. Cite the repository and the exact Git commit used.
CITATION.cff contains the citation metadata. No DOI has been assigned.

https://github.com/zxu351966-gif/mbhc-tutoring-history

Code in code/ is licensed under MIT. Data, expected values, prompts and authored
documentation are licensed under CC BY 4.0. See LICENSE_SCOPE.md and LICENSES/.
The licences do not cover excluded third-party materials or confer additional
privacy permissions.
