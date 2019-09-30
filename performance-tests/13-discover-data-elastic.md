## Discover data in Elastic stack

Navigate to your local Kibana [http://localhost:5601](http://localhost:5601).

Following parts are interesting for us:
- APM
- Discover

### Discover

We will mainly use `Discover` functionality to find data relevant for us. Most important fields for us are:

- `context.service.name` - defined by APM agent. With this one we can differentiate measurements from NightwatchJS tests agent and from Browser RUM agent.
- `context.tags.test` - it's test name, but function name from JS file. fe. `createMostUsedContent`
- `context.tags.branch` - branch name where test is running on (not so important for local development)

Let's try find some of our measurements.

Type in search field following: `context.tags.test:<YOUR TEST FUNCTION NAME>`. That should filter all data related to your test.

After that, we can narrow search even more down. For example: `context.tags.test : <YOUR TEST FUNCTION NAME> AND context.service.name : "NightwatchJS - Test"`

To reduce amount of displayed data on page, you can select specific columns, by clicking on `Add` next to it. For example: `span.name` and `transaction.name`.

And even more with adding of important span name to filter. For example: `span.name : "<NAME OF IMPORTANT MEASUREMENT FOR YOUR TEST"`
