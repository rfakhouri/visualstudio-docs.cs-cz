---
title: TYP ZPRÁVY | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- MESSAGETYPE
helpviewer_keywords:
- MESSAGETYPE enumeration
ms.assetid: 800cc77d-3c27-4763-a9df-552a9384bd49
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3fa09d938e0e7c3853431369c7e0634242df2ee0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="messagetype"></a>TYP ZPRÁVY
Určuje typ zprávy a důvod.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_MESSAGETYPE {   
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
public enum enum_MESSAGETYPE {   
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
 Označuje, že zpráva by měla být odesláno do okna výstupu. To se vzájemně vylučují z `MT_MESSAGEBOX`.  
  
 MT_MESSAGEBOX  
 Označuje, že zpráva mají být zobrazeny v okně se zprávou. To se vzájemně vylučují z `MT_OUTPUTSTRING`.  
  
 MT_TYPE_MASK  
 Hodnota masky izolovat cíl zprávy.  
  
 MT_REASON_EXCEPTION  
 Určuje, jestli se zprávou se zobrazují v důsledku výjimku. To se vzájemně vylučují z `MT_REASON_TRACEPOINT`.  
  
 MT_REASON_TRACEPOINT  
 Určuje, zda se v důsledku stiskne tracepoint zobrazen okno se zprávou. To se vzájemně vylučují k `MT_REASON_EXCEPTION`.  
  
 MT_REASON_MASK  
 Hodnota masky izolovat důvod se zobrazí zpráva.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou vráceny z [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md) a [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md) metody.  
  
 Jedna z hodnot Důvodem mohou být kombinovány s jednu z hodnot cílový výstup pomocí bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)   
 [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md)