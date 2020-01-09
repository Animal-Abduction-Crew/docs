# Ideas for the firmware of the robot <!-- omit in toc -->

Brainstorming ideas for developing our robot 🙂

- [Controllers](#controllers)
  - [Movement controller](#movement-controller)
  - [Loading controller](#loading-controller)
  - [Ultrasonic sensor controller](#ultrasonic-sensor-controller)
  - [Line detection sensor controller](#line-detection-sensor-controller)
  - [Object detection controller](#object-detection-controller)
- [TODO](#todo)

## Controllers

Modules which map real world functionalities

### Movement controller

Capabilities:

* Move forward for x seconds
* Move backwards for x seconds
* Rotate left for x seconds
* rotate right for x seconds

API proposal:

```csharp
void Move(Direction direction, Duration duration);
void Rotate(Direction direction, Duration duration);
```

### Loading controller

Capabilities:

* Grab an animal
* Release the animal again

API proposal:

```csharp
void GrabTarget();
void ReleaseTarget();
```

### Ultrasonic sensor controller

Capabilities:

* measures distance (in cm) to objects in front of the robot
* emits an event if an object is about to collide with the robot

API proposal:

```csharp
int MeasureDistance();

// event props
int distance;
DateTime occuredAt;
```

### Line detection sensor controller

Capabilities:

* emits an event if a contrast on the floor is detected (black duct tape = game boundary)

### Object detection controller

Capabilities:

* emits an event if the target was detected with a high probability

API proposal:

```csharp
// event props
double probability;
int maxX;
int maxY;
int minX;
int minY;
```

## TODO

* Describe control flows
* Find a way to intercept control flows for important event reactions without abandoning the current control flow
* probably a lot more 😄