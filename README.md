# Sending Ganglia Metrics to InfluxDB and ElasticSearch

## Making the Metrics for the ClassAds

Official documentation can be found here:
	https://htcondor.readthedocs.io/en/stable/admin-manual/monitoring.html?highlight=ganglia

The Metric must be constructed in this exact way:

1. For Metrics tagged with 2 tags w/ float/int type values:\
[\
	Aggregate = "%";\
	Name = "MetricName\~tag1\~tag2";\
	Value = ClassAd_Name;\
	Units = "%";\
	Desc = "%";\
	Requirements = "%";\
	TargetType = "%";\
]

1. For Metrics tagged with one tag w/ float/int type values:\
[\
	Aggregate = "%";\
	Name = "MetricName~tag";\
	Value = ClassAd_Name;\
	Units = "%";\
	Desc = "%";\
	Requirements = "%";\
	TargetType = "%";\
]

1. For Metrics tagged with one tag w/ String type values:\
[\
	Aggregate = "%";\
	Name = "MetricName(+st)Class_Ad~tag";\
	Value = 1;\
	Units = "%";\
	Desc = "%";\
	Requirements = "%";\
	TargetType = "%";\
]

1. For Non Tagged Metrics:\
[\
	Aggregate = "%";\
	Name = "MetricName";\
	Value = ClassAd_Name;\
	Units = "%";\
	Desc = "%";\
	Requirements = "%";\
	TargetType = "%";\
]

## Sending Metrics with ElasticSearch:
1. rabbitmq.json should be templated in the same way and copied to the same directory as metrics-influxdb-condor-gangliad
1. ElasticSearch can be enabled/disabled by setting sendViaES to False in metrics-influxdb-condor-gangliad
