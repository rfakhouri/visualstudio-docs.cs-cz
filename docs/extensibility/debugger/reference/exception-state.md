---
title: EXCEPTION_STATE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EXCEPTION_STATE
helpviewer_keywords:
- EXCEPTION_STATE enumeration
ms.assetid: 597f4f4c-9b70-485c-b5dc-3c2e3aecc664
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1faa847d907af938bb5f91206a5f438bcba886a3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="exceptionstate"></a>EXCEPTION_STATE
Určuje stav výjimky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_EXCEPTION_STATE {   
   EXCEPTION_NONE                          = 0x0000,  
   EXCEPTION_STOP_FIRST_CHANCE             = 0x0001,  
   EXCEPTION_STOP_SECOND_CHANCE            = 0x0002,  
   EXCEPTION_STOP_USER_FIRST_CHANCE        = 0x0010,  
   EXCEPTION_STOP_USER_UNCAUGHT            = 0x0020,  
   EXCEPTION_STOP_ALL                      = 0x00FF,  
   EXCEPTION_CANNOT_BE_CONTINUED           = 0x0100,  
  
   // These are for exception types only  
   EXCEPTION_CODE_SUPPORTED                = 0x1000,  
   EXCEPTION_CODE_DISPLAY_IN_HEX           = 0x2000,  
   EXCEPTION_JUST_MY_CODE_SUPPORTED        = 0x4000,  
   EXCEPTION_MANAGED_DEBUG_ASSISTANT       = 0x8000,  
  
   // These are no longer used  
   EXCEPTION_STOP_FIRST_CHANCE_USE_PARENT      = 0x0004,  
   EXCEPTION_STOP_SECOND_CHANCE_USE_PARENT     = 0x0008,  
   EXCEPTION_STOP_USER_FIRST_CHANCE_USE_PARENT = 0x0040,  
   EXCEPTION_STOP_USER_UNCAUGHT_USE_PARENT     = 0x0080,  
};  
typedef DWORD EXCEPTION_STATE;  
```  
  
```csharp  
public enum enum_EXCEPTION_STATE {   
   EXCEPTION_NONE                          = 0x0000,  
   EXCEPTION_STOP_FIRST_CHANCE             = 0x0001,  
   EXCEPTION_STOP_SECOND_CHANCE            = 0x0002,  
   EXCEPTION_STOP_USER_FIRST_CHANCE        = 0x0010,  
   EXCEPTION_STOP_USER_UNCAUGHT            = 0x0020,  
   EXCEPTION_STOP_ALL                      = 0x00FF,  
   EXCEPTION_CANNOT_BE_CONTINUED           = 0x0100,  
  
   // These are for exception types only  
   EXCEPTION_CODE_SUPPORTED                = 0x1000,  
   EXCEPTION_CODE_DISPLAY_IN_HEX           = 0x2000,  
   EXCEPTION_JUST_MY_CODE_SUPPORTED        = 0x4000,  
   EXCEPTION_MANAGED_DEBUG_ASSISTANT       = 0x8000,  
  
   // These are no longer used  
   EXCEPTION_STOP_FIRST_CHANCE_USE_PARENT      = 0x0004,  
   EXCEPTION_STOP_SECOND_CHANCE_USE_PARENT     = 0x0008,  
   EXCEPTION_STOP_USER_FIRST_CHANCE_USE_PARENT = 0x0040,  
   EXCEPTION_STOP_USER_UNCAUGHT_USE_PARENT     = 0x0080,  
};  
```  
  
## <a name="members"></a>Členové  
 EXCEPTION_NONE  
 Není zastavit výjimku.  
  
 EXCEPTION_STOP_FIRST_CHANCE  
 Zastavte první pálení výjimky. Při popisu události výjimky, tento příznak označuje, že událost výjimky je první odpovídající výjimce událostí.  
  
 EXCEPTION_STOP_SECOND_CHANCE  
 Zastavte druhý pálení výjimky. Při popisu události výjimky, označuje, že událost výjimky je sekundu odpovídající výjimce událostí.  
  
 EXCEPTION_STOP_USER_FIRST_CHANCE  
 Zastavte první pálení výjimka režimu uživatele. Při popisu události výjimky, označuje, že událost výjimky je událost uživatele první odpovídající výjimce.  
  
 EXCEPTION_STOP_USER_UNCAUGHT  
 Zastavte při není zachycena výjimka režimu uživatele. Při popisu události výjimky, označuje, že událost výjimky je událost výjimky režimu nezachycená uživatele.  
  
 EXCEPTION_STOP_ALL  
 Ukončete všechny výjimky. Nepoužívá se při popisu události výjimky.  
  
 EXCEPTION_CANNOT_BE_CONTINUED  
 Při popisu události výjimky, označuje, že výjimky nelze pokračovat z.  
  
 EXCEPTION_CODE_SUPPORTED  
 Označuje, že výjimka má kód je podpora. Použité při zobrazování výjimku  
  
 EXCEPTION_CODE_DISPLAY_IN_HEX  
 Označuje, že kód výjimky se mají zobrazit v šestnáctkové soustavě. Použité při zobrazování výjimku.  
  
 EXCEPTION_JUST_MY_CODE_SUPPORTED  
 Označuje, že kód výjimky podporuje JustMyCode. Použité při zobrazování výjimku.  
  
 EXCEPTION_MANAGED_DEBUG_ASSISTANT  
 Označuje, že ladicí program spravovaného kódu by měla zpracování výjimek. Pokud není sada, výchozí program pro ladění zpracovává výjimky. To je předán [SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md) metoda a nesmí se používat v [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) struktury.  
  
 EXCEPTION_STOP_FIRST_CHANCE_USE_PARENT  
 ZASTARALÉ, NEPOUŽÍVEJTE.  
  
 EXCEPTION_STOP_SECOND_CHANCE_USE_PARENT  
 ZASTARALÉ, NEPOUŽÍVEJTE.  
  
 EXCEPTION_STOP_USER_FIRST_CHANCE_USE_PARENT  
 ZASTARALÉ, NEPOUŽÍVEJTE.  
  
 EXCEPTION_STOP_USER_SECOND_CHANCE_USE_PARENT  
 ZASTARALÉ, NEPOUŽÍVEJTE.  
  
## <a name="remarks"></a>Poznámky  
 Použít jako `dwState` členem [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) struktura k označení stavu výjimku a co můžete udělat o něm.  
  
 Tyto hodnoty jsou také předávány [SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md) metodu a nastavit stav všechny výjimky.  
  
 Tyto příznaky může být kombinován s bitové operace OR.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)   
 [SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md)