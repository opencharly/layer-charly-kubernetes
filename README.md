# charly-kubernetes

The `charly-kubernetes` family — the Kubernetes deployment and cluster-probe
skills.

The `charly-kubernetes` candy is a **concept candy**: it ships no install
content and owns the `kubernetes` family of `skill:` entities. It currently
carries three entities:

- `kubernetes` — `charly fleet add`, `charly fleet from-box`, Kustomize manifest
  generation, cluster profiles, Kubernetes deployments, the `deploy:` block in
  the deploy spec, and OCI-label capabilities.
- `helm` — the helm words: the `step:helm-release` install step and the
  `verb:helm` release-status assertion, plus the `helm_charts:` deploy field.
- `check-k8s` — the declarative `kube:` check verb (nodes, pods, ingress,
  storage class, addon health, apply/delete, raw resource GETs), served
  out-of-process by `candy/plugin-kube`.

The `kind` skill of the same family is owned by the sibling `opencharly/layer-kind`
repo. `candy/plugin-marketplace` regenerates the standalone
[opencharly/marketplace](https://github.com/opencharly/marketplace) corpus from
these entities, so the skills are authored here and projected there.

## What it provides

| Property | Value |
|---|---|
| Layer / candy | `charly-kubernetes` (concept candy) |
| Install content | none — a `true` no-op `plan:` |
| Owns | 3 `skill:` entities: `kubernetes`, `helm`, `check-k8s` |
| Projected to | `marketplace/kubernetes/skills/` |
| Service / port | none |

## How to use it

This repo is consumed as a **skill source**, not as an image layer. Edit the
`skill:` entities in `charly.yml`; the marketplace regeneration projects them
into `/charly-kubernetes:*` pages. To reference the repo directly, compose it in
a box. A box is a `candy:` node that carries the box's `base:` image and a nested
`candy:` list of layer refs (the nested `candy:` is the composition list; the
outer `candy:` is the box body):

```yaml
my-box:
  candy:                  # the box body (an IMAGE is a `candy:` node carrying `base:`)
    base: fedora          # the box's base image
    candy:                # the box's composition list
      - '@github.com/opencharly/layer-charly-kubernetes:v2026.269.1757'
```

## Layout

- `charly.yml` — the `charly-kubernetes:` concept candy entity plus three
  `skill:` entities (`kubernetes`, `helm`, `check-k8s`).
- `.github/workflows/tag-on-merge.yml` — CalVer tag + `CHANGELOG/` on merge.
- `README.md` — this user overview.

## Related

- Owning skills: `/charly-kubernetes:kubernetes`, `/charly-kubernetes:helm`,
  `/charly-kubernetes:check-k8s`
- Authoring reference: `/charly-image:layer`
- Sibling: `opencharly/layer-kind`
- [`opencharly/marketplace`](https://github.com/opencharly/marketplace) — the projected corpus
- [`opencharly/charly`](https://github.com/opencharly/charly) — the charly CLI and image builder
- [`opencharly/opencharly`](https://github.com/opencharly/opencharly) — the umbrella
