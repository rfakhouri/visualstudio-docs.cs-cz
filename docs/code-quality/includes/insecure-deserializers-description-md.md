---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 054198eff46c0983a5610b29dee5e29e5ac67a70
ms.sourcegitcommit: 748d9cd7328a30f8c80ce42198a94a4b5e869f26
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "68147099"
---
Nezabezpečené deserializers jsou zranitelné při deserializaci nedůvěryhodná data. Útočník může změnit serializovaná data, aby mohly zahrnout typy neočekávané vkládat objekty se zlými úmysly vedlejší účinky. Útok na nezabezpečené deserializátor může, například spuštění příkazů na příslušný operační systém, komunikují přes síť a odstraňovat soubory.