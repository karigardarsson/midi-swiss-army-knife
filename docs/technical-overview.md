# Technical overview

## System boundary

MIDI Swiss Army Knife is a local embedded controller that sits between a player’s decisions and an external musical device. The controller owns interaction, candidate browsing, snapshots, and local state; the external sequencer remains responsible for its own pattern timing, editing, and persistent device reality.

## Architectural seams

| Concern | Showcase-level description |
| --- | --- |
| Controls and OLED | Physical controls enter a state-driven runtime. The OLED is a bounded display client, not the owner of musical state. |
| Musical layer | Harmony, note guidance, line and drum material provide finite, inspectable choices rather than unconstrained generation. |
| Runtime state | Browse cursors, selected candidates, pending operations, committed state, and routing are intentionally distinct. |
| Transport/writer | Device communication is treated as a transaction boundary with readback and verification. |
| External device | Digitakt II is the principal target. The showcase makes no general compatibility claim. |

## Transaction model

An outgoing operation takes a stable snapshot: the selected candidate, target role, and destination are captured before the writer begins. The later result is evaluated against a fresh device observation before any local state becomes committed.

That separation protects against a common live-system failure: a user keeps browsing while transport work is pending, and mutable UI state accidentally changes the meaning of the in-flight request.

## MIX LAB as a state-management case study

MIX LAB is useful as a compact example of the broader design:

- A visible candidate is temporary.
- A `CURRENT MIX` member is local committed state associated with a role.
- A routing target is an intended destination, not proof of what the external device currently contains.
- A verified outcome may promote the pending snapshot; failure keeps prior local truth intact.

BUILD and FREE are not permission systems. They are two exploration lenses over the same experimental candidate corpus. BUILD offers relationship-aware annotations; FREE permits unrestricted browsing.

## Deliberately withheld detail

The public overview does not expose message payloads, private object representations, raw captures, byte offsets, exact ownership maps, device backups, or full implementation. It documents the engineering method and boundaries without publishing the proprietary/reverse-engineered surface needed to recreate the private writer.
