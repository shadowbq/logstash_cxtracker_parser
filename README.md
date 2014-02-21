logstash cxtracker parser
=========================


As a long time user of Passive collected NETFLOW (IPFIX) tools like SANCP and CXTracker I've scraped together a 'bad ass' netflow tool that is now ultra scalable good bye SQL.. (thank god). 

https://github.com/shadowbq/logstash_cxtracker_parser

CXTracker:

https://github.com/gamelinux/cxtracker


------------------------------

http://www.elasticsearch.org/

An end-to-end search and analytics platform. infinitely versatile.

The Elasticsearch ELK Stack

"By combining the massively popular Elasticsearch, Logstash and Kibana we have created an end-to-end stack that delivers actionable insights in real-time from almost any type of structured and unstructured data source. Built and supported by the engineers behind each of these open source products, the Elasticsearch ELK stack makes searching and analyzing data easier than ever before." - snip.. 

Logstash

Scrub, parse, and enrich.
like soap for your data.

"Logstash helps you take logs and other time based event data from any system and store it in a single place for additional transformation and processing. Logstash will scrub your logs and parse all data sources into an easy to read JSON format." snip .. 

---------

CXTracker  format string. 

<pre>
%cxd %stm %etm %dur %pro %sip %spt %dip %dpt %spk %sby %dpk %dby %sfl %dfl %ver
</pre>    

Example Record from CXTracker. 

<pre>
1392755693000049942 2014-02-18 20:34:53 2014-02-18 20:35:09 16 6 10.1.1.17 53022 55.58.243.137 80 24 7236 8 1174 27 27 2 
</pre>

Successfully Parsed Data

<pre>
{
       "message" => "1392755693000049942 2014-02-18 20:34:53 2014-02-18 20:35:09 16 6 10.1.1.17 53022 55.58.243.137 80 24 7236 8 1174 27 27 2",
      "@version" => "1",
    "@timestamp" => "2014-02-20T22:17:10.730Z",
          "type" => "example",
          "host" => "someplace.nowhere.org",
          "cxid" => "1392755693000049942",
    "start_time" => "2014-02-18T15:34:53.000-05:00",
      "end_time" => "2014-02-18T15:35:09.000-05:00",
           "dur" => "16",
         "proto" => "TCP",
        "src_ip" => "10.1.1.17",
      "src_port" => "53022",
        "dst_ip" => "55.58.243.137",
      "dst_port" => "80",
      "src_pkts" => "24",
     "src_bytes" => "7236",
      "dst_pkts" => "8",
     "dst_bytes" => "1174",
        "family" => "AF_INET",
       "src_CWR" => "FALSE",
       "src_ECE" => "FALSE",
       "src_URG" => "FALSE",
       "src_ACK" => "TRUE",
      "src_PUSH" => "TRUE",
       "src_RST" => "FALSE",
       "src_SYN" => "TRUE",
       "src_FIN" => "TRUE",
       "dst_CWR" => "FALSE",
       "dst_ECE" => "FALSE",
       "dst_URG" => "FALSE",
       "dst_ACK" => "TRUE",
      "dst_PUSH" => "TRUE",
       "dst_RST" => "FALSE",
       "dst_SYN" => "TRUE",
       "dst_FIN" => "TRUE"
}
</pre>
