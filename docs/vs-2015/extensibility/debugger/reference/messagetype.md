---
title: TYP ZPRÁVY | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- MESSAGETYPE
helpviewer_keywords:
- MESSAGETYPE enumeration
ms.assetid: 800cc77d-3c27-4763-a9df-552a9384bd49
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c17564c992f4c8855d8a96165975a5d0e132755c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62547205"
---
# <a name="messagetype"></a>MESSAGETYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Určuje typ zprávy a důvod.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_MESSAGETYPE {   
   MT_OUTPUTSTRING      = 0x0000001,  
   MT_MESSAGEBOX        = 0x00000002,  
   MT_TYPE_MASK         = 0x000000FF,  
   MT_REASON_EXCEPTION  = 0x00000100,  
   MT_REASON_TRACEPOINT = 0x00000200,  
   MT_REASON_MASK       = 0x0000FF00  
};  
typedef DWORD MESSAGETYPE;  
```  
  
```csharp  
public enum enum_MESSAGETYPE {   
   MT_OUTPUTSTRING      = 0x0000001,  
   MT_MESSAGEBOX        = 0x00000002,  
   MT_TYPE_MASK         = 0x000000FF,  
   MT_REASON_EXCEPTION  = 0x00000100,  
   MT_REASON_TRACEPOINT = 0x00000200,  
   MT_REASON_MASK       = 0x0000FF00  
};  
```  
  
## <a name="members"></a>Členové  
 MT_OUTPUTSTRING  
 Označuje, že zprávy by měl být odesláno do okna výstup. To se vzájemně vylučuje z `MT_MESSAGEBOX`.  
  
 MT_MESSAGEBOX  
 Určuje, že zprávy by měl zobrazeny v okně se zprávou. To se vzájemně vylučuje z `MT_OUTPUTSTRING`.  
  
 MT_TYPE_MASK  
 Hodnota masky izolovat cíl zprávy.  
  
 MT_REASON_EXCEPTION  
 Označuje, že se zobrazuje okno se zprávou v důsledku výjimky. To se vzájemně vylučuje z `MT_REASON_TRACEPOINT`.  
  
 MT_REASON_TRACEPOINT  
 Označuje, že se v důsledku dosažení zarážku s trasováním zobrazuje okno se zprávou. Toto je vzájemně se vylučující k `MT_REASON_EXCEPTION`.  
  
 MT_REASON_MASK  
 Hodnota masky izolovat důvod se zobrazí zpráva.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou vráceny z [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md) a [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md) metody.  
  
 Jedna z hodnot z důvodu je možné kombinovat s některou z hodnot cíl výstupu pomocí logické bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)   
 [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md)
