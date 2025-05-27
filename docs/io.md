# IO

## Types

- ClickEvent: MouseUp | MouseDown
- For x and y coordinates, use a 2D vector: typedef struct (x, y) Vector2D
- Left-click down position (x, y): typedef struct (x, y) LCDPosition
- Segment of LCDPositions: typedef SingleLinkedList<LCDPosition> Segment
- Timestamp to LCDPosition: Vector<Pair<Timestamp, LCDPosition>>
- toggle when ClickEvent changes: bool

## Inputs

- 

## Outputs

- 