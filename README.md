# Dice Toolkit

A browser-based toolkit for exploring tabletop dice-pool probabilities and rolling custom dice pools. The site is built with plain HTML, CSS, and JavaScript; no build step or external dependencies are required.

## Tools

- **Probability Explorer** — adjust die sides, pool size, and target number to view exact and cumulative probabilities.
- **Dice Pool Roller** — roll a custom pool, reroll individual dice, and compare the result with the probability distribution.

## Run locally

Open [index.html](index.html) in a browser. The two tools are also available directly:

- [Probability Explorer](dice_pool_probability_distribution_visualizer.html)
- [Dice Pool Roller](custom_dice_pool_roller_probability_visualizer.html)

## Probability method

For an `n`-sided die with a target of `above_num` or higher, the per-die success probability is:

```text
p = (n + 1 - above_num) / n
```

For `total_dice` independent rolls, the probability of exactly `i` successes is the binomial distribution:

```text
P(X = i) = C(total_dice, i) * p^i * (1 - p)^(total_dice - i)
```

The method is based on the Python example shared by Bob Klemm:
[dice_rolling.py](https://github.com/rjklemm/Python-math-and-physics-projects-2024-to-present/blob/main/dice_rolling.py).

## Deployment

The repository includes a GitHub Actions workflow at `.github/workflows/pages.yml` to deploy the static site to GitHub Pages when changes are pushed to `main`. In the repository settings, configure **Pages → Build and deployment → Source** to **GitHub Actions** if it is not already enabled.
