## Preparing of local environment

You need following tools and software installed on local machine.

- installed `docker` - [https://docs.docker.com/install](https://docs.docker.com/install)
- installed `docker-compose` - [https://docs.docker.com/compose/install](https://docs.docker.com/compose/install)
- installed yarn (>= 1.6) - [https://yarnpkg.com/docs/install](https://yarnpkg.com/docs/install)
- installed node (>= 8.11) - [https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)
- installed latest development version of Thunder with following modules (sampler, thunder_performance_measurement, testsite_builder)
- ready local repository of: https://github.com/thunder/docker-thunder-performance - with the editor of your choice for it
- Local Elastic Stack – checkout https://github.com/elastic/stack-docker with patch and follow instructions to run it
- Local Grafana – follow the instruction on https://grafana.com/docs/installation/docker/

### Setup Tools

1. Setup APM server and Kibana for APM monitoring

- visit [http://localhost:5601/app/apm](http://localhost:5601/app/apm). Your page will be empty. You should click on `Setup Instructions` there. On new page, click on `Check APM Server status` after that `Load Kibana objects` and at end `Launch APM`. After that, your Elasic stack is ready to receive APM data from Nightwatch JS Tests.

2. Setup Thunder installation

- follow instructions provided in Thunder distribution `development.md` file, part about `How to run the NightwatchJS performance tests`.
- do not use `https`. There is too much hassle about that to pay off for local development

3. Create content for testing

- download following file `https://raw.githubusercontent.com/thunder/thunder-performance-site-templates/master/thunder_base_set.json` to `docroot` of your Thunder installation
- execute following command to generate content `drupal testsite-builder:create-config thunder_base_set.json --create-content` - let it run, it will take some time.

4. Setup Grafana

- visit [http://localhost:3000/datasources](http://localhost:3000/datasources). Add new Elasticsearch data source for your local Elastic stack.
