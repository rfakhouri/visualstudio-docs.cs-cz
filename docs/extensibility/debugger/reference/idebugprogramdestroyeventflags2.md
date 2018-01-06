---
title: IDebugProgramDestroyEventFlags2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugProgramDestroyEventFlags2 interface
ms.assetid: d384ff71-dc71-40b9-a871-801f8b6a3418
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3a3bb34435bc7c6411fe694e4476eb9ffeacfe1d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramdestroyeventflags2"></a>IDebugProgramDestroyEventFlags2
Umožňuje přepsat výchozí chování stroj ladění [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] uživatelského rozhraní při ukončení relace ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProgramDestroyEventFlags2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementováno modulem ladění moduly. Je užitečné pro hostitele, kteří mohou vytvořit a zrušení více programů během životního cyklu procesu.  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `IDebugProgramDestroyEventFlags2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Getflags –](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)|Načte program destroy příznaky.|  
  
## <a name="remarks"></a>Poznámky  
 Výchozí chování [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] uživatelského rozhraní je přejděte zpět do režimu návrhu po všechny programy odeslali program destroy událostí. Toto rozhraní umožňuje modul ladění, chcete-li toto chování změnit.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll