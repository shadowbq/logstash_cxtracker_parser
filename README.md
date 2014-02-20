logstash_cxtracker_parser
=========================

CXTracker format string. 

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
