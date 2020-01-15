# Control flows

## Original concept

### Search for the target

TODO:

* Maybe a little bit too complex?
* Ultrasonic-Problem

```plantuml

start

repeat
    if (game boundary detected?) then (yes)
        :realign at the boundary;
        note right
            in order to correct deviation from straight route
            (using the infrared sensors)
        end note
        repeat
            repeat
            :move a little bit backwards;
            :look for potential targets (ultrasonic sensors);
            ' check for game boundary
            repeat while (potential target spotted? (ultrasonic sensors)) is (no)
            ->yes;
            ' if potential spotted
            :rotate to potential target;
            :identify potential target (object detection);
            if (target spotted?) then (yes)
                stop
            else (no)
                :undo previous rotation;
            endif
        repeat while (game boundary detected?) is (no)
        ->yes;
        :realign at the boundary;
        note right
            in order to correct deviation from straight route
            (using the infrared sensors)
        end note
        :move a tiny bit forward;
        note right
            to prevent triggering the next boundary check
        end note
    else (no)
        :move a little bit forward;
        :look for target  (object detection);
    endif
repeat while (target spotted? (object detection)) is (no)
->yes;

stop

```

### Navigate to the target

TODO:

* What happens if target is lost during rotation?
* What happens if another animal is in the way (collision detection)?

```plantuml

start
while (target is faced directly?)
    :rotate a little bit towards the target;
    note right
    using the position of the detected object relative to
    the center of the cameras point of view
    end note
endwhile

while (target is not in grab-range?)
    :move a little bit forward;
    note right
    using the front ultrasonic sensor to measure distance
    end note
    ' TODO collision prevention
endwhile

stop

```

### Move target out of boundaries

```plantuml

start

while (no stop signal?)
    :close grab arms a little bit;
endwhile

while (no boundary detected?)
    :move a little bit forward;
endwhile

:align at the boundary;

:move forward out of boundaries;

:stop;

while (no stop signal?)
    :open grab arms a little bit;
endwhile

while (no boundary detected?)
    :move a little bit backwards;
endwhile

stop

```

## Concept v2

Idea:

* move to the middle 
* start moving in a spiral
* widen the spiral if obstacle detected
* follow the game border

```plantuml

start

:move forward to the middle of the playing field;
note right
    (by timing)
end note
:start moving in an expanding spiral;
note right
    avoid contact to non-targets by detecting them with IR / OD
    and passing them in an outer sphere
end note
if (target detected?) then (yes)
    stop
else (no)
    
endif

stop

```

## Micro concepts

### Align at boundary

```plantuml

start

:a game boundary was detected on one side;

while (other side also detected a boundary?)
    :run motor on the side which had no game boundary contact yet;
endwhile

stop

```
