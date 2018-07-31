---
title: Azure SDK pro Python
description: Sada Azure SDK pro Python usnadňuje používání služeb Microsoft Azure z aplikací Pythonu běží na libovolné platformě.
ms.date: 06/26/2018
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
ms.openlocfilehash: 4dd7e5841db4c05de5607f9aefe7b9a3a36fee19
ms.sourcegitcommit: 4f82c178b1ac585dcf13b515cc2a9cb547d5f949
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341235"
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

Dokumentace ke službě můžete najít na [azure sdk pro python.readthedocs.org](https://docs.microsoft.com/en-us/python/azure/?view=azure-python).

[Sady Azure SDK for středisko pro vývojáře Python](http://azure.microsoft.com/develop/python/) má také některé užitečné zdroje informací, včetně počtu kurzy:

- Vytváření webových aplikací s [Django](/azure/app-service-web/web-sites-python-create-deploy-django-app), [Flask](/azure/app-service-web/web-sites-python-create-deploy-flask-app), a [Bottle](/azure/app-service-web/web-sites-python-create-deploy-bottle-app).
- [Úložiště objektů BLOB](/azure/storage/storage-python-how-to-use-blob-storage)
- [Úložiště tabulek](/azure/storage/storage-python-how-to-use-table-storage)
- [Fronta úložiště](/azure/storage/storage-python-how-to-use-queue-storage)
- [Azure Cosmos DB](/azure/cosmos-db/sql-api-python-application)
- [Fronty služby Service Bus](/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
- [Témata a odběry Service Bus](/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
- [Správa služeb](/azure/cloud-services/cloud-services-python-how-to-use-service-management)

Pro veřejné rozhraní API bez dokumentaci, testování částí [úložiště SDK GitHub](https://github.com/Azure/azure-sdk-for-python) jsou dobré zdroje informací:

- [Testy jednotky úložiště](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Testy jednotek služby Service Bus](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [Testy jednotek pro správu služby](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)

## <a name="support"></a>Podpora

Úložiště Git pro sadu SDK se nachází na [ https://github.com/Azure/azure-sdk-for-python ](https://github.com/Azure/azure-sdk-for-python).

[Soubor problémy v úložišti](https://github.com/Azure/azure-sdk-for-python/issues) najít jakékoli problémy nebo máte otázky týkající se použití sady SDK.
