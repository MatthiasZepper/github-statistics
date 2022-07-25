# tempo

Repo for collecting and storing open source metrics - developed by [Harrison Hogg](https://hogg.io) for Spotify and [Backstage](https://github.com/backstage) and published under the [Apache 2.0 licens]e(https://github.com/backstage/backstage/blob/master/LICENSE). Currently trial-running to collect the Github metrics for nf-core community.  

## Scripts

### `$ yarn generate`

Generates the metrics for the entire nf-core org.

#### Args

- `--withAdopterList` - Fetches and processes the adopter list
- `--withMetrics` - Fetches and processes pull request and issue metrics
- `--commitChange` - Commits the metric changes back to the repo, when omitted it runs in a dryrun mode.

## Shape of [metrics.json](./metrics.json)

```ts
{
    /**
     * List of the adopters taken from then
     * backstage/backstage/ADOPTERS.md file
     */
    namesOfAdopters: string[];
    /**
     * List of contributors that have either
     * submitted a pull request or opened
     * an issue.
     */
    namesOfContributors: string[];
    /**
     * List of new contributors that have either
     * submitted a pull request or opened
     * an issue.
     */
    namesOfContributorsNew: string[];
    /**
     * Number of pull requests in the last
     * month
     */
    numberOfPullRequestNew: number;
    /**
     * p50 number of new pull requests
     * submitted every week
     */
    p50NumberOfPullsPerWeek: number;
    /**
     * p50 number of new contributors
     * every week.
     */
    p50NumberOfNewContributorsPerWeek: number;
    /**
     * p50 of the time pull requests in the
     * last 30 days have been opened to the
     * time they were closed.
     */
    p50SecondsToClosePulls: number;
    /**
     * p50 of the time issues in the
     * last 30 days have been opened to the
     * time they were closed.
     */
    p50SecondsToCloseIssues: number;
    /**
     * mean number of new pull requests
     * submitted every week
     */
    meanNumberOfPullsPerWeek: number;
    /**
     * mean number of new contributors
     * every week.
     */
    meanNumberOfNewContributorsPerWeek: number;
    /**
     * mean of the time pull requests in the
     * last 30 days have been opened to the
     * time they were closed.
     */
    meanSecondsToClosePulls: number;
    /**
     * mean of the time issues in the
     * last 30 days have been opened to the
     * time they were closed.
     */
    meanSecondsToCloseIssues: number;
}
```
