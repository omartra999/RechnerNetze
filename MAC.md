# Channel Allocation Problem

## Collision:
> Multiple Stations access one channel, `all collided packets are lost` => waste of `Bandwidth`

### How to avoid Collisions?
- **Static Channel Allocation** => Simple
- **Dynamic Channel Allocation** => Efficient

### MAC Protocol for a broadcast channel with R bit/sec
- if only one node is sending => `throughput = R`
- if M nodes are sending => `throughput = R/M`
- Decentralized protocol => `no Master`
- Simple and inexpensive to implement

## MAC Medium Access Control:
- is required when multiple stations want to put `frames` on the medium (wire) at the same time
- is a `Sublayer` of the `Data Link Layer`
- is **NOT** a part of the `OSI Model`
![Mac_SubLayer](mac_layer.png)
----
# Static Channel Allocation:
- One Channel has the Medium the rest don't have a medium
- **Multiplexing:** putting `multiple Data Flows` on one channel
- **Frequency Division Multiplexing (FDM)**
- **Time Division Multiplexing (TDM)**
 > Static => Division Multiplexing
- **Contra:** might end up in unused `time slots`/`frequency bands`

## Frequency Division Multiplexing
> Works just like a Chord on a musical instrument, input = many notes of different frequencies at the same time, output = a harmonized understandable sound from the same instrument
> Dividing Frequencies
## Time Division Multiplexing
> Percussionist, Dividing the Frame to Bars per Beats, every instrument playes on its beat and grooves 

| Frequency Division Multiplexing                           | Time Division Multiplexing                                    |
|-----------------------------------------------------------|---------------------------------------------------------------|
| `n` Stations on a `Cable`<br/> Channel bandwidth = `H`    | Channel transfer `B` bit/sec<br/>`n` stations on a cable      |
| Divide bandwidth to `H/n frequency bands`              | `n` time slots of length `t`                                  |
| Assign one `Band` to one `Station`                        | Round Robin<br/> Each Station transfers `B * t` bits per slot |
| No Collision possible :)                                  | No collision :)                                               |
| Bandwidth decreased by factor `n` for every single user :( | Bandwidth decreased by factor `n` for every single user :(    |
----
# Dynamic Channel Allocation:
- Channels which have more frames(data) to send, gets more Medium, and the ones which has less Data to send(Frames to put on wire) gets less Medium