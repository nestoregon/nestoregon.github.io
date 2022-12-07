# Day 2: Rock Paper Scissors

Classic game we all love.

As input we’re given some cryptic data:

```bash
A Y
B X
C Z
```

The ************first************ letter indicates what the opponent elf (🧝) chose.

The **second** letter indicates what you (🤓) chose.

- `A` and `X` mean 🪨 which is worth `1` point
- `B` and `Y` means 🧻 which is worth `2` points
- `C` and `Z` means ✂️ which is worth `3` points

Perfect! Now:

- 🟢 **Win**: You get `6` points
- 🟡 **Tie**: You get `3` points
- 🔴 **Lose**: You get `0` points

## Differences

Let’s see how to code it:

1. We need to treat **rock-paper-scissors** as numbers:
    1. 🪨 is `1`
    2. 🧻 is `2`
    3. ✂️ is `3`
2. When evaluating two assignments, we need to know who won. How do we do this?
    1. Green arrow means winning
    2. Red arrow means losing
    3. Same number means tying

When evaluating the first expression:

- `A Y`, this means `1 2`. The difference between both is `1` (2-1)
- `B X`, this means `2 1`. The difference between both is `-1` (1-2)
- `C Z`, this means `3 3`. The difference between both is `0` (3-3)

To know which of you wins, you can compute the differences.

- Winning → `1` and `-2`
- Losing → `-1` and `2`
- Tying → Difference of `0`

![Untitled](Day%202%20Rock%20Paper%20Scissors%203a53980eb02a477786ad92216a17e3e4/Untitled.png)

Let’s see how to translate it into points:

- `A Y` → 🪨 VS 🧻 is `8` points (`6` for winning + `2` for your 🧻)
- `B X` → 🧻 VS 🪨 is `1` point (`0` for losing + `1` for your 🪨)
- `C Z` → ✂️ VS ✂️ is `6` points (`3` for tying + `3` for your ✂️)

**Total** = `15` (8 + 1 + 3)

- Difference of `1` → `6` points
- Difference of `2` → `0` points
- Difference of `0` → `3` points

### Schematic

![Untitled](Day%202%20Rock%20Paper%20Scissors%203a53980eb02a477786ad92216a17e3e4/Untitled%201.png)

The other question is:

What if we know the outcome (winning, losing, tying) and we want to get the play that we need to make?

For instance:

- `A Y` → 🪨 and 🟡. To tie you need to play 🪨. Total of `4` points (`3` for tying + `1` for your 🪨)
- `B X` → 🧻 and 🔴. To lose you need to play 🪨. Total of `2` points (`0` for losing + `1` for your 🪨)
- `C Z` → ✂️ and 🟢. To win you need to play 🪨. Total of (`6` for winning + `1` for your 🪨)

Total: `12 points`.

![Untitled](Day%202%20Rock%20Paper%20Scissors%203a53980eb02a477786ad92216a17e3e4/Untitled%202.png)