---
title: IDebugProgramDestroyEventFlags2 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugProgramDestroyEventFlags2 interface
ms.assetid: d384ff71-dc71-40b9-a871-801f8b6a3418
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9afc8a810468733661abb2a71e609e3cbe303d51
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49223610"
---
# <a name="idebugprogramdestroyeventflags2"></a>IDebugProgramDestroyEventFlags2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Umožňuje ladicí stroj přepsat výchozí chování [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] uživatelského rozhraní při ukončení relace ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProgramDestroyEventFlags2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementováno ladicí stroj. Je užitečné pro hostitele, kteří mohou vytvořit a zničit více programů během životního cyklu procesu.  
  
## <a name="methods"></a>Metody  
 V následující tabulce jsou uvedeny metody objektu `IDebugProgramDestroyEventFlags2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)|Načte program zničit příznaky.|  
  
## <a name="remarks"></a>Poznámky  
 Výchozí chování [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] uživatelského rozhraní je chcete přejít zpátky do režimu návrhu po všech programů odeslali program zrušení události. Toto rozhraní umožňuje ladicí stroj ke změně tohoto chování.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

