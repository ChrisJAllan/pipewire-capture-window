# pipewire-capture-window
Send audio from a window to a virtual capture device

## Usage

1. Make a virtual input to loop captured audio.

Example pipewire.conf:
```
# ...
context.objects = [
    {   factory = adapter
        args = {
            factory.name     = support.null-audio-sink
            node.name        = "capture"
            node.description = "Virtual Capture"
            media.class      = "Audio/Source/Virtual"
            audio.position   = "FL,FR"
        }
    }
    # ...
]
```

2. Edit `capture-window` and change `DEST="capture"` to the `node.name`.

3. Run script, select window, and direct whatever recording program to use the loop device.
