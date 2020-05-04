## The Monk

The Monk is a fairly interesting class: one of the four martial
characters in the original Player's Handbook, it uses a pseudo-magical
resource named "ki" to fuel it's defensive, mobility, and crowd-control
abilities, as well as a single offensive ability, "Flurry of Blows",
which lets you perform two unarmed strikes as a bonus action at level 2.

At level 3 of the Monk class, you choose a subclass. Some subclasses add
spending ki to improve its offensive capabilities. I'll look at those
here.

### Caveats

I'm not trying to determine which Monk subclass is "better" (whatever
that means). This is simply a model analysis of the subclasses' damage
output and damage strategies at various levels in order to get a feel
for what the subclass can do in combat. This analysis doesn't touch the
role playing, exploration, social, or skill challenge aspects of the
class.

Even within combat, this analysis only address damage output, and says
nothing about possible non-damage goals of combat; if you're fighting as
a delaying tactic, an escort mission, or to impress a noble, damage
might not be that important. It doesn't model damage _input_, which is
usually important to a Monk, which only has **d8** hit dice. It's
doesn't look at tactics or non-damage effects, which can often have a
bigger effect on combat success than raw damage.

Finally, even damage output might not be match a real table. The world
and enemies are considered to have fixed properties, and the strategy
for dealing is to do the most damage at any moment. Assumptions about
terrain, mobility, lighting, enemy types, party are all static and
simple. We shouldn't think of the modeling here as being representative,
but rather as merely indicative of what kind of damage is possible.

### Model

#### Description

I modeled simplified multiple round combats, where a character performs
actions on each round, which may result in some damage done to an enemy.
Specific enemy characters are not tracked; only a generic AC, saving
throw, and effectively infinite pool of HP is considered. Enemies don't
take actions, except saving throws where appropriate.

Character resources, such as per-turn and per-rest resources are
tracked. For the Monk, this usually comes down to tracking **ki** and
specific abilities that are specified as once or more per turn. Each
combat begins with a fully-rested character; depletion is (somewhat)
modelled using longer combats.

Features that can only be used under specific conditions, such as
on-hit, on-miss, or by taking a specific action or bonus action are
tracked, including actions that can only be done with a specific type of
attack (weapon, unarmed, etc).

#### Features

I only modeled features that have a direct impact on damage. This
includes the following:

- _Monk_ base class ("monk"):
  - Martial Arts
  - Ki (resource and "Flurry of Blows")
  - Monastic Tradition (compared)
  - Ability Score Improvement (see "Assumptions" below)
  - Extra Attack

- _Way of the Astral Self_ subclass ("astral"):
  - Arms of the Astral Self (Wisdom substitution and bonus attacks)
  - Awakening of the Astral Self (Empowered Arms)
  - Complete Astral Self (Astral Barrage)

- _Way of the Argent Fist_ (from Morgrave Miscellany) ("argent")
  - Wrath of the Argent
  - Radiant Embrace (expanded critical range)

- _Way of the Kensei_ subclass ("kensei")
  - Path of the Kensei (Kensei weapon: longsword)
  - One with the Blade (Deft Strike)
  - Sharpen the Blade
  - Unerring Accuracy

- _Way of Mercy_ subclass ("mercy")
  - Hands of Harm
  - Noxious Aura (aura damage, 1 creature)

- _Way of Shadow_ subclass ("shadow")
  - Opportunist

- _Way of the Drunken Master_
  - _TODO_

- _Way of the Four Elements_
  - _TODO_

- _Way of the Long Death_
  - _TODO_

#### Assumptions

I modeled a primary / secondary stat Monk with the following modifiers:
  - Level 1: 3 / 2
  - Level 4: 4 / 3
  - Level 8: 5 / 3
  - Level 12: 5 / 4
  - Level 16: 5 / 5

Most subclasses use **Dexterity** / **Wisdom** for these stats, but the
Astral Monk has those reversed: **Wisdom** / **Dexterity**, since the
flavor and mechanics of that subclass seems to push for a stronger
wisdom focus.

Generally speaking, for situations where damage can be optimized by the
actions of the party, I assume that these optimizations are available.
For example, I generously assume the enemy is poisoned or incapacitated
for the Mercy Monk's "Hands of Harm" feature, and that it is within
range of her "Noxious Aura" feature. Shadow Monks always get their
"Opportunist" reaction, and Kensei monks always fight with a longsword.

The exception to this rule is that monks never get opportunity attacks.
This is done to provide a stark contrast to the Opportunist feature,
which is basically an easier-to-obtain version of an opportunity attack.

