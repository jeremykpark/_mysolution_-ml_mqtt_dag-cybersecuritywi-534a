[_mysolution_-ml_mqtt_dag-cybersecuritywi-534a] Details
============================

Generated On: 2025-03-14 17:56:35 UTC

TML Solution DAG Parameters' Details: User Chosen Parametets
----------------------------

STEP 1: Get TML Core Params: `tml_system_step_1_getparams_dag <https://github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/tml_system_step_1_getparams_dag-_mysolution_.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - solutionname
     - _mysolution_-ml_mqtt_dag-cybersecuritywi-534a
   * - solutiontitle
     - My Solution Title
   * - solutiondescription
     - This is an awesome real-time solution built by TSS
   * - brokerhost
     - 127.0.0.1
   * - brokerport
     - 9092
   * - cloudusername
     - None
   * - ingestdatamethod
     - MQTT
 
STEP 2: Create Kafka Topics: `tml_system_step_2_kafka_createtopic_dag <https://github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/tml_system_step_2_kafka_createtopic_dag-_mysolution_.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - companyname
     - Otics
   * - myname
     - Sebastian
   * - myemail
     - Sebastian.Maurice
   * - mylocation
     - Toronto
   * - replication
     - 1
   * - numpartitions
     - 1
   * - enabletls
     - 1
   * - microserviceid
     - 
   * - raw_data_topic
     - cisco-network-mainstream
   * - preprocess_data_topic
     - cisco-network-preprocess
   * - ml_data_topic
     - ml-data
   * - prediction_data_topic
     - prediction-data

STEP 3: `Produce to Kafka Topics <https://github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/tml_read_MQTT_step_3_kafka_producetotopic_dag-_mysolution_.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - PRODUCETYPE
     - MQTT
   * - TOPIC
     - cisco-network-mainstream
   * - PORT
     - _9010
   * - IDENTIFIER
     - MQTT Subscription Topic: tml/cybersecurity
   * - HTTPADDR
     - https://
   * - FROMHOST
     - IXRDevDesktop,127.0.1.1
   * - TOHOST
     - 0.0.0.0
   * - CLIENTPORT
     - Not Applicable
   * - TSS_CLIENTPORT
     - Not Applicable
   * - TML_CLIENTPORT
     - Not Applicable
   * - docfolder
     - --docfolderprocess--
   * - doctopic
     - --doctopic--
   * - chunks
     - --chunks--
   * - docingestinterval
     - --docingestinterval--

STEP 4: Preprocesing Data: `tml-system-step-4-kafka-preprocess-dag <https://github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/tml_system_step_4_kafka_preprocess_dag-_mysolution_.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - cisco-network-mainstream
   * - preprocess_data_topic
     - cisco-network-preprocess
   * - preprocessconditions
     - 
   * - delay
     - 70
   * - maxrows
     - 800
   * - array
     - 0
   * - saveasarray
     - 1
   * - topicid
     - -999
   * - rawdataoutput
     - 1
   * - asynctimeout
     - 120
   * - timedelay
     - 0
   * - preprocesstypes
     - anomprob,trend,avg
   * - pathtotmlattrs
     - --pathtotmlattrs--
   * - identifier
     - IoT device performance and failures
   * - jsoncriteria
     - uid=metadata.dsn,filter:allrecords~subtopics=metadata.property_name~values=datapoint.value~identifiers=metadata.display_name~datetime=datapoint.updated_at~msgid=datapoint.id~latlong=lat:long

