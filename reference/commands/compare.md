---
description: Generate an Impact Report
---

# compare

```
piperider compare [options]
```

The comparison by recipe is achieved by executing the `piperider and dbt` commands by recipe configuration. The first run utilizes the base configuration, while the second run uses the target configuration. Subsequently, a comparison report is generated by the results obtained from both runs.

The default configuration will be generated while the project was initialized at `.piperider/compare/default.yml`.

For configuration details, please see the[ link](../../get-started/compare.md#comparison-recipe).

```
base:
  branch: main
  dbt:
    commands:
    - dbt deps
    - dbt build
  piperider:
    command: piperider run
target:
  dbt:
    commands:
    - dbt deps
    - dbt build
  piperider:
    command: piperider run
```

The `--recipe` option can pick up another configuration at `.piperider/compare/<recipe>.yml`Generate report

```shell
piperider generate-report [options]
```

Generate static HTML reports in `.piperider/outputs/<run>`  based on the profiling results of the latest `run` by default.

| Option           | Argument                    | Description                                                     |
| ---------------- | --------------------------- | --------------------------------------------------------------- |
| `--input`        | Path to the `run.json` file | Generate a report based on a specific profiling `run.json` file |
| `-o`, `--output` | Path                        | Specify the output directory for the generated report           |
| `--report-dir`   | Path                        | Specify the path to read and write reports                      |
| `--debug`        | N/A                         | Enable debugging output                                         |
| `--help`         | N/A                         | List command-line options                                       |