# GitHub Actions DAG (Directed Acyclic Graph) Examples

This repository demonstrates a practical example of Directed Acyclic Graph (DAG) workflow in GitHub Actions.

## Workflow Structure

The workflow consists of 4 jobs with the following dependencies:

```mermaid
graph TD
  job1[Job 1]
  job2[Job 2]
  job3[Job 3]
  job4[Job 4]
  job1 --> job3
  job2 --> job3
  job2 --> job4
  job3 --> job4
```

## Job Dependencies

- `job-1` and `job-2` run independently
- `job-3` requires both `job-1` and `job-2` to complete
- `job-4` requires both `job-2` and `job-3` to complete

## Implementation Details

- All jobs run on `ubuntu-24.04`
- Each job prints start and completion messages
- Dependencies are managed using the `needs` keyword
- Workflow triggers on pushes to `main/*` branches

## Usage

1. Copy the workflow file to `.github/workflows/`
2. Push changes to a branch matching `main/*`
3. Monitor the workflow execution in GitHub Actions tab

## License

MIT
