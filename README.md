The BigData Indexer is an application designed to efficiently index and manage large volumes of structured and unstructured data. It offers scalable indexing capabilities, advanced search functionality, and seamless integration with various data sources.

## Features:

1. Scalable Indexing: The BigData Indexer efficiently indexes large volumes of data, enabling fast and reliable search operations.
2. Advanced Search: With advanced search capabilities, users can quickly retrieve relevant information from the indexed data, even in massive datasets.
3. Integration with Big Data Technologies: The application seamlessly integrates with popular big data technologies such as Hadoop, Apache Spark, and Apache Kafka, enabling efficient data processing and indexing at scale.
4. Real-time Data Indexing: The BigData Indexer supports real-time indexing of streaming data sources, ensuring up-to-date search results.
5. Customizable Data Sources: Users can easily configure the application to index data from various sources, including databases, file systems, and streaming platforms.
   
## Getting Started:
To get started with the BigData Indexer, follow these steps:

1. Install the application on your server or local machine.
2. Configure the indexing settings, including data source Redis for key value store, Elasticsearch for indexing, Kibana for visualization, Rabbit MQ for messaging, Google IDP for authentication.
3. Start the indexing process to populate the initial index with data.
4. Use the search interface to query the indexed data and retrieve relevant information.

Usage:
The BigData Indexer provides a user-friendly interface for managing indexing tasks and querying indexed data. Here are some sample usage scenarios:

Indexing Data: Use the application's indexing interface to configure data sources and start the indexing process.
Searching Data: Use the search interface to enter search queries and retrieve relevant information from the indexed data.
Security: It ensures data security and access control through user authentication and authorization mechanisms. Access to indexed data and administrative functions is restricted to authorized users only.

APIs:
POST http://localhost:8080/v1/plan/

{
    "objectId": "planCostShares_1234",
    "objectType": "planCostShares",
    "planCostShares": {
        "deductible": 10,
        "_org": "org",
        "copay": 5,
        "objectId": "123",
        "objectType": "planCostShares"
    },
    "linkedplanServices": [
        {
            "linkedService": {
                "_org": "MCG",
                "objectId": "123_1234",
                "objectType": "linkedService",
                "name": "MCG_Basic"
            },
            "planserviceCostShares": {
                "deductible": 10,
                "_org": "org",
                "copay": 5,
                "objectId": "123_2",
                "objectType": "planServiceCostShares"
            },
            "_org": "MCG",
            "objectId": "123_4",
            "objectType": "linkedplanService"
        },
        {
            "linkedService": {
                "name": "well",
                "_org": "example.com",
                "objectId": "1234520xvc30sfs-505",
                "objectType": "service"
            },
            "planserviceCostShares": {
                "deductible": 10,
                "_org": "example.com",
                "copay": 175,
                "objectId": "1234512xvc1314sdfsd-506",
                "objectType": "membercostshare"
            },
            "_org": "example.com",
            "objectId": "27283xvx9sdf-507",
            "objectType": "planservice"
        }
    ],
    "_org": "Blue Cross Blue Shield",
    "planType": "Insurance",
    "creationDate": "2020-07-30T14:00:00.000-04"
}

PATCH http://localhost:8080/v1/plan/{id}
{
    "objectId": "planCostShares_1234",
    "objectType": "planCostShares",
    "planCostShares": {
        "deductible": 10,
        "_org": "org",
        "copay": 5,
        "objectId": "123",
        "objectType": "planCostShares"
    },
    "linkedplanServices": [
        {
            "linkedService": {
                "_org": "MCG",
                "objectId": "123_1234",
                "objectType": "linkedService",
                "name": "MCG_Basic"
            },
            "planserviceCostShares": {
                "deductible": 10,
                "_org": "org",
                "copay": 5,
                "objectId": "123_2",
                "objectType": "planServiceCostShares"
            },
            "_org": "MCG",
            "objectId": "123_4",
            "objectType": "linkedplanService"
        },
         {
            "linkedService": {
                "_org": "MCG",
                "objectId": "123_1234aaaa",
                "objectType": "linkedService",
                "name": "MCG_Premium"
            },
            "planserviceCostShares": {
                "deductible": 10,
                "_org": "org",
                "copay": 5,
                "objectId": "123_2aaaa",
                "objectType": "planServiceCostShares"
            },
            "_org": "MCG",
            "objectId": "123_4aaaa",
            "objectType": "linkedplanService"
        },
        {
            "linkedService": {
                "name": "well",
                "_org": "example.com",
                "objectId": "1234520xvc30sfs-505",
                "objectType": "service"
            },
            "planserviceCostShares": {
                "deductible": 10,
                "_org": "example.com",
                "copay": 175,
                "objectId": "1234512xvc1314sdfsd-506",
                "objectType": "membercostshare"
            },
            "_org": "example.com",
            "objectId": "27283xvx9sdf-507",
            "objectType": "planservice"
        }
    ],
    "_org": "Blue Cross Blue Shield",
    "planType": "Insurance",
    "creationDate": "2020-07-30T14:00:00.000-04"
}

DELETE http://localhost:8080/v1/plan/{id}
