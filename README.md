# reference-gpu-traces

Captured GPU traces and reference imagery for automated regression testing.

## Running Tests

To run tests check out the main xenia repo, ensure you have
[Git LFS](https://git-lfs.github.com/) installed, and run:

```
  $ xb gputest
```

You can find a results file at `build/gputest/results.html` containing diffs.

## Adding Traces

Pass `--trace_gpu_prefix=testdata/reference-gpu-traces/traces/` to xenia to
have captured traces be automatically placed in the right folder, or copy your
new trace files to `traces/` and `git add`.

Run the reference update only for your new files:

```
  $ xb gputest --generate_missing_reference_files
```

Commit the new traces and reference files.

## Updating Golden Reference Imagery

```
  $ xb gputest --update_reference_files
```

Commit any diffs (ensuring LFS is setup) and then bump the main xenia submodule
revision.
