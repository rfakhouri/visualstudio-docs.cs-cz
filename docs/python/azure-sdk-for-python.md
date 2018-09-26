---
title: Azure SDK pro Python
description: Sada Azure SDK pro Python usnadňuje používání služeb Microsoft Azure z aplikací Pythonu běží na libovolné platformě.
ms.date: 09/56/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: 0a68027e975357a404cd7b4f29c837767c60e015
ms.sourcegitcommit: 95aedf723c6be5272c3c5a2911cb2bdec50e2148
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/26/2018
ms.locfileid: "47228809"
---
# <a name="azure-sdk-for-python"></a>Azure SDK pro Python

Sada Azure SDK pro Python umožňuje snadno využívat a spravovat služby Micorosft Azure z aplikací běžících ve Windows, Mac OS x a Linux.

## <a name="installation"></a>Instalace

Při instalaci sady Azure SDK z [indexu balíčků Pythonu](https://pypi.python.org/pypi/azure).

Nainstalujte **nejnovější stabilní verzi** (podporuje Python 2.7 a 3.x) následujícím způsobem:

```command
pip install azure
```

Můžete také postupovat [instalace Pythonu a sady SDK](https://docs.microsoft.com/azure/python-how-to-install/) v dokumentaci k Azure.

## <a name="documentation"></a>Dokumentace

Úplnou dokumentaci se nachází na [Azure pro Centrum pro vývojáře Python](https://docs.microsoft.com/en-us/python/azure/?view=azure-python). Qucik prostředí, najdete v části [začít s vývojem pro cloud pomocí Pythonu](/python/azure/python-sdk-azure-get-started?view=azure-python).

Také najdete v těchto kurzech pro ostatní služby Azure pomocí Pythonu:

- Azure App Service:
  - [Vytvoření webové aplikace](/azure/app-service/containers/quickstart-python)
  - [Vytvoření webové aplikace Docker Python využívající databázi PostgreSQL v Azure](/azure/app-service/containers/tutorial-docker-python-postgresql-app)
- Azure Storage:
  - [Úložiště objektů BLOB](/azure/storage/blobs/storage-quickstart-blobs-python)
  - [Table storage a Cosmos DB](/azure/cosmos-db/table-storage-how-to-use-python)
  - [Fronta úložiště](/azure/storage/queues/storage-python-how-to-use-queue-storage)
  - [Flask a Cosmos DB](/azure/cosmos-db/sql-api-python-application)
- Service Bus
  - [Fronty služby Service Bus](/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
  - [Témata a odběry Service Bus](/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
- [Správa služeb](/azure/cloud-services/cloud-services-python-how-to-use-service-management)

Pro veřejné rozhraní API bez dokumentaci, testování částí [úložiště SDK GitHub](https://github.com/Azure/azure-sdk-for-python) jsou dobré zdroje informací:

- [Testy jednotky úložiště](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Testy jednotek služby Service Bus](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [Testy jednotek pro správu služby](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)

## <a name="support"></a>Podpora

Úložiště GitHub pro sadu SDK se nachází na [ https://github.com/Azure/azure-sdk-for-python ](https://github.com/Azure/azure-sdk-for-python).

[Soubor problémy v úložišti](https://github.com/Azure/azure-sdk-for-python/issues) najít jakékoli problémy nebo máte otázky týkající se použití sady SDK.
