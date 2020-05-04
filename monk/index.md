## The Monk

The Monk is a fairly interesting class: one of the four martial
characters in the original Player's Handbook, it uses a magic-like
resource named "ki" to fuel it's defensive, mobility, and crowd-control
abilities, as well as a single offensive ability, "Flurry of Blows".

At level 3 of the Monk class, you choose a subclass, each of which has
unique features. We'll look at those subclasses here.

### Caveats

We're not trying to determine which Monk subclass are "better". This is
simply an analysis of the subclasses' potential damage output to get a
feel for what each subclass can do in combat. This analysis doesn't
touch the role playing, exploration, social, or skill aspects of any
class.

Even within combat, this analysis only address damage output, and says
nothing about any non-damage goals of combat; if you're fighting as a
delaying tactic, an escort mission, or to impress a noble, damage might
not be that important. It also doesn't track damage _input_, which is
important to the **d8** hit-dice Monk. It doesn't look at tactics or
non-damage effects, which can be a bigger factor than raw damage.

Finally, the numbers presented here might not match what you'd see in a
real game. In our simple model, the world and enemies have fixed
properties, and our character tactics are basic; an actual game is fluid
and nuanced, with unpredictable turns that can drastically change any
outcome. We shouldn't think of the modeling here as being
representative, but rather as merely indicative of what is possible.

### Model

#### Description

We model simplified multi-round combats, where a Monk character performs
actions on each round, some of which may result in some damage done to
an enemy. Specific enemy characters are not tracked; only a generic AC,
saving throw, and damage done to an enemy; death and overkill is not
tracked. Enemies don't take actions except for the occasional saving
throw.

Character resources, such as per-turn and per-rest resources _are_
tracked. For the Monk, this usually comes down to tracking **ki** and
features that have limited use per turn. Each combat begins with a
fully-rested character; resource depletion for the characters is not
examined, but can be partially seen in the effects for long combats.

Features that can only be used under specific conditions, such as
on-hit, on-miss, or by taking a specific action or bonus action are also
tracked, including actions that can only be done in conjunction with a
specific type of attack (weapon, unarmed, etc).

Resolutions are resolved by a random numbers, just as they are in a real
game. Once the combat is complete, total damage output from the Monk for
that round is tallied, and the damage/round is calculated. Typically,
1000 combats are run and averaged for each data point. With 6
subclasses, 20 levels, 5 difficulty settings, and 3 combat lengths, a
total of 1.8 million combats are simulated to find our results.

#### Features

We model only class features that have a direct impact on damage. This
includes the following:

- _Monk_ base class ("Monk"):
  - Martial Arts
  - Ki (resource and "Flurry of Blows")
  - Monastic Tradition (compared)
  - Ability Score Improvement (see "Assumptions" below)
  - Extra Attack

- _Way of the Astral Self_ ("Astral Monk"):
  - Arms of the Astral Self (Wisdom substitution and bonus attacks)
  - Awakening of the Astral Self (Empowered Arms)
  - Complete Astral Self (Astral Barrage)

- _Way of the Argent Fist_ from Morgrave Miscellany ("Argent Monk")
  - Wrath of the Argent
  - Radiant Embrace (expanded critical range)

- _Way of the Kensei_ ("Kensei Monk")
  - Path of the Kensei (using a Kensei weapon: longsword)
  - One with the Blade (Deft Strike)
  - Sharpen the Blade
  - Unerring Accuracy

- _Way of Mercy_ ("Mercy Monk")
  - Hands of Harm
  - Noxious Aura (aura damage, 1 creature)

- _Way of Shadow_ ("Shadow Monk")
  - Opportunist

- _Way of the Drunken Master_ (not included)

- _Way of the Four Elements_ (not included)

- _Way of the Long Death_ (not included)

#### Assumptions

We model the primary / secondary Monk abilities with the following
modifiers. This is typical of a point-buy or basic array Monk creation
for races that have a good ability synergy, and where the Ability Score
Improvement (ASI) at levels 4, 8, 12, and 16 are used to improve the
Monk's primary, and then secondary abilities.
  - Level 1: 3 / 2
  - Level 4: 4 / 3
  - Level 8: 5 / 3
  - Level 12: 5 / 4
  - Level 16: 5 / 5

Most subclasses use **Dexterity** / **Wisdom** for these stats, but the
Astral Monk has those reversed: **Wisdom** / **Dexterity**, since the
flavor and mechanics of that subclass seem to push for a stronger wisdom
focus.

