## What is a time-series database?

When it comes down to a collection of observations obtained by repeated
measurements over time. This is called time series data, or time-series data. The
time series data is tracked over time and can refer to, for example, the
amount of load the server has in one hour. This time series data can be
obtained by various sensors or systems that obtain data and link it to a time. This
is then stored in a time-series database
 
Compared to SQL databases, time series databases are made to store time series data for a small amount of time
save period. With the storage over a shorter period, the queries can be delivered more quickly. And
options such as complex queries and relations are not possible in a time-series database.

---

## Important Concepts of Influx DB.
DOT framework methods used:
- Literature Study (Library)
- Best good and bad practices (Library)
 
Before the implementation of an Influx DB database is realized, it is desirable to have the right
use of the database. With proper use, it is hoped that the time-series
database can be optimally used within this project. To realize this, the documentation of
Consulted Influx DB to get the important concepts.
 
For example, it is important that the data that is stored in an Influx DB database is given a time. The
time that is passed along is used as a 'unique key' within the database. That's how the data is
is stored uniquely and cannot be duplicated within the database. It is without time
not possible to store the data within an Influx DB database.

It is also important to distinguish the data type in Influx DB in the correct element: tags or field.
For example, tags are made specifically for text only and give the data a characteristic property such as
the location or name of the data. Within Influx this can be used as a filter on data, giving a tag
the values in numbers and decimals. This can be plotted with a series of time units.
If the tags and field are formatted incorrectly, it may not be possible to use them
of filters on tags and/or incorrect display of time series data.

Alternatives for InfluxDB are Timescale DB and Prometheus DB. But dont have great integration with Grafana as Influx Db has.

### Grafana 

In the comparison with other visualization tools, it has come to the conclusion that Grafana is the most popular in data visualization
tools due to the open-source and flexibility in data source plug-ins. As a result, there are few imitations
tied to using this tool.

With the given metrics from InfluxDB Grafana can plot out different timeseries graphs.