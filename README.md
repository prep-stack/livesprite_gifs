# LiveSprite sprite packs

Community sprite packs for [LiveSprite](https://github.com/prep-stack/livesprite) -
the desktop program that puts animated GIF sprites on your screen and
notifies you when your favorite streamer goes live.

The **Browse packs...** button inside LiveSprite reads this repository:
it lists every pack in `packs/`, shows its animated preview, and lets
the user install or update it with one click.

## Repository layout

```
packs/
  <pack_id>/           one folder per sprite pack (lowercase, no spaces)
    pack.json          pack info - see below
    preview.gif        small animated preview shown in the Browse window
    *.gif              the sprite animations themselves
    *.png              optional icon/portrait shown in the manager list
```

### pack.json

```json
{
  "name": "Gawr Gura",
  "creator": "your-github-name",
  "version": "1.0.0",
  "preview": "preview.gif",
  "description": "One or two sentences about the pack."
}
```

- `name` - display name shown in the program
- `creator` - your name/handle, shown next to the pack
- `version` - `major.minor.patch`; **bump this every time you change
  anything in the folder**, otherwise installed copies won't see the update
- `preview` - filename of the preview GIF inside the pack folder
- `description` - optional short text

## Adding your own pack

1. Fork this repository
2. Create `packs/<your_pack_id>/` and put your GIFs in it
   - GIF filenames containing `run`/`walk` + `left`/`right`/`up`/`down`
     automatically get a matching walk direction in the program
   - keep GIFs reasonably small (they are drawn on people's desktops);
     transparent backgrounds look best
3. Add a `preview.gif` (one of your GIFs, or a dedicated small preview)
4. Add a `pack.json` (copy one from an existing pack and edit it)
5. Open a **Pull Request** - it will be reviewed before it goes live

## Updating your pack

1. Add/change/remove the files in your pack folder
2. **Bump the `version` in `pack.json`** (e.g. `1.0.0` -> `1.1.0`)
3. Open a Pull Request

Everyone who installed your pack gets the update offered inside
LiveSprite. Updates never touch the user's own settings (channels,
chances, directions) - only the GIF files are refreshed.

## Rules

- Only submit content you made or are allowed to redistribute
- No NSFW, no huge files, no non-GIF/PNG payloads
- Every Pull Request is manually reviewed before merging
