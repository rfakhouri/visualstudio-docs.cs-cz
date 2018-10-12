---
title: AddMessage | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b60f8bac24b01e39327357b89e9e96c04765077
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49248999"
---
# <a name="addmessage"></a>AddMessage
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Přidá vlastní zprávu pro diagnostiku grafiky *HUD* (zobrazení vedoucí nahoru).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
void AddMessage(  
  wchar_t const * szMessage  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `szMessage`  
 Zpráva, která mají být přidány do HUD.  
  
## <a name="remarks"></a>Poznámky  
 HUD Diagnostika grafiky se zobrazí v levém horním rohu aplikace, na kterém běží v rámci diagnostiky grafiky. Zobrazuje běhové informace o aplikaci a o zachycení informací grafiky a zprávy, které jsou přidány pomocí volání této funkce.  
  
 K přidání zprávy do HUD, nemusíte být aktivně zachycení informací grafiky – to znamená, je možné přidat zprávu prostřednictvím instance `VsgDbg` třídy, ale [Init](../debugger/init.md) členská funkce nevytváří nejprve volat. Zprávy se zobrazují jenom v HUD, se zaznamenávají do souboru protokolu grafiky.



