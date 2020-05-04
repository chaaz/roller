## The Monk: The Big Picture

Download all graphs [here](assets/bigpicture.png).

To read about how we modelled damage and arrived at our conclusions,
read [this](index.md).

### Conclusions

The conclusions presented here are drawn from both the output data, and
from view some of the internal variables and construction of our models.
They focus on the mechanical aspects of the class, and largely ignore
its more subjective or nuanced attributes. All conclusions are my own,
and you should take them with a grain of salt.

### The Monk

Compared to other classes, a Monk has good low-level damage thanks to
Flurry at level 2. However, at higher levels it has to spend a decent
chunk of ki to match the damage that other martial classes get for free.
Between this and ki cost for the Monk's excellent crowd-control and
defense abilities, a monk will run out of ki surprisingly quickly.
Despite the focus of this post on damage, I don't think that damage is
actually the Monk's strong suite. Mobility and crowd control, combined
with interesting defensive features make the Monk a class that is best
used to apply debuffs, help, or crowd control where it is needed most.

### Way of Shadow

The only thing, damage-wise, that a Shadow Monk has going for her over
the base class is the "Opportunist" ability at level 17. This provides a
consistent 25% damage boost over the base class for parties that can
provide it. The extra damage is surprisingly noticeable during easy,
short encounters.

Obviously, the spells and spell-like effects at earlier levels are a
real draw for all kinds of fun encounters, but it should be noted that
most of them don't directly improve her damage.

