---
title: Imachinedebugmanagercookie – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IMachineDebugManagerCookie interface
ms.assetid: 04770935-3ccf-41e9-b0c1-c78376ab1e3c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fdc02498360f2e3900012166474c5d1e35abd6ee
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977679"
---
# <a name="imachinedebugmanagercookie-interface"></a>IMachineDebugManagerCookie – rozhraní
Podobně jako `IMachineDebugManager` rozhraní, `IMachineDebugManagerCookie` rozhraní podporuje ladění.  
  
 Toto rozhraní (spolu s `IDebugCookie` rozhraní) povolení spouštět skripty v procesu ladicího programu skript bez nutnosti, že tyto skripty udržovat přehled o ladicím programu.  
  
 Ladicí program volá `IDebugCookie::SetDebugCookie` metoda na proces ladění správce (PDM). PDM odešle tento soubor cookie spolu s všechny žádosti o přidání nebo odebrání aplikace skriptu do nebo z počítače ladění Manager (MDM), pomocí metody `IMachineDebugManagerCookie` rozhraní. MDM poté oznámí každý ladicí program změny, s výjimkou ten, který má tento soubor cookie.  
  
 Kromě metod zděděných z `IUnknown`, `IMachineDebugManagerCookie` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IMachineDebugManagerCookie::AddApplication](../../winscript/reference/imachinedebugmanagercookie-addapplication.md)|Přidá aplikaci do běhu seznamu aplikací.|  
|[IMachineDebugManagerCookie::EnumApplications](../../winscript/reference/imachinedebugmanagercookie-enumapplications.md)|Vrátí enumerátor aktuální seznam spuštěných aplikací.|  
|[IMachineDebugManagerCookie::RemoveApplication](../../winscript/reference/imachinedebugmanagercookie-removeapplication.md)|Odebere aplikaci ze spuštění seznam aplikací.|  
  
## <a name="see-also"></a>Viz také  
 [IMachineDebugManager Interface](../../winscript/reference/imachinedebugmanager-interface.md)   
 [IDebugCookie – rozhraní](../../winscript/reference/idebugcookie-interface.md)