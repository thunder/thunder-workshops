## Writing of test

Everyone has one test template for test, but we need short explanation of different parts.

Let's take a look at `tests/src/Nightwatch/Tests/CreateMostUsedContent.js`.

We have:
- includes for APM agent and Thunder utils
- we have to fetch Site information for some tests
- at the beginning of the test we have to initialize APM agent. To do that we have to call `performance.startMeasurement` function
- marking of sub-tasks
- closing test measurement, will close trace

Everyone has template with TODO comments.

Let's fill some data into Kibana by executing test in loop: `for i in {1..10}; do yarn test:nightwatch ../profiles/contrib/thunder/tests/src/Nightwatch/Tests/<YOUR TEST FILE>; done`
