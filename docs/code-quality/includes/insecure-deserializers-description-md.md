---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 054198eff46c0983a5610b29dee5e29e5ac67a70
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65461824"
---
Nezabezpečené deserializers jsou zranitelné při deserializaci nedůvěryhodná data. Útočník může změnit serializovaná data, aby mohly zahrnout typy neočekávané vkládat objekty se zlými úmysly vedlejší účinky. Útok na nezabezpečené deserializátor může, například spuštění příkazů na příslušný operační systém, komunikují přes síť a odstraňovat soubory.