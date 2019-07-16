---
title: ToggleHUD | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 87c2571926b92e59ae03e5e988bbf535474dc6d0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68144581"
---
# <a name="togglehud"></a>ToggleHUD
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Přepíná diagnostiky grafiky *HUD* překrytí (zobrazit vedoucí nahoru), nebo vypnout.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
void ToggleHUD();  
```  
  
## <a name="remarks"></a>Poznámky  
 HUD Diagnostika grafiky se zobrazí v levém horním rohu aplikace, na kterém běží v rámci diagnostiky grafiky. Zobrazí běhových informací o aplikaci a o zachycení informací grafiky a zprávy, které jsou přidány pomocí volání [AddMessage](../debugger/addmessage.md) členskou funkci.  
  
 Chcete-li přepnout HUD, nemusíte být aktivně zachycení informací grafiky – to znamená, ho můžou být prostřednictvím instance `VsgDbg` třídy, ale [Init](../debugger/init.md) nemusí být nejprve volat členské funkce.
