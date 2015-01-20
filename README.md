luke
====

Luke for PES Lucene, merged from https://github.com/DmitryKey/luke

Usage 1: Launching with dependencies packaged in 'lib' folder 

```bash
mvn clean package
cd target
java -jar luke-4.2.0-SNAPSHOT.jar


Usage 2: Launching with dependencies embedded with single jar 

```bash
mvn clean package
cd target
unzip luke-with-deps.jar
```bash

Edit 3 following files by adding codecs missing:
- luke-with-deps.jar\META-INF\services\org.apache.lucene.codecs.Codec
...
org.apache.lucene.codecs.lucene40.Lucene40Codec
org.apache.lucene.codecs.lucene410.Lucene410Codec
org.apache.lucene.codecs.lucene41.Lucene41Codec
org.apache.lucene.codecs.lucene42.Lucene42Codec
org.apache.lucene.codecs.lucene45.Lucene45Codec
org.apache.lucene.codecs.lucene46.Lucene46Codec
org.apache.lucene.codecs.lucene49.Lucene49Codec

- luke-with-deps.jar\META-INF\services\org.apache.lucene.codecs.PostingsFormat
...
org.apache.lucene.codecs.lucene40.Lucene40PostingsFormat
org.apache.lucene.codecs.lucene41.Lucene41PostingsFormat


- luke-with-deps.jar\META-INF\services\org.apache.lucene.codecs.DocValuesFormat
...
org.apache.lucene.codecs.lucene40.Lucene40DocValuesFormat
org.apache.lucene.codecs.lucene410.Lucene410DocValuesFormat
org.apache.lucene.codecs.lucene42.Lucene42DocValuesFormat
org.apache.lucene.codecs.lucene45.Lucene45DocValuesFormat
org.apache.lucene.codecs.lucene49.Lucene49DocValuesFormat


Repackaging luke-with-deps.jar and distribute in any location
java -jar luke-with-deps.jar