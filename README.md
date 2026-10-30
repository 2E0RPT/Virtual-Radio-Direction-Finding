# Virtual Radio Direction Finding

**User Manual**\
By Rob (2E0RPT)

Virtual Radio Direction Finding is a multiplayer first-person game about
hunting hidden radio transmitters, a hobby known as **radio direction
finding** or **foxhunting**. You carry a handheld radio for talking to
your friends and a three-element Yagi directional antenna for tracking
down the signal.

Two kinds of game are played on a large map of hills, forest and
villages:

-   **Radio Egg Hunt:** Find a hidden beacon; the fastest player wins.
-   **Radio Fox Hunt:** Hounds track down hiding foxes.

## Table of Contents

-   [Getting Started](#getting-started)
-   [Default Controls](#default-controls)
-   [Endurance and Scoreboards](#endurance-and-scoreboards)
-   [1. Radio Egg Hunt](#1-radio-egg-hunt)
-   [2. Radio Fox Hunt](#2-radio-fox-hunt)
-   [3. The Yagi Directional Antenna](#3-the-yagi-directional-antenna)
-   [4. The Radio Voice Service](#4-the-radio-voice-service)
-   [5. Administrator Features](#5-administrator-features)

## Getting Started

1.  Start the game with `Game.exe`. It connects to the game server
    automatically. To use a different server, pass its address, for
    example:

    ``` text
    Game.exe 192.168.1.5
    Game.exe myserver.example:7777
    ```

2.  Log in with your player name and password:

    -   Player name: 3--15 letters, digits, or underscores (`_`).
    -   Password: 4--31 characters.
    -   If the name does not exist, you will be asked whether to create
        the account or try again.

3.  The lobby lists everyone online. Click **Radio EGG hunt** or **Radio
    FOX hunt** to join that game with everyone else in the lobby.

4.  Players who log in while a game is running wait in the lobby for the
    next game.

5.  Use **Key binds** to customise keys and mouse buttons.
    **Scoreboard** shows results.

## Default Controls

All controls except **Quit** can be changed in **Key binds**.

  -----------------------------------------------------------------------
  Action                  Default key             What it does
  ----------------------- ----------------------- -----------------------
  Walk                    `W`, `A`, `S`, `D`      Move forward, left,
                                                  backward and right.
                                                  Diagonal movement is
                                                  50% slower.

  Look around             Mouse                   The cursor is hidden
                                                  and captured while you
                                                  are in the world.

  Run                     Hold `Shift`            Up to 2.5 times walking
                                                  speed; uses endurance.

  Raise the Yagi          Hold `Space`            Listen for the beacon
                                                  or fox. Lower it to
                                                  stop listening.

  Map                     Hold `M`                Shows the whole map,
                                                  your position as a
                                                  yellow arrow, and your
                                                  X/Y coordinates above
                                                  it.

  Compass                 Hold `C`                A handheld compass; the
                                                  red end of the needle
                                                  always points north.

  Hide mode               `H`                     Foxes only: lock
                                                  yourself in place when
                                                  hidden.

  Talk on the radio       Hold left mouse button  Push-to-talk. Release
                                                  to listen.

  Quit                    `Esc`                   Opens "Quit game - Are
                                                  you sure?"; answer Y or
                                                  N. This key cannot be
                                                  changed.
  -----------------------------------------------------------------------

### Endurance

A bar at the top right shows your endurance while running.

-   Running drains endurance by **2% per second**.
-   When you are not running, endurance recovers by **3% per second**.
-   Running speed depends on remaining endurance.
-   At 0%, you cannot run until you release the run key.

Tree trunks and house walls are solid (houses have an open doorway), but
grass and shrubs can be walked through.

### Scoreboards

The Scoreboard screen is split in two:

-   The top half shows the current game or the last game and updates
    live as players finish.
-   The bottom half contains permanent best-time tabs: Egg Hunt, Single
    Fox Hunt, and one tab for each hunt with 2--8 foxes.
-   If the last game sets a new high score, the relevant tab flashes
    red, yellow, green and blue until clicked.

## 1. Radio Egg Hunt

*Find the hidden beacon as fast as you can.*

### The Aim

A small radio beacon, called the **egg**, is hidden somewhere on the
map. It is a small dark-green dome with a thin black antenna and a red
light on top. It is never shown on the map.

Each player is dropped at a random place at least 300 units from the
beacon and must track it down by ear. Walk into the beacon to finish
your round. Your time is recorded, and you go to the scoreboard to wait
for the others.

### How a Round Works

1.  **Start:** Click **Radio EGG hunt** in the lobby. A 3-second
    countdown gives everyone a moment to look around, then the clock
    starts.
2.  **Hunt:** Hold `Space` to raise the Yagi, sweep it around, walk
    towards the loudest beep, and use the map and compass to track your
    position.
3.  **Find it:** Touch the beacon to end your round. Players are ranked
    1st, 2nd, 3rd, and so on in arrival order, with their times.
4.  **Wait:** The scoreboard updates live as the others finish. When
    every player has found the beacon or left the game, a **Back to
    lobby** button appears.

The beacon becomes visible when you are within about 200 units. Up
close, its red light flashes with every beep.

### How Egg Hunt Sounds: SSB Tracking

Egg Hunt is modelled on **SSB (single-sideband) tracking**, where
direction finders listen for a weak carrier.

While the Yagi is raised, you hear constant static (a mix of hiss and
rumble). Every second, a short 1000 Hz beep comes through. The static
does not change, but the beep gets louder as you:

-   Point the Yagi directly at the beacon.
-   Get closer to it.
-   Stand on higher ground.

The beep volume is calculated by multiplying three factors: **direction
volume × distance volume × elevation volume**.

  -----------------------------------------------------------------------
  Factor                              How it works
  ----------------------------------- -----------------------------------
  Direction                           The Yagi pattern gives 100% when
                                      pointing directly at the beacon,
                                      20% when 90° off to the side, and
                                      silence when pointing directly
                                      away.

  Distance                            100% right next to the beacon,
                                      falling in a straight line to 0% at
                                      the map corner farthest away from
                                      it.

  Elevation                           From 10% on the lowest ground to
                                      100% on the highest hilltop, but
                                      never lower than the distance
                                      volume, so a close beacon is always
                                      clear.
  -----------------------------------------------------------------------

#### Worked Example

You stand 600 units from the beacon. Its farthest corner is 1800 units
away, and the ground under you is 6.0 units high. You aim 30° off the
beacon:

-   Direction: 85.1%
-   Distance: `1 - 600 / 1800 = 66.7%`
-   Elevation: 78.2%

The beep is `0.851 × 0.667 × 0.782 = 44.4%` of full volume.

### Hunting Tips

-   **Triangulate:** Face the loudest direction, hold `M`, and note
    where the map arrow points. Walk well to one side, repeat, and the
    two lines cross at the beacon.
-   **Sweep in steps:** The beacon beeps once a second, and the volume
    is fixed at the start of each beep. Turn 15--20°, stop, listen to
    one beep, then turn again.
-   **Find the middle of the loud zone:** The volume changes slowly near
    the peak. Find the two angles where the beep is clearly half as loud
    (about 61° either side), then aim halfway between them.
-   **Climb before listening:** On the lowest ground, the beacon is only
    one tenth as loud as on the highest hilltop.
-   **Quiet does not mean the wrong direction:** Distance and low ground
    make everything quieter. Compare beeps from the same spot as you
    turn.
-   **Save your running:** Run on open ground and walk while sweeping,
    so your endurance refills while you listen.
-   **Know where it is not:** The beacon is never on a path, never close
    to a house, and never near a tree.

## 2. Radio Fox Hunt

*Hounds track down the hiding foxes.*

### The Aim

There is no beacon in a Fox Hunt. Some players are **foxes**: they run
off, find a hiding place, and then transmit on a timetable. The other
players are **hounds**, who use their Yagi to find them. The round lasts
until every hound has found every fox.

### Setting Up: The Fox Hunt Lobby

Click **Radio FOX hunt** in the main lobby. At least two players must be
in the lobby.

Everyone moves to the Fox Hunt lobby, where each player has three
buttons beside their name: **Hound**, **Fox**, and **Ready**.

-   A switched-on button is light green with black text.
-   A switched-off button is red with white text.
-   Everyone starts as a Hound.
-   Choose your role, then press **Ready**. Changing your role clears
    your Ready status.

Two settings can be adjusted with `-` and `+` buttons:

-   **How long should each fox TX for:** 10--60 seconds, in 5-second
    steps.
-   **How long does the fox(es) wait to TX again:** 15--900 seconds, in
    15-second steps.

The green **Everyone ready? - Let's play** button works only when there
is at least one hound, at least one fox, and every player has pressed
**Ready**.

### The Hiding Phase

-   Foxes are dropped at random places on the map and have 3 minutes to
    find somewhere to hide. During this time, foxes have infinite
    endurance.
-   A fox can press `H` to enter hide mode early, or wait for the 3
    minutes to run out.
-   In hide mode, a fox stays where it is.
-   Hounds wait on a **The foxes are hiding...** screen with a
    countdown.
-   When the 3 minutes are up, or all foxes have pressed `H`, the hunt
    starts. Foxes become mostly transparent to blend into their
    surroundings, and hounds appear together at the centre of the map.

### Fox Transmissions: Timers and the Pie Chart Clock

Foxes do not choose when to transmit. The server runs the timetable
using the two settings chosen in the lobby.

-   The first transmission starts 15 seconds after the hunt begins.
-   With more than one fox, they take turns.
-   The configured wait time is divided evenly between the foxes. For
    example, with 3 foxes, **TX for** set to 15 seconds, and **wait**
    set to 45 seconds, each fox transmits for 15 seconds followed by a
    15-second gap.

As a fox, a message counts down to your next turn (for example, "Next
transmission in 1:25") and changes to a flashing **ON-AIR** display
showing the remaining transmission time. Speak clearly and watch the
ON-AIR timer. You can talk to or taunt the hounds, but do not be rude.
If you do not speak, or your microphone is not working correctly, a
warble tone is transmitted instead.

As a hound, a pie-chart clock appears at the top right of the screen. It
shows one complete cycle, starting at 12 o'clock and moving clockwise:

-   Each coloured slice represents one fox's transmission and is as wide
    as its **TX for** time (Fox 1 blue, Fox 2 orange, Fox 3 green, and
    so on).
-   White sections represent the waits.
-   A red dot moves clockwise around the rim. Inside a coloured slice,
    that fox is on air; in a white section, nobody is transmitting.
-   A caption below the clock says who is on air (for example, "Fox 1 on
    air - 20 s") or how long until the next transmission.
-   **A fox is on air - raise your Yagi (SPACE)** flashes while a fox
    transmits.
-   The clock re-aligns with the server at the start of every
    transmission, so it does not drift.

### How Fox Hunt Sounds: FM Tracking

Fox Hunt is modelled on **FM tracking**, which behaves differently from
Egg Hunt:

-   When the Yagi points away from the fox, or you are far away, you
    hear mostly hissy static.
-   As you get closer and point the Yagi at the fox, the noise drops and
    the fox sounds clearer and cleaner.
-   When a fox starts transmitting, you hear a short squelch burst. When
    it ends, you hear that fox's own 5-note roger beep followed by
    another squelch burst.
-   With several foxes, their roger beeps help you tell them apart, and
    the pie clock shows who is due next.
-   You only hear a fox while the Yagi is raised. Lower it and the world
    goes quiet again.
-   Foxes are never heard on the voice radio, so the radio cannot be
    used to find a fox.

Normally, a fox sounds like a steady, slightly warbling tone. While on
air, the fox's microphone is open: if the fox talks, hounds hear the
fox's voice instead of the warble. If nobody speaks for 3 seconds, the
warble returns; it switches back to voice as soon as the fox talks. Only
foxes currently on air can be heard. Their voices pass through the Yagi
just like the tone: clear when aimed at, hissy when not.

### Fox Microphone Controls

In hide mode, a fox gets a small panel at the top right of the screen
with a live microphone-level meter and a **Voice level** slider.

-   The white line across the meter is the voice threshold (default
    20%).
-   When the meter rises above the line, the game counts you as talking.
-   Adjust the slider so your normal speaking voice rises above the line
    while background noise stays below it.

In hide mode, the mouse pointer is released so you can use the slider.
The mouse can no longer turn the camera, so `W`, `A`, `S`, and `D` pan
the camera instead. Your microphone is sent to hounds only while you are
on air.

### Finding a Fox

Walk right up to a fox to find it. A message tells you **You found fox
1!**, and the HUD updates **Foxes found: 1 / 3**.

Once you have found all foxes, you can stay on the map and help (or
hinder) the others. The round ends when every hound has found every fox,
or when no hounds or no foxes remain. Hounds are ranked by the time
taken to find all foxes. Each Fox Hunt size (1--8 foxes) has its own
permanent scoreboard tab.

## 3. The Yagi Directional Antenna

*Your most important tool.*

### What It Is

A Yagi is a directional antenna with a long boom and several cross
elements. It receives best along the direction the boom points (the
**main lobe**) and much less from the sides and rear.

In the game, you hold a three-element Yagi. Hold `Space` to raise it and
listen; release the key to lower it. You can still walk while it is
raised. While the Yagi is up:

-   The handheld radio display is hidden, although you can still hear
    your friends.
-   The ambient background sound loop pauses until you lower it again.

Only the compass direction you are facing matters. Looking up or down
does not change the signal.

### Gain in Every Direction

The volume for the direction part of the signal is:

``` text
((1 + cos(angle)) / 2) ^ 2.32
```

Here, `angle` is how far the boom is from the transmitter. The same
angle produces the same volume whether you are off to the left or right.

    Angle off target   Volume       Level (dB) What you hear
  ------------------ -------- ---------------- -----------------
                  0°     100%              0.0 Full volume
                 15°      96%             -0.3 Almost full
                 30°      85%             -1.4 Strong
                 45°      69%             -3.2 Clearly quieter
                 60°      51%             -5.8 About half
                 90°      20%            -14.0 Weak
                120°       4%            -28.0 Very faint
                135°     1.2%            -38.7 Barely there
                150°     0.2%            -54.5 Almost nothing
                180°       0%   minus infinity Silent (null)

### Using the Yagi Well

-   The beam is about 122° wide. The signal is half as loud about 61°
    either side of the centre line, so the usable main lobe is roughly
    122° wide.
-   The peak is flat and the sides are steep. At 15° off, the volume is
    only 4% lower, making the exact peak hard to judge. Find the two
    angles where the signal is clearly half as strong, then aim halfway
    between them.
-   The game's Yagi is idealised. It has a perfect silent point directly
    behind it and no side lobes. A real three-element Yagi picks up some
    signal from the back and sides, which is why real foxhunters often
    use an attenuator.
-   Combine it with the map and compass. Take a bearing with the Yagi,
    check it against the map (`M`) or compass (`C`), move, and take
    another. The point where the lines cross is the transmitter.
-   In Egg Hunt, the Yagi changes how loud the beep is. In Fox Hunt, it
    changes how noisy the signal is. In both, the strongest or clearest
    direction is the way to go.

## 4. The Radio Voice Service

*Talk to your friends, or keep them out of earshot.*

### Your Handheld Radio

Besides the Yagi, every player has a second radio for talking to other
players. It works like a real push-to-talk handheld: hold the left mouse
button to talk and release it to listen. You can change the button in
**Key binds**.

The voice radio is separate from the Yagi and the beacon. It is not
directional and cannot be used to find an egg or a fox.

### What You See on the Radio

-   **Transmitting:** A red screen with `TX`.
-   **Receiving:** A green screen with the name of the player talking.
    Signal bars show how clear the signal is.
-   The radio appears only while someone is talking. It is hidden while
    your Yagi, compass, or map is raised, but you can still hear
    everything.
-   If an administrator has switched your voice off, the radio shows
    `VOICE OFF` when you try to talk.

### How the Radio Sounds

-   Only one person talks at a time. Others must wait while someone is
    transmitting.
-   A transmission cannot last longer than 30 seconds. The radio cuts
    the speaker off and shows `TIME OUT`.
-   **Roger beep:** Releasing the talk button ends the transmission with
    a 5-note roger beep made from tones in a pentatonic scale, followed
    by a short squelch burst. Each player gets a unique roger beep,
    chosen randomly when their account is created and kept permanently.
-   **Static grows with distance:** In Egg Hunt, more static is mixed
    into voices as players get farther apart---none when standing
    together and full static at opposite corners of the map.
-   **No distance clues in Fox Hunt:** The radio is completely
    omnidirectional and has no distance static, so it cannot give a fox
    away.

### Talking in the Lobby, on the Scoreboard, and in the Fox Lobby

You can talk and listen in the lobby, on the scoreboard, and in the Fox
Hunt lobby as well.

-   Players in menus use their own **lobby channel**.
-   Players walking around in a game use the **game channel**.
-   The channels are separate so lobby chat does not disturb a round and
    players who have finished cannot give away the beacon or foxes.

In menus, a small badge in the corner shows a red `TX` while talking, a
green `RX: name` while receiving, or a reminder of which key to hold. If
the push-to-talk button is also a menu click, holding it over empty
space talks, while clicking a button works normally.

### Cross Band

The **Cross band** checkbox in the lobby joins the two channels. When
ticked, players in the lobby, on the scoreboard, and in the Fox Hunt
lobby can talk to players still in the game, and vice versa. When
unticked (the default), the channels remain separate and lobby chat does
not affect the game.

Any player can tick or untick Cross band unless an administrator has
locked it; then it shows **Cross band (locked)**.

A person in a menu has no position on the map, so their voice always
arrives without distance static.

## 5. Administrator Features

*Running a fair and friendly server.*

### Becoming an Administrator

Administrator status can only be granted or removed at the server
console (the window where `Server.exe` is running). It cannot be changed
from the game, so players cannot make themselves administrators.

Enter these commands in the server window:

  -----------------------------------------------------------------------
  Console command                     What it does
  ----------------------------------- -----------------------------------
  `admin add NAME`                    Makes that player an administrator
                                      immediately, even if they are
                                      logged in.

  `admin remove NAME`                 Removes that player's administrator
                                      rights.

  `admin list`                        Lists administrators and shows who
                                      is logged in.

  `kick NAME`                         Disconnects the player from the
                                      server. They can log in again.

  `ban NAME`                          Bans the account. They cannot log
                                      in until unbanned.

  `unban NAME`                        Lifts a ban. Unbanning is only
                                      possible at the server console.

  `banned`                            Lists banned accounts.

  `help`                              Shows the list of commands.
  -----------------------------------------------------------------------

An administrator is marked `[admin]` beside their name in player lists.
A hint in the lobby reminds administrators to right-click for options.
The following actions are accessed by right-clicking.

### Switching a Game Off: Egg and Fox Buttons

In the lobby, an administrator can right-click **Radio EGG hunt** or
**Radio FOX hunt** to disable or enable that button.

When a game is disabled, other players cannot click it and see
**Disabled by an administrator**, but the other game remains available.
Administrators can still start a game they have disabled.

### Locking Cross Band

Right-click the Cross band checkbox and choose **Lock** or **Unlock** so
other players cannot change it. The label changes to **Cross band
(locked)**. Administrators can still change the setting.

### In the Fox Hunt Lobby

-   **Set anyone to Hound or Fox:** An administrator can click the Hound
    and Fox buttons on every player's row, not just their own. That
    player's Ready status is cleared so they can confirm again.
-   **Lock the timers:** Right-click one of the `+` or `-` buttons and
    choose **Lock the + / - buttons for other players**. The two
    settings can then only be changed by administrators, and everyone
    sees `(locked)`.

### Automatic Release

Lock-outs do not last forever. If no administrator has been logged on
for 2 minutes, every lock-out---disabled game buttons, Cross band lock,
and the `+`/`-` lock---is lifted automatically and all players regain
control.

### The Player Menu

Administrators can right-click another player in the lobby, Fox Hunt
lobby, or scoreboard to open a menu with five options:

  -----------------------------------------------------------------------
  Option                              What it does
  ----------------------------------- -----------------------------------
  **Disable voice**                   The player can no longer talk on
                                      their radio (it shows `VOICE OFF`).
                                      This lasts until they disconnect.

  **Enable voice**                    Lets the player talk again.

  **End round**                       Removes the player from the current
                                      game. They go to the scoreboard
                                      marked "did not finish".

  **KICK player**                     Asks for confirmation. Choosing Yes
                                      disconnects the player from the
                                      server; they can log in again.

  **BAN Player**                      Shows a warning and asks for
                                      confirmation. Choosing Yes bans the
                                      account and disconnects the player.
  -----------------------------------------------------------------------

#### Important Notes

-   An administrator cannot be kicked, banned, or silenced from this
    menu.
-   You cannot use the player menu on yourself.
-   A banned player sees **This account is banned from the server** when
    trying to log in.
-   Bans are saved on the server. Only `unban NAME` at the server
    console removes a ban.
-   A kicked player sees **You were kicked off the server by an
    administrator** and can log straight back in.

------------------------------------------------------------------------

***Legal Notice***

**FORMAL STATEMENT OF CLARIFICATION AND POSITION ON ANIMAL WELFARE**

**Subject: Amateur Radio Direction Finding (ARDF), Virtual Radio Direction Finding (VRDF), and the Distinction from Real-World Fox Hunting**

For the avoidance of doubt, **Amateur Radio Direction Finding (ARDF) and the Virtual Radio Direction Finding (VRDF) game are entirely separate from, and in no way associated with, the pursuit, harassment, capture, or killing of real-life foxes or any other animals.**

ARDF is a recognised amateur radio activity in which participants use radio receivers and directional-finding techniques to locate hidden radio transmitters. VRDF recreates aspects of this technical and recreational activity within a virtual gaming environment. In both cases, the term *fox* refers to a radio transmitter or a virtual objective, not a living animal.

Any similarities in terminology are purely historical or contextual and must not be interpreted as an endorsement of, participation in, or association with real-world animal hunting. Neither ARDF nor VRDF should be confused with traditional fox hunting, and neither activity requires the involvement of live animals.

### Our Position on Real-World Fox Hunting

We wish to make our position on the pursuit of real foxes equally clear.

We strongly oppose the unnecessary suffering of animals and express our displeasure at activities that involve chasing, exhausting, injuring, or killing foxes for entertainment or sport. We believe wildlife should be treated responsibly and that cruelty to animals should never be excused as recreation.

In England and Wales, the Hunting Act 2004 makes hunting wild mammals with dogs an offence, subject to specific statutory exemptions. Traditional fox hunting with a pack of dogs is illegal under this legislation. Activities that breach the law should be reported to the appropriate authorities and dealt with accordingly. We support compliance with animal welfare legislation and the proper enforcement of wildlife protection laws.

### Recognising the Challenges Foxes Can Present

We also recognise that foxes can present genuine and sometimes serious challenges for people living and working in both urban and rural environments.

In urban communities, foxes may scatter rubbish, damage property, enter gardens, prey on domestic poultry, or cause concern among residents. In agricultural areas, foxes may threaten vulnerable livestock, particularly young animals and poultry, and may create additional difficulties for farmers who are already managing demanding working conditions.

These concerns should not be dismissed. Farmers and urban residents have legitimate interests in protecting their property, animals, livelihoods, and local environments.

However, acknowledging these challenges does not justify cruelty or the use of illegal hunting practices. Responsible fox management should be proportionate to the problem, consistent with applicable law, and designed to minimise unnecessary suffering. Where intervention is necessary, lawful and humane approaches should be considered.

**There is a clear distinction between responsibly managing wildlife-related problems and pursuing animals for sport or entertainment.** Recognising the former does not require supporting the latter.

### Final Clarification

ARDF and VRDF are activities centred on radio technology, directional finding, navigation, problem-solving, and recreation. Their use of the word *fox* does not connect them to real-world fox hunting.

We therefore reject any suggestion that participation in ARDF or VRDF implies support for, involvement in, or approval of the hunting of living foxes.

We advocate respect for the law, responsible wildlife management, and the prevention of unnecessary animal suffering, while recognising the practical challenges that foxes can present to farmers and urban communities.

**The distinction is simple: finding a radio transmitter, whether in a real-world ARDF event or a virtual VRDF game, is not the hunting of a living animal. The two activities are fundamentally different in purpose, method, and ethical implications.**