STEP 4b: Preprocesing Data: `tml-system-step-4b-kafka-preprocess-dag <https://github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/tml_system_step_4b_kafka_preprocess_dag-_mysolution_.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - --raw_data_topic2--
   * - preprocess_data_topic
     - --preprocess_data_topic2--
   * - preprocessconditions
     - --preprocessconditions2--
   * - delay
     - --delay2--
   * - maxrows
     - --maxrows2--
   * - array
     - --array2--
   * - saveasarray
     - --saveasarray2--
   * - topicid
     - --topicid2--
   * - rawdataoutput
     - --rawdataoutput2--
   * - asynctimeout
     - --asynctimeout2--
   * - timedelay
     - --timedelay2--
   * - preprocesstypes
     - --preprocesstypes2--
   * - pathtotmlattrs
     - --pathtotmlattrs2--
   * - identifier
     - --identifier2--
   * - jsoncriteria
     - --jsoncriteria2--

STEP 4c: Preprocesing Data: `tml-system-step-4c-kafka-preprocess-dag  <https://github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/tml_system_step_4c_kafka_preprocess_dag-_mysolution_.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - --raw_data_topic3--
   * - preprocess_data_topic
     - --preprocess_data_topic3--
   * - delay
     - --delay3--
   * - maxrows
     - --maxrows3--
   * - array
     - --array3--
   * - saveasarray
     - --saveasarray3--
   * - topicid
     - --topicid3--
   * - rawdataoutput
     - --rawdataoutput3--
   * - asynctimeout
     - --asynctimeout3--
   * - timedelay
     - --timedelay3--
   * - searchterms
     - --rtmssearchterms--
   * - rtmsstream
     - --rtmsstream--
   * - identifier
     - --identifier3--
   * - rememberpastwindows
     - --rememberpastwindows--
   * - patternwindowthreshold
     - --patternwindowthreshold--
   * - localsearchtermfolder
     - --localsearchtermfolder--
   * - localsearchtermfolderinterval
     - --localsearchtermfolderinterval--
   * - rtmsscorethreshold
     - --rtmsscorethreshold--
   * - rtmsscorethresholdtopic
     - --rtmsscorethresholdtopic--
   * - attackscorethreshold
     - --attackscorethreshold--
   * - attackscorethresholdtopic
     - --attackscorethresholdtopic--
   * - patternscorethreshold
     - --patternscorethreshold--
   * - patternscorethresholdtopic
     - --patternscorethresholdtopic--
   * - RTMS Output Github Link
     - `Output Data URL <--rtmsoutputurl-->`_

STEP 5: Entity Based Machine Learning : `tml-system-step-5-kafka-machine-learning-dag <https://github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/tml_system_step_5_kafka_machine_learning_dag-_mysolution_.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - preprocess_data_topic
     - cisco-network-preprocess
   * - ml_data_topic
     - ml-data
   * - modelruns
     - 100
   * - offset
     - -1
   * - islogistic
     - 0
   * - networktimeout
     - 600
   * - modelsearchtuner
     - 90
   * - processlogic
     - 
   * - dependentvariable
     - 
   * - independentvariables
     - 
   * - rollbackoffsets
     - 300
   * - topicid
     - -999
   * - consumefrom
     - 
   * - fullpathtotrainingdata
     - /Viper-ml/viperlogs/<choose foldername>
   * - transformtype
     - 
   * - sendcoefto
     - 
   * - coeftoprocess
     - 
   * - coefsubtopicnames
     - 
   * - ML Output Github Link
     - `Output Data URL <https:\/\/github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/mldata/<choose foldername>>`_

STEP 6: Entity Based Predictions: `tml-system-step-6-kafka-predictions-dag <https://github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/tml_system_step_6_kafka_predictions_dag-_mysolution_.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - preprocess_data_topic
     - cisco-network-preprocess
   * - ml_prediction_topic
     - iot-ml-prediction-results-output
   * - streamstojoin
     - Voltage_preprocessed_AnomProb,Current_preprocessed_AnomProb
   * - inputdata
     - 
   * - consumefrom
     - 
   * - offset
     - -1
   * - delay
     - 70
   * - usedeploy
     - 1
   * - networktimeout
     - 600
   * - maxrows
     - 800
   * - topicid
     - -999
   * - pathtoalgos
     - 

STEP 7: Real-Time Visualization: `tml-system-step-7-kafka-visualization-dag <https://github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/tml_system_step_7_kafka_visualization_dag-_mysolution_.py>`_
^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - vipervizport
     - 9005
   * - topic
     - 
   * - dashboardhtml
     - 
   * - secure
     - 1
   * - offset
     - -1
   * - append
     - 0
   * - chip
     - amd64
   * - rollbackoffset
     - 400

