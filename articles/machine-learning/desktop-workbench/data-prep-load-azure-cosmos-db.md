---
title: 在 Azure 机器学习工作台中作为数据源连接到 Azure Cosmos DB | Microsoft Docs
description: 本文档提供示例，说明如何通过 Azure 机器学习工作台连接到 Azure Cosmos DB
services: machine-learning
author: cforbe
ms.author: cforbe
manager: mwinkle
ms.reviewer: jmartens, jasonwhowell, mldocs
ms.service: machine-learning
ms.component: core
ms.workload: data-services
ms.custom: ''
ms.devlang: ''
ms.topic: article
ms.date: 09/11/2017
ROBOTS: NOINDEX
ms.openlocfilehash: 9c4ea529e8ca6dbb9b7321dc24468fad93435705
ms.sourcegitcommit: 32d218f5bd74f1cd106f4248115985df631d0a8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "46948190"
---
# <a name="connecting-to-azure-cosmos-db-as-a-data-source"></a>作为数据源连接到 Azure Cosmos DB

[!INCLUDE [workbench-deprecated](../../../includes/aml-deprecating-preview-2017.md)] 


本文包含了 python 示例，允许在 Azure 机器学习工作台中连接到 Cosmos DB。

## <a name="load-azure-cosmos-db-data-into-data-preparation"></a>将 Azure Cosmos DB 数据加载到数据准备中

创建新的基于脚本的数据流，然后使用以下脚本从 Azure Cosmos DB 加载数据。 

```python
import pydocumentdb
import pydocumentdb.document_client as document_client

import pandas as pd

config = { 
    'ENDPOINT': '<Endpoint>',
    'MASTERKEY': '<Key>',
    'DOCUMENTDB_DATABASE': '<DBName>',
    'DOCUMENTDB_COLLECTION': '<collectionname>'
};

# Initialize the Python DocumentDB client.
client = document_client.DocumentClient(config['ENDPOINT'], {'masterKey': config['MASTERKEY']})

# Read databases and take first since id should not be duplicated.
db = next((data for data in client.ReadDatabases() if data['id'] == config['DOCUMENTDB_DATABASE']))

# Read collections and take first since id should not be duplicated.
coll = next((coll for coll in client.ReadCollections(db['_self']) if coll['id'] == config['DOCUMENTDB_COLLECTION']))

docs = client.ReadDocuments(coll['_self'])

df = pd.DataFrame(list(docs))
```

## <a name="other-data-source-connections"></a>其他数据源连接
有关其他示例，请参阅[其他源数据连接示例](data-prep-appendix8-sample-source-connections-python.md)