On the other side, situations which are largely out of the party's hands
are not granted. So, for example, the Argent Monk doesn't get double
Wrath damage from attacking undead, and the Shadow Monk can't teleport
and get advantage on every round.

I assume that the monk goes first every round; this doesn't affect much,
except that it adds an some points of "Noxious Aura" damage at the end
of the last round.

#### Tactics

The Monk tactics modelled here are simple:

- On the first round, if they can use some feature that provides a bonus
  to damage or change to hit, they use that feature first. This includes
  things like the Kensei Monk's "Sharpen the Blade" or the Mercy Monk's
  "Noxious Aura".
- They'll make an Attack action, making the maximum number of attacks.
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

With regards to weapons, I modeled that attacks made with the Attack
action are done with a non-magical quarterstaff in its "versatile" mode,
which does **1d8** base damage; it's generally accepted that a monk can
do this and still use her unarmed "Flurry of Blows" or "Martial Arts"
bonus attack. This is done until the monk can equal **1d8** damage with
her own unarmed strikes at level 11, at which point unarmed strikes are
used for all attacks. The exceptions to this is that the Astral Monk
always uses her "Arms of the Astral Self" weapon starting at level 3 for
all attacks, and the Kensei monk uses a longsword (also in its
"versatile" mode) for her Attack action from levels 3-20.

### Variables

There are four main variables that are modelled:

**Subclass:** The subclass which the Monk chooses. I currently have 5
subclasses (Argent, Astral, Kensei, Mercy, and Shadow) in the model, as
well as a "Pure" monk (that doesn't use any subclass features) for
comparison.

**Class Level:** The monk class level at which the combat occurs. I
model all levels 1-20 for all subclasses.

**Difficulty:** I represent the difficulty with a number 0-20, and
include 5 difficulty settings in the model:
  - At difficulty 0, the Monk's attacks always hit, and enemies never
    make their saving throw. ("Noxious Aura" damage is the only feature
    modeled so far that uses an enemy's saving throw).
  - At difficulty 5, the Monk hits with a natural d20 roll of 5 or
    greater, and enemies save with a natural d20 roll of 16 or greater.
  - At difficulty 10, the Monk hits with a natural d20 roll of 10 or
    greater, and enemies save with a natural d20 roll of 11 or greater.
  - At difficulty 15, the Monk hits with a natural d20 roll of 15 or
    greater, and enemies save with a natural d20 roll of 6 or greater.
  - At difficulty 20, the Monk hits with a natural d20 roll of 20, and
    enemies always make their saving throw.

At difficulty 5 and higher, enemies are scaled: their AC and saving
throws are adjusted against the Monk's primary stat and proficiency
bonus, so that the "natural roll" statements remain true at all Monk
class levels. This scaling tries model the relative strength of enemies
typically encountered at their respective class levels. Other class
features which raise or lower the Monk's chance to hit or DC of their
features are not included to enemy scaling. So, for example, a Kensei
Monk that uses "Sharpen the Blade" would have a better chance of hitting
the enemy than one who does not (all else being equal).

**Combat Length:** I included three different combat lengths: 1 round, 5
rounds, and 10 rounds of combat. I found that the typical length of
combat in a real game is around 4-6 rounds, so a 1-round combat is
short, while a combat that stretches out to 10 rounds is quite long. The
Monk's tactics are unchanged regardless of combat length, which is
especially unlikely in a real game. For this reason "combat length"
might be more useful as an indicator of early, mid, and late-combat
effectiveness; 10-round combat results might also be an indicator of how
a Monk performs when it's resources start to become depleted.

Combat lengths longer than 10 rounds are not modelled; very long combats
usually have a much different set of actions and tactics at the table
which are hard to model. Also, a number of activated features might
expire mid-combat in such situations, which is hard to model.

### Output

I present the model here as a set of 15 graphs for the 5 difficulty
settings times 3 combat lengths: each graph contains a single plot line
for each subclass that models its average per-round combat damage over
all the levels of its life.

## Future work

If we continue doing this, we hope to finish modelling more subclasses
of the Monk class, as well as compare it to other D&D classes. Some
class features provide spell or spell-like abilities, which are
difficult to model because their damage is highly situational, but we
can probably make some baseline assumptions.

We also like to model different situations: what happens if the Mercy
Monk doesn't always get their triple dice from "Hands of Harm"? What if
we include opportunity attacks in the model?

Finally, we'd like to play with different tactics. While we can never
include the wide range of tactics available to an experienced player, we
can probably make our Monks slightly more intelligent.