STEP 8: `tml_system_step_8_deploy_solution_to_docker_dag <https://github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/tml_system_step_8_deploy_solution_to_docker_dag-_mysolution_.py>`_
^^^^^^^^^^^^^^^^^^^^^
.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - Docker Container
     - jeremykpark/_mysolution_-ml_mqtt_dag-cybersecuritywi-534a-amd64 (https://hub.docker.com/r/jeremykpark/_mysolution_-ml_mqtt_dag-cybersecuritywi-534a-amd64)
   * - Docker Run Command
     - docker run -d -p 5050:5050 -p 4040:4040 -p 6060:6060 \
          --env TSS=0 \
          --env SOLUTIONNAME=_mysolution_-ml_mqtt_dag-cybersecuritywi-534a \
          --env SOLUTIONDAG=solution_preprocessing_ml_mqtt_dag-cybersecuritywithprivategpt-534a \
          --env GITUSERNAME=jeremykpark  \
          --env GITREPOURL=https://github.com/jeremykpark/tml-raspberrypi.git \
          --env SOLUTIONEXTERNALPORT=5050 \
          -v /var/run/docker.sock:/var/run/docker.sock:z \
          -v /your_localmachine/foldername:/rawdata:z \
          --env CHIP=amd64 \
          --env SOLUTIONAIRFLOWPORT=4040 \
          --env SOLUTIONVIPERVIZPORT=6060 \
          --env DOCKERUSERNAME='jeremykpark' \
          --env EXTERNALPORT=9010 \
          --env KAFKACLOUDUSERNAME='KV4GV4NF2H33GAPT' \
          --env VIPERVIZPORT=9005 \
          --env MQTTUSERNAME='tsstestcluser234' \
          --env AIRFLOWPORT=9000 \
          --env MQTTPASSWORD='<Enter mqtt password>' \
          --env KAFKACLOUDPASSWORD='<Enter API secret>' \
          --env GITPASSWORD='<Enter Github Password>' \
          --env READTHEDOCS='<Enter Readthedocs token>' \
          jeremykpark/_mysolution_-ml_mqtt_dag-cybersecuritywi-534a-amd64

STEP 9: `tml_system_step_9_privategpt_qdrant_dag <https://github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/tml_system_step_9_privategpt_qdrant_dag-_mysolution_.py>`_
^^^^^^^^^^^^^^^^^^^^^
.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - PrivateGPT Container
     - --pgptcontainername--
   * - PrivateGPT Run Command
     - --privategptrun--
   * - Qdrant Container
     - --qdrantcontainer--
   * - Qdrant Run Command
     - --qdrantrun--
   * - Consumefrom
     - 
   * - pgpt_data_topic
     - --pgpt_data_topic--
   * - offset
     - -1
   * - rollbackoffset
     - 400
   * - topicid
     - -999
   * - enabletls
     - 1
   * - partition
     - --partition--
   * - prompt
     - --prompt--
   * - context
     - --context--
   * - jsonkeytogather
     - --jsonkeytogather--
   * - keyattribute
     - --keyattribute--
   * - keyprocesstype
     - --keyprocesstype--
   * - vectordbcollectionname
     - --vectordbcollectionname--
   * - concurrency
     - --concurrency--
   * - CUDA_VISIBLE_DEVICES
     - --cuda--
   * - pgpthost
     - --pgpthost--
   * - pgptport
     - --pgptport--
   * - hyperbatch
     - --hyperbatch--
   * - docfolder
     - --docfolder--
   * - docfolderingestinterval
     - --docfolderingestinterval--
   * - useidentifierinprompt
     - --useidentifierinprompt--
   * - searchterms
     - --searchterms--
   * - streamall
     - --streamall--
   * - temperature
     - --temperature--
   * - vectorsearchtype
     - --vectorsearchtype--
   * - llm
     - --llmmodel--
   * - embedding
     - --embedding--
   * - vectorsize
     - --vectorsize--

STEP 10: `tml_system_step_10_documentation_dag <https://github.com/jeremykpark/tml-raspberrypi/tree/main/tml-airflow/dags/tml-solutions/_mysolution_/tml_system_step_10_documentation_dag-_mysolution_.py>`_
^^^^^^^^^^^^^^^^^^^^^
.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - Solution Documentation URL
     - https://_mysolution_-ml_mqtt_dag-cybersecuritywi-534a.readthedocs.io
