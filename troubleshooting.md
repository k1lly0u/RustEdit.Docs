# Troubleshooting

> **This page is a skeleton.** The failures below are the ones worth documenting
> first; the causes and fixes need someone who has actually debugged them.
> Delete this note when it's filled in.

Work down the page - the entries are roughly in the order people hit them.

## The editor won't start

_TODO: missing runtime, blocked by antivirus, extracted into a protected
folder._

## Terrain loads but prefabs don't

Almost always the Rust folder setting: the editor found *a* path but not one
with game content in it.

_TODO: how to confirm, and what a correct path looks like._

## The map won't load on a server

_TODO: file in the wrong place, wrong startup argument, size limits._

## Everything is slow

| Symptom | Usually |
| --- | --- |
| Slow to open a map | _TODO_ |
| Slow while editing | _TODO_ |
| Slow to save | _TODO_ |

## Something I placed isn't in game

Check the obvious one first: it may be under the terrain. The editor shows
objects below ground; the game plays them as solid and invisible.

_TODO: the other common causes._

## Getting help

If none of this covers it, ask on the forum with:

- what you did, in order;
- what you expected, and what happened instead;
- the map size and roughly how many prefabs;
- any error text, copied out rather than described.

That set of four answers most questions before anyone has to ask for them.
