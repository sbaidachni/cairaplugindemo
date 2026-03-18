# Scaffold Modes (Repository-Driven)

## Default

Default to `reference` mode unless user asks for a copied/self-contained layout.

## `reference` mode

- Keep selected architecture files close to upstream.
- Convert local module paths to pinned git module references.
- Pin to explicit tag/commit for reproducibility.

Template:

```hcl
source = "git::https://github.com/microsoft/CAIRA.git//modules/<module_name>?ref=<ref>"
```

## `copy` mode

- Copy discovered architecture files and only required modules.
- Determine required modules dynamically from Terraform `source` declarations discovered in selected architecture files.

## Ref resolution template

```bash
curl -s https://api.github.com/repos/microsoft/CAIRA/releases/latest
```

Use `.tag_name` from the response when user does not specify a ref.

## Safety constraints

- Do not overwrite existing files without explicit confirmation.
- Always show planned file changes before writing.
