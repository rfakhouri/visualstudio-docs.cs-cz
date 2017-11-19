---
title: FRAMEINFO_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FRAMEINFO_FLAGS
helpviewer_keywords: FRAMEINFO_FLAGS enumeration
ms.assetid: 41578062-8455-412a-9d8b-1e1e9dc8d52e
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e05d7471df151642f6495907694a0057ef39dfd4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="frameinfoflags"></a>FRAMEINFO_FLAGS
Určuje informace načíst o objekt rámce zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_FRAMEINFO_FLAGS {  
   FIF_FUNCNAME              = 0x00000001,  
   FIF_RETURNTYPE            = 0x00000002,  
   FIF_ARGS                  = 0x00000004,  
   FIF_LANGUAGE              = 0x00000008,  
   FIF_MODULE                = 0x00000010,  
   FIF_STACKRANGE            = 0x00000020,  
   FIF_FRAME                 = 0x00000040,  
   FIF_DEBUGINFO             = 0x00000080,  
   FIF_STALECODE             = 0x00000100,  
   FIF_ANNOTATEDFRAME        = 0x00000200,  
   FIF_DEBUG_MODULEP         = 0x00000400,  
   FIF_FUNCNAME_FORMAT       = 0x00001000,  
   FIF_FUNCNAME_RETURNTYPE   = 0x00002000,  
   FIF_FUNCNAME_ARGS         = 0x00004000,  
   FIF_FUNCNAME_LANGUAGE     = 0x00008000,  
   FIF_FUNCNAME_MODULE       = 0x00010000,  
   FIF_FUNCNAME_LINES        = 0x00020000,  
   FIF_FUNCNAME_OFFSET       = 0x00040000,  
   FIF_FUNCNAME_ARGS_TYPES   = 0x00100000,  
   FIF_FUNCNAME_ARGS_NAMES   = 0x00200000,  
   FIF_FUNCNAME_ARGS_VALUES  = 0x00400000,  
   FIF_FUNCNAME_ARGS_ALL     = 0x00700000,  
   FIF_ARGS_TYPES            = 0x01000000,  
   FIF_ARGS_NAMES            = 0x02000000,  
   FIF_ARGS_VALUES           = 0x04000000,  
   FIF_ARGS_ALL              = 0x07000000,  
   FIF_ARGS_NOFORMAT         = 0x08000000,  
   FIF_ARGS_NO_FUNC_EVAL     = 0x10000000,  
   FIF_FILTER_NON_USER_CODE  = 0x20000000,  
   FIF_ARGS_NO_TOSTRING      = 0x40000000,  
   FIF_DESIGN_TIME_EXPR_EVAL = 0x80000000  
};  
typedef DWORD FRAMEINFO_FLAGS;  
```  
  
```csharp  
public enum enum_FRAMEINFO_FLAGS {  
   FIF_FUNCNAME              = 0x00000001,  
   FIF_RETURNTYPE            = 0x00000002,  
   FIF_ARGS                  = 0x00000004,  
   FIF_LANGUAGE              = 0x00000008,  
   FIF_MODULE                = 0x00000010,  
   FIF_STACKRANGE            = 0x00000020,  
   FIF_FRAME                 = 0x00000040,  
   FIF_DEBUGINFO             = 0x00000080,  
   FIF_STALECODE             = 0x00000100,  
   FIF_ANNOTATEDFRAME        = 0x00000200,  
   FIF_DEBUG_MODULEP         = 0x00000400,  
   FIF_FUNCNAME_FORMAT       = 0x00001000,  
   FIF_FUNCNAME_RETURNTYPE   = 0x00002000,  
   FIF_FUNCNAME_ARGS         = 0x00004000,  
   FIF_FUNCNAME_LANGUAGE     = 0x00008000,  
   FIF_FUNCNAME_MODULE       = 0x00010000,  
   FIF_FUNCNAME_LINES        = 0x00020000,  
   FIF_FUNCNAME_OFFSET       = 0x00040000,  
   FIF_FUNCNAME_ARGS_TYPES   = 0x00100000,  
   FIF_FUNCNAME_ARGS_NAMES   = 0x00200000,  
   FIF_FUNCNAME_ARGS_VALUES  = 0x00400000,  
   FIF_FUNCNAME_ARGS_ALL     = 0x00700000,  
   FIF_ARGS_TYPES            = 0x01000000,  
   FIF_ARGS_NAMES            = 0x02000000,  
   FIF_ARGS_VALUES           = 0x04000000,  
   FIF_ARGS_ALL              = 0x07000000,  
   FIF_ARGS_NOFORMAT         = 0x08000000,  
   FIF_ARGS_NO_FUNC_EVAL     = 0x10000000,  
   FIF_FILTER_NON_USER_CODE  = 0x20000000,  
   FIF_ARGS_NO_TOSTRING      = 0x40000000,  
   FIF_DESIGN_TIME_EXPR_EVAL = 0x80000000  
};  
```  
  
## <a name="members"></a>Členové  
 FIF_FUNCNAME  
 Inicializace nebo pomocí `m_bstrFuncName` pole.  
  
 FIF_RETURNTYPE  
 Inicializace nebo pomocí `m_bstrReturnType` pole.  
  
 FIF_ARGS  
 Inicializace nebo pomocí `m_bstrArgs` pole.  
  
 FIF_LANGUAGE  
 Inicializace nebo pomocí `m_bstrLanguage` pole.  
  
 FIF_MODULE  
 Inicializace nebo pomocí `m_bstrModule` pole.  
  
 FIF_STACKRANGE  
 Inicializace nebo použití `m_addrMin` a `m_addrMax` pole (zásobník rozsah).  
  
 FIF_FRAME  
 Inicializace nebo pomocí `m_pFrame` pole.  
  
 FIF_DEBUGINFO  
 Inicializace nebo pomocí `m_fHasDebugInfo` pole.  
  
 FIF_STALECODE  
 Inicializace nebo pomocí `m_fStaleCode` pole.  
  
 FIF_ANNOTATEDFRAME  
 Inicializace nebo pomocí `m_fAnnotatedFrame` pole.  
  
 FIF_DEBUG_MODULEP  
 Inicializace nebo pomocí `m_pModule` pole.  
  
 FIF_FUNCNAME_FORMAT  
 Formátuje název funkce. Výsledkem je vrácený v `m_bstrFunName` jsou vyplněna pole a žádná další pole.  
  
 FIF_FUNCNAME_RETURNTYPE  
 Přidá návratový typ, který má `m_bstrFuncName` pole.  
  
 FIF_FUNCNAME_ARGS  
 Přidá argumenty, které mají `m_bstrFuncName` pole.  
  
 FIF_FUNCNAME_LANGUAGE  
 Přidá jazyka, který má `m_bstrFuncName` pole.  
  
 FIF_FUNCNAME_MODULE  
 Přidá na název modulu pro `m_bstrFuncName` pole.  
  
 FIF_FUNCNAME_LINES  
 Přidá počet řádků určených k `m_bstrFuncName` pole.  
  
 FIF_FUNCNAME_OFFSET  
 Přidá `m_bstrFuncName` pole Posun v bajtech od začátku řádku, pokud `FIF_FUNCNAME_LINES` je zadán. Pokud `FIF_FUNCNAME_LINES` není zadaný, nebo pokud čísla řádků nejsou k dispozici, přidá posun v bajtech od začátku funkce.  
  
 FIF_FUNCNAME_ARGS_TYPES  
 Přidá typ každý argument funkce `m_bstrFuncName` pole.  
  
 FIF_FUNCNAME_ARGS_NAMES  
 Přidá název každý argument funkce `m_bstrFuncName` pole.  
  
 FIF_FUNCNAME_ARGS_VALUES  
 Přidá hodnotu každý argument funkce `m_bstrFuncName` pole.  
  
 FIF_FUNCNAME_ARGS_ALL  
 Přidá typu, názvu a hodnoty všech argumentů `m_bstrFuncName` pole.  
  
 FIF_ARGS_TYPES  
 Typy argumentů načíst a formátovány.  
  
 FIF_ARGS_NAMES  
 Názvy argumentu načíst a formátovány.  
  
 FIF_ARGS_VALUES  
 Argument hodnoty načíst a formátovány.  
  
 FIF_ARGS_ALL  
 Načtení a naformátovat typu, názvu a hodnoty všech argumentů.  
  
 FIF_ARGS_NOFORMAT  
 Určuje argumenty, které nejsou naformátovat (například není přidat otvírání a zavírání v závorkách seznam argumentů ani přidat oddělovač mezi argumenty).  
  
 FIF_ARGS_NO_FUNC_EVAL  
 Určuje, že vyhodnocení funkce (vlastnost) by neměl používat při načítání hodnot argumentů.  
  
 FIF_FILTER_NON_USER_CODE  
 Ladění modulu je k filtrování rámce bez uživatelského kódu, nejsou zahrnuty.  
  
 FIF_ARGS_NO_TOSTRING  
 Nepovolit `ToString()` funkce vyhodnocení nebo formátování při vrácení argumenty funkce.  
  
 FIF_DESIGN_TIME_EXPR_EVAL  
 Rámce informace by měl být, že podmínky z hostované doména aplikace namísto hostitelského procesu.  
  
## <a name="remarks"></a>Poznámky  
 Tyto příznaky jsou předávány [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) a [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md) metody, které určují pole, která se mají v inicializovat [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktura nebo struktury.  
  
 Tyto příznaky se také používají k označení které pole [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktura jsou používané a platné, pokud je vrácen strukturu. Tyto hodnoty mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)