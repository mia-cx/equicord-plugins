# Equicord Plugins

A collection of Equicord/Vencord user plugins.

## Plugins

| Plugin | Description |
| --- | --- |
| [FixupSocialEmbeds](./fixupSocialEmbeds) | Replaces social-media URL hosts with embed-friendly alternatives before sending or editing a message. |

Each plugin lives in its own camelCase directory with an `index.ts` or
`index.tsx` entry point, matching Equicord's user-plugin layout.

## Install

User plugins require an Equicord source build. If `src/userplugins` does not
already contain anything you need to keep, clone this collection directly into
that directory:

```sh
cd /path/to/Equicord
git clone https://github.com/mia-cx/equicord-plugins.git src/userplugins
pnpm build
pnpm inject
```

If you already have user plugins, clone the collection elsewhere and symlink
only the plugins you want:

```sh
git clone https://github.com/mia-cx/equicord-plugins.git /path/to/equicord-plugins
ln -s /path/to/equicord-plugins/fixupSocialEmbeds \
  /path/to/Equicord/src/userplugins/fixupSocialEmbeds

cd /path/to/Equicord
pnpm build
pnpm inject
```

After the initial injection, rebuild and restart Discord whenever a plugin is
added or updated. Enable installed plugins under **Equicord Settings → Plugins**.

## Adding a plugin

Create one top-level camelCase directory per plugin:

```text
equicord-plugins/
├── fixupSocialEmbeds/
│   └── index.tsx
└── anotherPlugin/
    └── index.ts
```

Add the plugin to the table above and keep plugin-specific documentation in
that plugin's directory.
