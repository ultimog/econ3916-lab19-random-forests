# econ3916-lab19-random-forests
# Tree-Based Models: Random Forests

## Objective
I compared a random forest with a single tree and linear models, measured which features it relies on, and tuned it by cross-validation.

## Methodology
- I compared a single decision tree, OLS, Ridge and a random forest on California Housing, using the same training and test rows.
- I read the forest's out-of-bag score.
- I compared impurity (MDI) and permutation importance for the forest.
- I tuned max_depth and max_features by 3-fold cross-validation.
- I wrote my own prompt asking an AI for a feature-importance chart function, and checked its numbers against mine.

## Key Findings
- Test R² was 0.6228 for the single tree, 0.5758 for Ridge and 0.8046 for the forest. The tree scored a perfect 1.000 on its training rows: with 15,860 leaves for 16,512 rows, it memorized them.
- Latitude scored 0.0890 by MDI but 0.4427 by permutation: MDI undercounts features used in many small, deep splits.
- The tuned forest reached a test R² of 0.8094.
- My AI prompt took 2 rounds. Round 1 left out the permutation settings, so the AI used the defaults (5 shuffles, no seed) and its numbers were 0.4% to 11% off mine. Once round 2 stated 10 shuffles and seed 42, every number matched mine exactly.
