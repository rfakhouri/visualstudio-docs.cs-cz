---
title: Azure SDK pro Python
description: Sada Azure SDK pro Python usnadňuje používání služeb Microsoft Azure z aplikací Pythonu běží na libovolné platformě.
ms.date: 12/06/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: b14066272fa160cf2b4fc9f344185a3b68751926
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55031718"
---
# <a name="consume-azure-services-using-the-azure-sdk-for-python"></a>Využívání služeb Azure pomocí sady Azure SDK pro Python

Sada Azure SDK pro Python umožňuje snadno využívat a spravovat služby Micorosft Azure z aplikací běžících ve Windows, MacOS a Linux.

## <a name="installation"></a>Instalace

Při instalaci sady Azure SDK z [indexu balíčků Pythonu](https://pypi.python.org/pypi/azure).

Nainstalujte **nejnovější stabilní verzi** (podporuje Python 2.7 a 3.x) následujícím způsobem:

```command
pip install azure
```

Můžete také postupovat [instalace Pythonu a sady SDK](https://docs.microsoft.com/azure/python-how-to-install/) v dokumentaci k Azure.

## <a name="documentation"></a>Dokumentace

[Sady Azure SDK for středisko pro vývojáře Python](https://docs.microsoft.com/python/azure/?view=azure-python) má také některé užitečné zdroje informací, včetně počtu kurzy:

- [Vytváření webových aplikací ve službě Azuyre App Service v Linuxu](/azure/app-service/containers/quickstart-python).
- [Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-python)
- [Table Storage](/azure/cosmos-db/table-storage-how-to-use-python)
- [Queue Storage](/azure/storage/storage-python-how-to-use-queue-storage)
- [Azure Cosmos DB](/azure/cosmos-db/sql-api-python-application)
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
