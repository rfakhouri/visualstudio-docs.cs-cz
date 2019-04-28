---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 43327901b2233b9b2818296f9269975d8524438b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541549"
---
Nezabezpečené deserializers jsou zranitelné při deserializaci nedůvěryhodná data. Útočník může změnit serializovaná data na neočekávané typy se zlými úmysly vedlejší účinky. Útok na nezabezpečené deserializátor může, například spuštění příkazů na příslušný operační systém, komunikují přes síť a odstraňovat soubory.