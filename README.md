# Tern OMP Layout Fixes

A small [Tern](https://stencil.so/tern) plugin that adjusts OMP's native surface layout:

- Expands OMP transcripts from Tern's centered Reader, Spine, or Console measure to the available pane width.
- Adds `36px` of separation between the transcript tail and Tern's sticky composer.

The plugin affects only surface regions with `data-surface="omp.session"`. Other terminal programs, Tern plugin blocks, and OMP overlays are unchanged.

## Install

Install from GitHub:

```powershell
tern plugin install github.com/0xGREG/tern-omp-layout-fixes
```

To install from a local checkout:

```powershell
tern plugin install C:\path\to\tern-omp-layout-fixes
```

Tern reloads plugins after installation. If an existing window has not repainted, run:

```powershell
tern plugin reload
```

## Develop

Link the checkout so edits reload in place:

```powershell
tern plugin link C:\path\to\tern-omp-layout-fixes
tern plugin list
```

Tern watches linked plugin files and normally reloads changes automatically. Use `tern plugin reload` to force a reload.

## Remove

```powershell
tern plugin remove omp-layout-fixes
```

## How it works

Tern exposes documented global stylesheet hooks for native program surfaces. This plugin targets:

```css
.sf-main[data-surface="omp.session"]
```

The width declarations override Tern's built-in chat skin measure, while bottom padding keeps the final transcript block away from the composer dock. No OMP source modification is required.

## License

[MIT](LICENSE)
