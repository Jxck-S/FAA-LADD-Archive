# FAA-LADD-Archive

A historical archive of the FAA **LADD** (Limiting Aircraft Data Displayed)
filter files that drive [laddlist.com](https://laddlist.com).

## Layout (git-native)

Each weekly FAA update overwrites stable filenames and is recorded as **one
commit dated to the email**:

| File | Source attachment |
|------|-------------------|
| `industry_filter.txt` | `LADD_Industry_Filter_*.txt` — the full Industry block list |
| `remove.txt` | `LADD_remove_*.txt` — that week's removals as reported by the FAA |

The **git history is the archive** — there are no date folders. To see what
changed:

```bash
git log -p industry_filter.txt        # every week's added (+) / removed (-) regs
git blame industry_filter.txt         # when each registration first appeared
git log --since=2025-01-01 industry_filter.txt
```

## History

The repo originally stored one snapshot per `YYYY/Month/DD/` folder. It was
migrated to this git-native layout by a one-time script that replayed each
historical snapshot as a dated commit.
