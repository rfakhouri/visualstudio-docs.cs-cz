---
title: IDebugProperty3 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProperty3
helpviewer_keywords:
- IDebugProperty3 interface
ms.assetid: 8f9be68d-4490-4eca-8f6b-8a10ed77e226
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8ffb3ef65e10776230dc9896bf6dccbe4a813f9a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667439"
---
# <a name="idebugproperty3"></a>IDebugProperty3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProperty3](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproperty3).  
  
Toto rozhraní poskytuje podporu pro:  
  
-   Načítání libovolně dlouhý řetězec přidružený k vlastnosti.  
  
-   Jedinečné ID přiřazení s vlastností.  
  
-   Načítání seznamu vlastních prohlížečů pro vlastnost.  
  
-   Nastavení hodnoty vlastnosti umožňuje nahlásit případné chyby  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProperty3 : IDebugProperty2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní na stejný objekt, který implementuje [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) k poskytování podpory pro dlouhé řetězce, vlastnosti ID a vlastních prohlížečů.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) na `IDebugProperty2` rozhraní k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod zděděných z `IDebugProperty2`, `IDebugProperty3` rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)|Vrátí délku řetězce spojeného s vlastností.|  
|[GetStringChars](../../../extensibility/debugger/reference/idebugproperty3-getstringchars.md)|Vrátí řetězec do uživatelem zadané vyrovnávací paměti.|  
|[CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)|Vytvoří jedinečné ID pro tuto vlastnost.|  
|[DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md)|Zničí jedinečné ID pro tuto vlastnost.|  
|[GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)|Vrátí počet vlastních prohlížečů, které se dají zobrazit tuto vlastnost.|  
|[GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)|Vrátí seznam vlastních prohlížečů, které se dají zobrazit tuto vlastnost.|  
|[SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)|Nastaví hodnotu této vlastnosti, vrátí chybovou zprávu, pokud se něco pokazilo.|  
  
## <a name="remarks"></a>Poznámky  
 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md) je upřednostňovaný způsob pro správce ladění relace (SDM) k nastavení hodnoty vlastnosti.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)

