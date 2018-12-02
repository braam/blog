---
title: Connecting an broadcasting system.
date: 2018-12-02
tags:
  - unify
  - osbiz
layout: layouts/post.njk
---
My Customer wanted to connect an broadcasting system to the PABX, the following we need:
<ul>
  <li>STRB: the amplifier switch needed to be closed otherwise the input won't triggered.</li>
  <li>Analog position in PABX.</li>
</ul>

## Setup analog port in PABX
You need to setup an normal SLAV port in the PABX, through this port the speech will blown in the aplifiers input. It's important to set the port type to <b>Loudspeaker</b>.

<img src="/img/amplifier_broadcast_analogport.png" />

## Connecting the STRB
Actually at the customer it's an STRBR so we can just terminate an RJ45 connecter in the middle (PIN 4 and 5). This will be an NO contact. The function of the actuator needs to be changed to <b>"Amplifier Speaker"</b>. It's important to assing the chosen analog port as "Assigned Station" Also change the "Switching Time" to <b>1 * 100 ms</b>. This will interrupt the NO contact immediate after you finished the broadcast by hanging up the phone.
Hint: This setting can only applied by Hipath Manager E.

<img src="/img/amplifier_broadcast_strb.png" />

## Amplifier input
Connect the pair for NO contact correctly as the diagram shows, also connect the analog position to + and - screw block, the polarity doesn't matter. On most amplifiers you'll need to set the switch for input to <b>MIC</b> instead of <b>Line</b>. If the signal is to silent you can set the extra switch to level up the signal by +18V.

<img src="/img/amplifier_broadcast_amp.jpg" />
