# FixupSocialEmbeds

An Equicord/Vencord user plugin that replaces social media URL hosts with
embed-friendly alternatives immediately before sending or editing a message.

It ships with these replacements:

| Input host | Output host |
| --- | --- |
| `x.com` | `fixupx.com` |
| `instagram.com` | `hhinstagram.com` |

Paths, query parameters, and fragments are preserved. Replacements only match
the exact configured hostname, so `x.com` does not accidentally match
`notx.com`.

## Install

Clone this repository into Equicord's `src/userplugins` directory:

```sh
git clone https://github.com/mia-cx/equicord-plugins.git \
  src/userplugins/FixupSocialEmbeds
```

Then rebuild Equicord and enable **FixupSocialEmbeds** in the Plugins settings.

## Configure

Open Equicord Settings → Plugins → FixupSocialEmbeds. You can edit, add, or
remove as many input/output host pairs as you want.

For example:

```text
https://x.com/example/status/123?foo=bar
→ https://fixupx.com/example/status/123?foo=bar
```

The plugin runs on both new messages and edited messages.
