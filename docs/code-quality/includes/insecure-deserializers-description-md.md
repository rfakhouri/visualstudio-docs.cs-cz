---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 43327901b2233b9b2818296f9269975d8524438b
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60118149"
---
Nezabezpečené deserializers jsou zranitelné při deserializaci nedůvěryhodná data. Útočník může změnit serializovaná data na neočekávané typy se zlými úmysly vedlejší účinky. Útok na nezabezpečené deserializátor může, například spuštění příkazů na příslušný operační systém, komunikují přes síť a odstraňovat soubory.