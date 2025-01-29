# Network Layer:
- Moves `packets` between `different` networks
- `Route` packets from sender to receiver across multiple paths and networks.

## Functions of the Network Layer:
- Assigning logical Address
- Packetizing
- Host-to-host delivery
- Forwarding
- Fragmentation and reassembly of packets
- logical subnetting
- network address transition
- routing
----

# Connection-orientated vs Connection-less

## Connection-Orientated Service
![Connection-orientated_Service](Resources/Connection-orientated_Service.png)

## Connection-less Service
![Connectionlesss_Service](Resources/Connectionless_Service.png)

| Issue                     | Connectionless                                        | Connection-orientated                                              |
|---------------------------|-------------------------------------------------------|--------------------------------------------------------------------|
| Circtuit Setup            | not needed                                            | required                                                           |
| Addressing                | Each packet contains source and destination address   | Each packen contains a short `VC (Virtual-Circuit)` number         |
| State Information         | Routers di not hold any information about connections | Each `VC` requires `router table space`  per connection            |
| Routing                   | Each packet is routed `independently`                 | Route chosen when `VC` setup, all packets follow it                |
| Effect of router failures | None, except for packets lost during crash            | All `VC`s that passed through the failed routers are terminated    |
| Quality of service        | Difficult                                             | Easy if enough resources can be allocated in advance for each `VC` |
| Congestion control        | Difficult                                             | Easy if enough resources can be allocated in advance for each `VC                                                                   |

----
# Routing Algorithms

## Dijkstra's Algorithm for shortest path tree SPT
> Shortest Path Routing requires global knowledge => Path can be inaccurate
![Graph01](Graph01.png)
### Step 1:
- sptSet = { }
- pick the `vertex` with the minimum cost and append it to `sptSet`, this is the first step => root vertex
- sptSet = {(v = 0, d = 0), } `(vertex, distance from vertex)`
- update the adjacent vertices from the picked vertex
![Dijkstra_Step01](Resources/Dijkstra_Step01.jpg)

### Step 2:
- sptSet = {(v = 0, d = 0)}
- Pick the vertex with minimum distance value and not already included in  SPT  (not in  `sptSET`). The `vertex 1` is picked and added to `sptSet`.
- sptSet = {(v = 0, d = 0), (v = 1, d = 4)}
![Dijkstra_Step02](Resources/Dijkstra_Step02.jpg)

### Step n: 
- repeat till the end

## Flooding
> No global knowledge required, very robust
- Propagate each message to all neighbors `Each Message reaches every Node, a Message can reach one node several times`
- `Maximum Hop Count` + `Sequence Numbers` to avoid infinite circulation
- Each Message has its `Hop Count` (initial: `m.hop_count = 0`), and its `Sequence Number` `m.seq`, `m.source` the name of the source router
- for each propagation of `m` : `m.hop_count += 1`
- ```python
    if m.hop_count = max_hop_count: 
        discard(m)
  ``` 
- each router contains a counter `k`
- when a message is created:
```python
m.seq = k
m.source = router.name
k += 1
```
- when a message is created:
```python
if (m.seq,m.source) in table:
    discard(m)
else:
    table.add(m.seq,m.source)
    propagate
```
----


# Dynamic Routing Algorithems

| Distance Vector Routing                                        | Link State Routing                                                                                                          |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|
| Routers exchange their routing tables regularly with neighbors | Routers flood their view of the world </br> Every Router gains global knowledge </br> every router calculates shortest path |
| Only communication between neighbors                           | Adapts fast                                                                                                                 |    
| Adapts slowly to new topologies                                | More overhead due to flooding                                                                                               |

## Distance Vector Routing(this + youtube):
- **`A` receives routing table of `X`**
1. `A` knows it's distance to `X` is $ Ax $
2. `X` says it can reach `Y` at a distance of $ Xy $
3. `A` can reach `Y` at a distance of $ Ax + Xy $
4. if this is the best route => insert to routing table