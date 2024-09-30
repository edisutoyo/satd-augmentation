# Replication Package of Deep Learning and Data Augmentation for Detecting Self-Admitted Technical Debt

## Description of this study:

Self-Admitted Technical Debt (SATD) refers to circumstances where developers use textual artifacts to explain why the existing implementation is not optimal. Past research in detecting SATD has focused on either identifying SATD (classifying SATD items as SATD or not) or categorizing SATD (labeling instances as SATD that pertain to requirement, design, code, test, etc.). However, the performance of these approaches remains suboptimal, particularly for specific types of SATD, such as test and requirement debt, primarily due to extremely imbalanced datasets. To address these challenges, we build on earlier research by utilizing BiLSTM architecture for the binary identification of SATD and BERT architecture for categorizing different types of SATD. Despite their effectiveness, both architectures struggle with imbalanced data. Therefore, we employ a large language model data augmentation strategy to mitigate this issue. Furthermore, we introduce a two-step approach to identify and categorize SATD across various datasets derived from different artifacts. Our contributions include providing a balanced dataset for future SATD researchers and demonstrating that our approach significantly improves SATD identification and categorization performance compared to baseline methods.

Therefore, to showcase the effectiveness of our approach, we compared it against several existing approaches:

1. Natural Language Processing (NLP) and Matches task Annotation Tags (MAT) [Github](https://github.com/Naplues/MAT)
2. eXtreme Gradient Boosting+Synthetic Minority Oversampling Technique (XGBoost+SMOTE) [Figshare](https://figshare.com/s/87a4b5002c7488822e60)
3. eXtreme Gradient Boosting+Easy Data Augmentation (XGBoost+EDA) [Github](https://github.com/shenyuanduanzui/xgboost_satd)
4. MT-Text-CNN [Github](https://github.com/yikun-li/satd-different-sources-data)
5. LightGBM [Github](https://github.com/Wxxxxx2023/SATD-code)
6. JSD Generative Adversarial Network [Link](https://doi.org/10.1016/j.infsof.2023.107190)


## Structure of the replication package:
In accordance with the original dataset, the dataset comprises four distinct CSV files delineated by the artifacts under consideration in this study. Each CSV file encompasses a text column and a class, which indicate classifications denoting specific types of SATD, namely code/design debt (C/D), documentation debt (DOC), test debt (TES), and requirement debt (REQ) or Not-SATD.

```
├── SATD Keywords
│  ├── Keywords based on Source of Artifacts
│  │  ├── Code comment.txt
│  │  ├── Commit message.txt
│  │  ├── Issue section.txt
│  │  └── Pull section.txt
│  ├── Keywords based on Types of SATD
│  │  ├── code-design debt.txt
│  │  ├── documentation debt.txt
│  │  ├── requirement debt.txt
│  │  └── test debt.txt
│  └── .DS_Store
├── src
│  ├── bert
│  │  ├── config.py
│  │  ├── main.py
│  │  ├── model_builder.py
│  │  ├── predict.py
│  │  ├── train_model.py
│  │  └── utils.py
│  ├── bilstm
│  │  ├── commit_augmented.csv
│  │  ├── data_preparation.py
│  │  ├── embedding_loader.py
│  │  ├── evaluate_model.py
│  │  ├── main.py
│  │  ├── model_builder.py
│  │  └── train_model.py
│  └── preprocessing.py
├── Supplementary Material.docx
├── data-augmentation-code_comments.csv
├── data-augmentation-commit-messages.csv
├── data-augmentation-issues.csv
└── data-augmentation-pull-requests.csv
```

## Project sources for each artifact are as follows:
```
+---------------------+---------------+----------------------------+----------------------------+
| Source code comment | Issue section | Pull section               | Commit message             |
+---------------------+---------------+----------------------------+----------------------------+
| ant                 | camel         | accumulo                   | accumulo                   |
| argouml             | chromium      | activemq                   | activemq                   |
| columba             | gerrit        | activemq-artemis           | activemq-artemis           |
| emf                 | hadoop        | airflow                    | airflow                    |
| hibernate           | hbase         | ambari                     | ambari                     |
| jedit               | impala        | apisix                     | apisix                     |
| jfreechart          | thrift        | apisix-dashboard           | apisix-dashboard           |
| jmeter              |               | arrow                      | arrow                      |
| jruby               |               | attic-apex-core            | attic-apex-core            |
| squirrel            |               | attic-apex-malhar          | attic-apex-malhar          |
|                     |               | attic-stratos              | attic-stratos              |
|                     |               | avro                       | avro                       |
|                     |               | beam                       | beam                       |
|                     |               | bigtop                     | bigtop                     |
|                     |               | bookkeeper                 | bookkeeper                 |
|                     |               | brooklyn-server            | brooklyn-server            |
|                     |               | calcite                    | calcite                    |
|                     |               | camel                      | camel                      |
|                     |               | camel-k                    | camel-k                    |
|                     |               | camel-quarkus              | camel-quarkus              |
|                     |               | camel-website              | camel-website              |
|                     |               | carbondata                 | carbondata                 |
|                     |               | cassandra                  | cassandra                  |
|                     |               | cloudstack                 | cloudstack                 |
|                     |               | commons-lang               | commons-lang               |
|                     |               | couchdb                    | couchdb                    |
|                     |               | cxf                        | cxf                        |
|                     |               | daffodil                   | daffodil                   |
|                     |               | drill                      | drill                      |
|                     |               | druid                      | druid                      |
|                     |               | dubbo                      | dubbo                      |
|                     |               | echarts                    | echarts                    |
|                     |               | fineract                   | fineract                   |
|                     |               | flink                      | flink                      |
|                     |               | fluo                       | fluo                       |
|                     |               | geode                      | geode                      |
|                     |               | geode-native               | geode-native               |
|                     |               | gobblin                    | gobblin                    |
|                     |               | griffin                    | griffin                    |
|                     |               | groovy                     | groovy                     |
|                     |               | guacamole-client           | guacamole-client           |
|                     |               | hadoop                     | hadoop                     |
|                     |               | hawq                       | hawq                       |
|                     |               | hbase                      | hbase                      |
|                     |               | helix                      | helix                      |
|                     |               | hive                       | hive                       |
|                     |               | hudi                       | hudi                       |
|                     |               | iceberg                    | iceberg                    |
|                     |               | ignite                     | ignite                     |
|                     |               | incubator-brooklyn         | incubator-brooklyn         |
|                     |               | incubator-dolphinscheduler | incubator-dolphinscheduler |
|                     |               | incubator-doris            | incubator-doris            |
|                     |               | incubator-heron            | incubator-heron            |
|                     |               | incubator-hop              | incubator-hop              |
|                     |               | incubator-mxnet            | incubator-mxnet            |
|                     |               | incubator-pagespeed-ngx    | incubator-pagespeed-ngx    |
|                     |               | incubator-pinot            | incubator-pinot            |
|                     |               | incubator-weex             | incubator-weex             |
|                     |               | infrastructure-puppet      | infrastructure-puppet      |
|                     |               | jena                       | jena                       |
|                     |               | jmeter                     | jmeter                     |
|                     |               | kafka                      | kafka                      |
|                     |               | karaf                      | karaf                      |
|                     |               | kylin                      | kylin                      |
|                     |               | lucene-solr                | lucene-solr                |
|                     |               | madlib                     | madlib                     |
|                     |               | myfaces-tobago             | myfaces-tobago             |
|                     |               | netbeans                   | netbeans                   |
|                     |               | netbeans-website           | netbeans-website           |
|                     |               | nifi                       | nifi                       |
|                     |               | nifi-minifi-cpp            | nifi-minifi-cpp            |
|                     |               | nutch                      | nutch                      |
|                     |               | openwhisk                  | openwhisk                  |
|                     |               | openwhisk-wskdeploy        | openwhisk-wskdeploy        |
|                     |               | orc                        | orc                        |
|                     |               | ozone                      | ozone                      |
|                     |               | parquet-mr                 | parquet-mr                 |
|                     |               | phoenix                    | phoenix                    |
|                     |               | pulsar                     | pulsar                     |
|                     |               | qpid-dispatch              | qpid-dispatch              |
|                     |               | reef                       | reef                       |
|                     |               | rocketmq                   | rocketmq                   |
|                     |               | samza                      | samza                      |
|                     |               | servicecomb-java-chassis   | servicecomb-java-chassis   |
|                     |               | shardingsphere             | shardingsphere             |
|                     |               | shardingsphere-elasticjob  | shardingsphere-elasticjob  |
|                     |               | skywalking                 | skywalking                 |
|                     |               | spark                      | spark                      |
|                     |               | storm                      | storm                      |
|                     |               | streams                    | streams                    |
|                     |               | superset                   | superset                   |
|                     |               | systemds                   | systemds                   |
|                     |               | tajo                       | tajo                       |
|                     |               | thrift                     | thrift                     |
|                     |               | tinkerpop                  | tinkerpop                  |
|                     |               | tomee                      | tomee                      |
|                     |               | trafficcontrol             | trafficcontrol             |
|                     |               | trafficserver              | trafficserver              |
|                     |               | trafodion                  | trafodion                  |
|                     |               | tvm                        | tvm                        |
|                     |               | usergrid                   | usergrid                   |
|                     |               | zeppelin                   | zeppelin                   |
|                     |               | zookeeper                  | zookeeper                  |
+---------------------+---------------+----------------------------+----------------------------+
```

## Requirements:
- GloVe
- nltk
- pandas
- numpy
- seaborn
- transformers
- torch
- tensorflow
- keras
- langdetect
- inflect
- inflection
 
This dataset has undergone a data augmentation process using the [AugGPT](https://arxiv.org/abs/2302.13007) technique. Meanwhile, the original dataset can be downloaded via the following link: [https://github.com/yikun-li/satd-different-sources-data](https://github.com/yikun-li/satd-different-sources-data)
