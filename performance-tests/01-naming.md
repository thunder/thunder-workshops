## Used naming

- Elastic stack - docker compose stack with Elasticsearch, Kibana and APM Server
- APM Server - is service inside Elastic stack dedicated to accept application monitoring information and save them in Elasticsearch
- APM Agent - is client integrated in some application, that sends data to APM Server. We have to APM agents. The NodeJS agent is part of NightwatchJS testing application and it sends information directly from test. We will sometimes refer to it as `NightwatchJS tests agent`. The Browser RUM agent is loaded in Browser during execution of tests and it sends browser performance measurements.
- APM tracing, transaction, span - trace is one identifier for whole process, transaction is group of spans (fe. page load), span is the smallest unit of time measurement (fe. load of image file)
