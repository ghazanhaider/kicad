# KiCad






## KiCad bindings

Connect:
```
from kipy import KiCad
kicad = KiCad()
board = KiCad.get_board()
print(f"Connected to KiCad {kicad.get_version()}")
print(f"Active Layer is {board.get_active_layer()}")
```

PCB Tracks:
```
board = KiCad().get_board()
for t in board.get_tracks():
    if (t.layer == board.get_active_layer()) & (t.width not in [156400,156500,142500,300000,500000,180000]):
        print("Width: " + str(t.width) + "  Layer: " + str(t.layer) + " Net: " + str(t.net))
        board.add_to_selection(t)
```




### Older PCBNEW bindings:

```
import pcbnew
board = pcbnew.GetBoard()
tracks = board.GetTracks()
layer = board.GetLayerID("Mid.Cu")
fp_list = brd.GetFootprints()
tracks=board.GetTracks()

badtracks=[]
for t in board.GetTracks()
    print("Width: " + str(t.GetWidth()) + "Layer: " + str(t.GetLayer()))
```


https://www.atomic14.com/2022/10/24/kicad-python-scripting-cheat-sheet
https://kicad.mmccoo.com/index.php/2017/02/01/modifying-pcbnew-layout-from-python/

