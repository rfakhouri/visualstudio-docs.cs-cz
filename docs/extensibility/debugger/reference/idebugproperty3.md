---
title: IDebugProperty3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProperty3
helpviewer_keywords: IDebugProperty3 interface
ms.assetid: 8f9be68d-4490-4eca-8f6b-8a10ed77e226
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 853d6f4f4f4b9bef54b35c1f2277e3112c1fe31d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugproperty3"></a>IDebugProperty3
Toto rozhraní poskytuje podporu pro:  
  
-   Načítání dlouhé řetězce spojeného s vlastností.  
  
-   Jedinečné ID přiřazení s vlastností.  
  
-   Načítání seznamu vlastní prohlížečů pro vlastnost.  
  
-   Nastavení hodnoty vlastnosti umožňuje nahlásit případné chyby  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProperty3 : IDebugProperty2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje modul ladění (DE) pro stejný objekt, který implementuje [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) kvůli zajištění podpory pro dlouhých řetězců, vlastnost ID a vlastní prohlížeče.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [QueryInterface](/cpp/atl/queryinterface) na `IDebugProperty2` rozhraní k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod zděděno z `IDebugProperty2`, `IDebugProperty3` rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)|Vrátí délku řetězce spojeného s vlastností.|  
|[GetStringChars](../../../extensibility/debugger/reference/idebugproperty3-getstringchars.md)|Vrátí řetězec do vyrovnávací paměti zadanou uživatelem.|  
|[CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)|Vytvoří jedinečné ID pro tuto vlastnost.|  
|[DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md)|Zničí jedinečné ID pro tuto vlastnost.|  
|[GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)|Vrátí počet vlastní prohlížečů, které tuto vlastnost lze zobrazit s.|  
|[GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)|Vrátí seznam vlastní prohlížečů, které tuto vlastnost lze zobrazit s.|  
|[SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)|Nastaví hodnotu této vlastnosti, vrátí chybovou zprávu, pokud se něco pokazilo.|  
  
## <a name="remarks"></a>Poznámky  
 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md) je upřednostňovaný způsob pro relaci ladění správce (SDM) k nastavení vlastnosti na hodnotu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)