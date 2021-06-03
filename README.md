# kustomize-ytt-generator

A kustomize generator plugin that runs ytt.

TODO: Write a sensible introduction here.

## Usage

This plugin is written in Python (any reasonably modern 3.x should be fine) and
requires [PyYAML][pyyaml] to be installed. The
easiest way to accomplish this is to run `pip install pyyaml` in a virtualenv
or similar. Also, `ytt` must be installed.

In order for `kustomize` find the plugin, it must live [in a specific
location][kustomize_placement]. The [examples][examples/] set the
`KUSTOMIZE_PLUGIN_HOME` environment variable to achieve this, but real-world
usage may require something different.

As with all kustomize plugins, configuration lives in a [YAML
file][kustomize_config] referenced in `kustomization.yaml`. In addition to the
usual `apiVersion`, `kind`, and `metadata` fields, the following are available:

| name             | required | description |
| ---------------- | -------- | ----------- |
| `template_path`  | yes      | Path to a directory containing ytt templates. |
| `values`         | yes      | Data values for ytt to populate templates with. |
| `extra_ytt_args` | no       | Any extra command line args to pass to ytt. |

A small example that demonstrates basic usage can be found at
[example/basic](example/basic).


[pyyaml]: https://pypi.org/project/PyYAML/
[kustomize_placement]: https://kubectl.docs.kubernetes.io/guides/extending_kustomize/#placement
[kustomize_config]: https://kubectl.docs.kubernetes.io/guides/extending_kustomize/#configuration
