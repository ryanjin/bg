---
title: solr-command
date: '2019-01-25'
description:
categories:
	- solr

tags:
	- solr

---

healthcheck

	<str name="df">error</str>
    <str name="healthcheckFile">server-enabled.txt</str>


	http://gy-solr03:8983/solr/invoketrace_shard1_0_1_0_replica2/admin/ping?wt=json
	{"responseHeader":{"status":0,"QTime":0,"params":{"q":"solrpingquery","wt":"json","df":"error","echoParams":"all","distrib":"false","rows":"10"}},"status":"OK"}

clusterstatus

	http://gy-solr03:8983/solr/admin/collections?action=clusterstatus&wt=

collections-list

	http://localhost:8983/solr/admin/collections?action=LIST&wt=json

core-list

	http://gy-solr03:8983/solr/admin/cores?wt=json