For situations where damage can be optimized by the actions of the
party, we generally assume that these are granted. As examples, we
generously assume the enemy is poisoned or incapacitated for the Mercy
Monk's "Hands of Harm" feature, and that one enemy is within range of
her "Noxious Aura". Shadow Monks always get their "Opportunist"
reaction, and Kensei monks always fight with a longsword.

The exception to this rule is that monks never get opportunity attacks.
This is done to provide a contrast to the "Opportunist" feature, which
is damage-wise an easier-to-obtain version of an opportunity attack.

On the other side, situations which are largely out of the party's hands
are **not** granted. So the Argent Monk doesn't get double "Wrath of the
Argent" damage from attacking undead, and the Shadow Monk can't teleport
and get advantage on every round.

In our program the monk goes first every round; this doesn't affect
much, except that it adds an some points of "Noxious Aura" damage at the
end of the last round.

#### Tactics

The Monk tactics in this analysis are very simple:

- On the first round, if they can use some feature that provides a bonus
  to damage or change to hit, they use that feature first. This includes
  things like the Kensei Monk's "Sharpen the Blade" or the Mercy Monk's
  "Noxious Aura".
- If possible, they'll make an Attack action, making the maximum number
  of attacks. Kensei Monks use a versatile longsword (**1d10**) for this
  attack, and Astral Monks use their arm weapon. All other monks use a
  versatile quarterstaff (**1d8**) until level 11, when their unarmed
  strike damage catches up.
- If they can, they'll spend a ki point and make a "Flurry of Blows"
  attack as a bonus action.
  - Exception: at level 3 and higher, the Astral Monk uses the bonus
    attack(s) provided by her "Arms of the Astral Self" feature instead
    of "Flurry of Blows".
- If they can't use the above attack, they'll instead use their "Martial
  Arts" single unarmed attack on your bonus action, if they can.
- Whenever they can use a feature that can do additional damage or can
  improve the chance to do damage, they'll use that feature. This
  includes the "Opportunist" reaction, as well as on-hit abilities like
  "Deft Strike" or "Hands of Harm".

### Variables

There are four input variables that are modelled:

**Subclass:** We currently have 5 subclasses (Argent, Astral, Kensei,
Mercy, and Shadow) in the model, as well as a "pure" monk (that doesn't
use any subclass features) for comparison.

**Class Level:** We model all levels 1-20 for all subclasses.

**Difficulty:** We represent the difficulty setting (**DS**) with a
number 0-20, and include 5 such settings in our analysis: 0, 5, 10, 15,
and 20. This is used to simulate the strength of enemy creatures that a
monk might find at their respective levels. The DS affects enemy AC and
saving throws ("Noxious Aura" damage is the only feature modeled so far
that uses an enemy's saving throw).

  - The enemy AC is equal to
    ```
    (Monk's primary mod) + (Monk's prof. bonus) + DS
    ```
    This means that most Monks will require to roll on the d20 equal to
    the DS to hit the enemy.
  - Enemies receive a bonus to their saving throw equal to
    ```
    (Monk's secondary mod) + (Monk's prof. bonus) + DS - 13
    ```
    So, enemies will make their saving throw against most Monks if they
    roll a `(21 - DS)` on the d20. (They'll need to roll an 11 at DS 10,
    a 6 at DS 15, etc.)
  - At **DS 0**, Monk attacks always hit, and enemies never make their
    saving throw, regardless of any other factor.

**Combat Length:** Our analysis includes three different combat lengths:
1 round, 5 rounds, and 10 rounds of combat. The typical combat in my
games runs around 4-6 rounds, so a 1-round combat is short, while a
combat that stretches out to 10 rounds is quite long. Most players will
gauge how long a combat might take at the outset, and adjust their
tactics accordingly. However, in the analysis presented here, the Monk's
tactics are unaffected by combat length.

Combat lengths longer than 10 rounds are not modelled, mostly because we
don't yet have a way to track the expiration of activated features, and
haven't written tactics for dealing with them.

### Output

I present the model here as a set of 15 graphs for the 5 difficulty
settings times 3 combat lengths: each graph contains a single plot line
for each subclass that models its average per-round combat damage over
all the levels of its life.

[Here](bigpicture.md) is a link to the final graph output.

## Future work

If we continue doing this, we hope to finish modelling more subclasses
of the Monk class, as well as compare it to other D&D classes. Some
class features provide spell or spell-like abilities, which are
difficult to model because their damage is highly situational, but we
can probably make some baseline assumptions.

We'd also like to model different situations: what happens if the Mercy
Monk doesn't always get their triple dice from "Hands of Harm"? What if
we include opportunity attacks in the model?

Finally, we'd like to play with different tactics. While we can never
include the wide range of strategies available to an experienced player,
we can probably make our Monk programs somewhat more intelligent.
