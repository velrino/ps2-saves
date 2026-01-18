# PS2 Saves for PCSX2

## Structure

```
saves/
├── Burnout3-USA.ps2                    (BASLUS-21050)
├── NFS-MostWanted-USA.ps2              (BASLUS-21351)
├── NFS-Carbon-USA.ps2                  (BASLUS-21494)
├── NFS-Underground2-USA.ps2            (BASLUS-21065)
├── MortalKombat-ShaolinMonks-USA.ps2   (BASLUS-21087)
└── ...
```

## How to add new saves

### 1. Download saves

- **GameFAQs**: https://gamefaqs.gamespot.com (search for game → Saves)
- **PS2-HOME**: https://www.ps2-home.com/forum/viewtopic.php?t=14285

Supported formats: `.psu`, `.max`, `.psv`, `.cbs`, `.xps`, `.sps`

### 2. Install mymcplus (only once)

```bash
cd /Users/velrino/Documents/ps2/saves
python3 -m venv venv
source venv/bin/activate
pip install mymcplus
```

### 3. Create memory card and import save

```bash
source venv/bin/activate
python -m mymcplus GameName-USA.ps2 format
python -m mymcplus GameName-USA.ps2 import /path/to/save.psu
python -m mymcplus GameName-USA.ps2 dir  # verify
```

### 4. In PCSX2

1. Settings → Memory Cards
2. Folder: `/Users/velrino/Documents/ps2/saves`
3. Select the `.ps2` file for the game in Slot 1

## Regions

**The save must be from the same region as the game!**

| Code | Region |
|------|--------|
| SLUS / BASLUS | USA (NTSC-U) |
| SLES / BESLES | Europe (PAL) |
| SLPM | Japan (NTSC-J) |

## Useful commands

```bash
# List saves on memory card
python -m mymcplus Game.ps2 dir

# Export save
python -m mymcplus Game.ps2 export BASLUS-XXXXX save.psu

# Delete save
python -m mymcplus Game.ps2 delete BASLUS-XXXXX
```
