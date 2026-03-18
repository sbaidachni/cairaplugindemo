# CAIRA File Mapping (Dynamic Discovery)

Do not maintain static architecture/module lists here. Discover from CAIRA repository APIs at execution time.

## Canonical discovery endpoints

- Reference architectures: `https://api.github.com/repos/microsoft/CAIRA/contents/reference_architectures?ref=<ref>`
- Modules: `https://api.github.com/repos/microsoft/CAIRA/contents/modules?ref=<ref>`
- Docs: `https://api.github.com/repos/microsoft/CAIRA/contents/docs?ref=<ref>`
- Guides: `https://api.github.com/repos/microsoft/CAIRA/contents/guides?ref=<ref>`

## File inspection pattern

For each discovered architecture directory:

1. Read `README.md` for scenario and requirements context.
2. Read `main.tf`, `variables.tf`, `outputs.tf`, and any additional `.tf` files present.
3. Extract module dependencies from Terraform `source` declarations.
4. Build an architecture capability snapshot from actual files.

## Evidence requirements

All recommendations should cite repository URLs used as evidence.

Example URL forms:

- `https://github.com/microsoft/CAIRA/blob/<ref>/reference_architectures/<architecture>/README.md`
- `https://github.com/microsoft/CAIRA/blob/<ref>/reference_architectures/<architecture>/main.tf`
- `https://github.com/microsoft/CAIRA/tree/<ref>/modules`
