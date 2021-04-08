[![Greenpeace](https://circleci.com/gh/greenpeace/planet4-helm-apm.svg?style=shield)](https://circleci.com/gh/greenpeace/planet4-helm-apm)

![Planet4](./p4logo.png)
# ElasticStack [APM](https://www.elastic.co/apm)

Free and open application performance monitoring.  Used by Wordpress php to post web site transaction data.  Extracted for recharging P4 websites to NROs.

<h1>Important Notes</h1>

>Ensure compatibility with:
- [Elasticsearch](https://github.com/greenpeace/planet4-helm-elasticsearch) 
- [Wordpress APM Agent Elasticsearch plugin](https://github.com/matheusevangelista/Wordpress-APM-Agent-Elasticsearch) in WP
- [ES-exporter](https://github.com/greenpeace/planet4-helm-esexporter)
- [Kibana](https://github.com/greenpeace/planet4-helm-kibana)

***
### Requirements - Internal Only
-   Access to P4 Infra [environment](https://www.notion.so/p4infra/bab9d0b1f2db4d929a59916899d531c1?v=eca7b78e1ae345c6883a9b37c6b76cac)

### Built with
- [apm](https://github.com/elastic/helm-charts/tree/7.9/apm-server) helm chart

### Deployment
This repository is deployed via [CircleCI](https://circleci.com/gh/greenpeace/planet4-traefik)

 - Commits to the develop branch trigger deployment to the development cluster.  
 - Create a PR for review to prepare for production deployment.
 - Approval and merge deploys to production.

### Usage
 - To access APM from within the cluster use:
     `http://apm-apm-server.elastic.svc.cluster.local:8200`
 - Clone the repo to access makefile commands via cli that are not executed via CircleCI
   - `make status` - <em> display status of named release </em>
   - `make value` - <em> display user values followed by all values deployed </em>
   - `make history` - <em> display deployment history of named release </em>
   - `make uninstall` - <em> delete release while retaining history, CRDs, PVs etc.</em>
   - `make destroy` - <em> destroy release including CRDs, PVs etc. </em> <strong> CAUSES DATA LOSS </strong>

 ### Infra Documentation
 - External
   - [Planet 4 Handbook](https://app.gitbook.com/@greenpeace/s/planet4/infrastructure/intro)
 - Internal use only
   - [P4 Notion](https://www.notion.so/p4infra/)

 ### Contributing
 If your interested in contributing to P4 Infrastructure code please check our our community page [here](https://github.com/greenpeace/planet4).
