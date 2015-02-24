> In a race, the quickest runner can never overtake the slowest,
> since the pursuer must first reach the point whence the pursued started,
> so that the slower must always hold a lead.

> – as recounted by Aristotle, Physics VI:9, 239b15

Our sentry guns have spotted two running targets. Should we shoot them now, or wait when they will be closer together?
We need to develop a protocol to handle this scenario.

We've asked two robots to help us simulate this situation:
Achilleborg (A1 -- fast agile prototype) and Tortoimenator (T2 -- heavy slow cyborg).


A1 is faster than T2, so it has a **X** seconds head start on A2.
For **X** seconds T2 will move at **t2_speed*X** metres.
So A1 must first reach the point whence T2 already reached.
But T2 is moving and next step for A1 is to reach the next point and so on to infinity.
The paradox is correct in theory,
but in practice A1 easily outruns T2. Hm... maybe we can calculate when A1 will catch up to T2.

![A1-T2](A1-T2.png)

You are given A1 and T2’s speed in m/s as well as the length of the advantage T2 has in seconds.
Try to count the time when from when A1 come abreast with T2 (count from T2 start).
The result should be given in seconds with precious &plusmn;10<sup>-8</sup>.

**Input:** Three arguments. Speeds of A1 and T2 and advantage as integers.

**Output:** The time when A1 catch up T2 (count from T2 start) as an integer or float.

**Example:**

```python
chase(6, 3, 2) == 4
chase(10, 1, 10) == 11.11111111
```

**How it is used:**

This mission serves as a reminder that sometimes simple arithmetic allows us to resolve difficult paradoxical problems easily.

**Precondition:**
```python
t2_speed < a1_speed < 343
0 < advantage <= 60
```