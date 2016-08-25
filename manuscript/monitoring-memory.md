# Monitoring memory

(TODO: fill in) heap dump, gc before reporting, memory leak detection, agent protocol, attaching agent to a running JVM, using old PerfCake build for compatibility with 1.5 Java


## Scenario memory.xml:
{lang=xml, linenos=on}
   <?xml version="1.0" encoding="utf-8"?>
   <scenario xmlns="urn:perfcake:scenario:7.0">
      <run type="time" value="300000"/>
      <generator class="DefaultMessageGenerator" threads="100"/>
      <sender class="HttpSender">
         <target>http://${server.host}:8888/</target>
         <property name="method" value="POST"/>
      </sender>
      <reporting>
         <reporter class="MemoryUsageReporter"">
            <property name="agentHostname" value="${server.host}"/>
            <property name="agentPort" value="8850"/>
            <destination class="ConsoleDestination">
               <period type="time" value="5000"/>
            </destination>
         </reporter>
      </reporting>
      <messages>
         <message content="payload"/>
      </messages>
   </scenario>

## Scenario memory-heapdump.xml:
{lang=xml, linenos=on}
   <?xml version="1.0" encoding="utf-8"?>
   <scenario xmlns="urn:perfcake:scenario:7.0">
      <run type="time" value="300000"/>
      <generator class="DefaultMessageGenerator" threads="100"/>
      <sender class="HttpSender">
         <target>http://${server.host}:8888/</target>
         <property name="method" value="POST"/>
      </sender>
      <reporting>
         <reporter class="MemoryUsageReporter"">
            <property name="agentHostname" value="${server.host}"/>
            <property name="agentPort" value="8850"/>
            **<property name="memoryDumpOnLeak" value="true"/>**
            <destination class="ConsoleDestination">
               <period type="time" value="5000"/>
            </destination>
         </reporter>
      </reporting>
      <messages>
         <message content="payload"/>
      </messages>
   </scenario>