Being able to attack with opportunity every round is a definite plus
(although that's not currently modelled), and would probably
help the Shadow Monk against higher-level opponents, where her damage
output otherwise lags behind other subclasses. A future iteration of
this analysis might include this feature.

### Way of the Kensei

The ability to use a **1d10** weapon at level 3 is useful on every
chart, but "Deft Strike", "Sharpen the Blade", and "Unerring Accuracy"
are all great to fight enemies with a high AC. "Sharpen" especially is
the only Monk ability that universally improves to-hit chance, which is
vitally important.

Kensei damage is not quite as impressive vs easy opponents. She has to
burn a bonus action to activate "Sharpen the Blade", which is a net
negative for easy, short combats. Her actual bonus boost by level 11 is
basically (monk die + 6)/round. Not bad, but nothing too exciting. The
Kensei also suffers from being a "2r" subclass: it has to burn 2 ki
points per round in order to keep up its maximum damage.

The Kensei subclass is entirely focused on weapon damage, and won't have
many features for social or exploration pillars, nor much ki for defense
or mobility. This is balanced against nice flavor, the ability to use a
weapon, and being able to damage from long range, which no other Monk
can do.

It's interesting to note the Kensei's dip in damage at levels 6-8 in the
"0 difficulty, 5 rounds" and "0 difficulty, 10 rounds" charts is not
statistical noise: when the Kensei first gets "Deft Strike" at level 6,
using a ki point for both it and "Flurry" every round causes her run out
of ki by round 4, which outputs less damage than simply using "Flurry"
every round.

### Way of Mercy

This Unearthed Arcana playtest content can be pretty powerful from a
damage output perspective. It's particularly effective in this analysis,
since it's granted the Poisoned and/or Incapacitated condition on its
enemies. The Mercy Monk's bread-and-butter damage feature "Hands of
Harm" does triple the damage it would otherwise do to Poisoned /
Incapacitated foes.

While both Poisoned and Incapacitated can be bestowed by the Monk itself
(Noxious Aura at level 6, and Stunning Strike at level 5), doing so
costs some points, and there are plenty of enemy types that are Poison
immune, as well as many enemies that are immune or resistant to necrotic
damage (the damage type applied by the feature). This grant thus ends up
being one of the more generous ones, and you can see the resultant power
on all the charts; a later analysis might include a Mercy Monk that
doesn't always get this boost.

"Hands of Harm" is reliable damage; it can be applied once the Monk
knows she's hit, which makes it effective against hard-to-hit enemies.
Medium-high difficulty charts have the Mercy Monk competing with Kensei
for best damage. The only downsides to the subclass are: (1) the Monk
has to spend a bonus action in round 1 to activate Noxious Aura (its
poison-dealer). Worse, this means that its only attacks in round 1 from
levels 6-10 are quarterstaff attacks, preventing it from using "Hands of
Harm" (which can be applied on unarmed attacks only). Also, (2) A Mercy
Monk is another "2r" Monk, meaning it spends two ki per round to
maximize its damage. This leaves little ki for its mobility, defense, or
healing.

The Mercy Monk is the only Monk that deals damage from its secondary
ability mod, via the "Noxious Aura" damage on a failed Wisdom save. The
effect is barely visible, but can be seen as a slight damage boost on
some of the 0-difficulty charts at levels 12 and 16.

### Way of the Argent Fist

This subclass is found in _Morgrave Miscellany_, a sequel to
_Wayfinder's Guide to Eberron_ published by Dungeon Master Guild. While
not official content, the class is very flavorful, and inspired me to
write this Monk comparison in the first place. There are two features of
the subclass that affect damage:

- "Wrath of the Argent Fist": at level 3 allows the Monk to spend 2 ki
  and add **1d4** radiant damage (**2d4** to fiends, monstrosities, or
  undead) to every monk weapon or unarmed strike for 1 minute. The
  wording in the text doesn't specify whether the activation costs an
  action, bonus action, or free action, so this analysis generously
  treats it as a free action on the Monk's turn. At level 17, she can
  spend 4 ki instead to double that (**2d4** or **4d4**).
- "Radiant Embrace": at level 17 the monk can spend an action once per
  long rest to do critical hits on a 19 or 20 (18-20 vs fiends,
  monstrosities, or undead) for 1 minute. (_TODO: this feature is not
  currently included in the model, and probably will give the Argent
  Monk a big boost vs higher-level opponents when it is._)

The class is very flavorful and seems like a lot of fun; it also does a
fair amount of healing (self and others), and can turn or paralyze
fiends, monstrosities, and undead. This subclass is probably a bit more
powerful when measured against other subclasses. Because of its free
activation, it does quite well in short combats, and it only needs to
keep up "Flurry" to maximize its damage round-over-round, so it can do
well in long combats as well.

During normal-length combats and/or against difficult opponents, it
can't keep up with the Kensei's bonus to-hit, or the Mercy Monk's
reliable 3x dice. It still out-performs the pure Monk and Shadow Monk,
though, proving that you can't go wrong with just some plain old extra
punch power. Players that don't have access to this content can consider
this analysis as equivalent to some magical item that grants +2 or +3
damage.

### Way of the Astral Self

This is also Unearthed Arcana playtest material, and a big departure
from other Monk subclasses: not only does it mechanically encourage
building a Wis/Dex monk (vs most other monks which are Dex/Wis), but it
also seems to encourage eschewing using "Flurry of Blows" for an
alternate "arms" bonus attack mechanism.

The arms attacks cost 0 ongoing ki, making this the only "0r" Monk in
the game: since no round-to-round ki is spent on damage, it really frees
up this Monk to spend her ki on class's defensive, mobility, and
crowd-control options. The Astral Monk has interesting skill and defense
powers, and Ki Consumption is by far the most powerful resource
management tool ever introduced in 5e, letting her be the stun monster
that everyone is afraid of from a Monk. Stuns that, let's remember, have
a DC based on her primary ability.

Damage-wise, the Astral Monk does very low damage at early levels on all
charts: lower even than the base class, since her bonus arms attack
don't do as many attacks as Flurry until level 11. By level 17, though,
the Monk is making 6 attacks per round, the most in the game (unless you
count the situational "Drunken Flurry", which can make as many as 7
attacks). At high levels, the Astral Monk is the highest average damage
dealer of all Monks vs trivial / easy enemies, and still does fair
damage against more difficult enemies.

The early-level damage is really the only downside, but it is
significant. Even if the Astral Monk were to skip the arms and do normal
quarterstaff / Flurry attacks until level 11 (an option which we might
include in a future analysis), she would still not be as effective as a
base Monk, since her Wis/Dex build means that she would be attacking and
damaging with her secondary ability.

### Way of the Drunken Master

_(Not included)_

We haven't modelled this subclass yet, but it's interesting to note that
"Drunkard's Luck" can cancel the disadvantage side of an
advantage/disadvantage pair when fighting blind against opponents that
are also blind (such as when fighting in heavy fog or darkness). This
means that the Drunken Monk effectively has advantage on its attacks vs
her opponent, while the enemy does not.

### Way of the Four Elements

_(Not included)_

All the spell work in this subclass makes it very difficult to model.
However, it's interesting that this is the only subclass that can apply
damage on every hit on a turn ("Fangs of the Fire Snake"), meaning that
it might be very good at burst damage a few times per short rest.

### Way of the Open Hand

_(Not included)_

Obviously, the Quivering Palm capstone of this class is god-like, the
only ability that is literally save-or-die in the whole game. This also
makes it impossible to model, unless we start making assumptions about
max HP for enemies at that level.

All its other subclass features have no direct effect on damage, though,
making the Open Hand Monk something of a control character.

### Way of the Sun Soul

_(Not included)_

Other than Sun Shield at level 17, it's very difficult to model the
damage from this subclass, since it comes from spells or spell-like
effects. We might try to make some reasonable assumptions in a future
analysis.

### Way of the Long Death

_(Not included)_

This subclass contains almost no direct damage effects, except for its
level 17 "Touch of the Long Death", which we could probably model fairly
easily. **2d10** per ki is actually pretty efficient compared to other
subclass features.

