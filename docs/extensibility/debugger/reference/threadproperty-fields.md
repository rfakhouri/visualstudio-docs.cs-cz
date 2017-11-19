---
title: THREADPROPERTY_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: THREADPROPERTY_FIELDS
helpviewer_keywords: THREADPROPERTY_FIELDS enumeration
ms.assetid: 5b88acb9-03ea-4c29-a788-f0087dccbe23
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 626c4aa309c7ce68eaf5d97c734ec4fd731148c1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="threadpropertyfields"></a>THREADPROPERTY_FIELDS
Určuje, jaké informace o vlákno je mají být načteny.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_THREADPROPERTY_FIELDS {   
   TPF_ID           = 0x0001,  
   TPF_SUSPENDCOUNT = 0x0002,  
   TPF_STATE        = 0x0004,  
   TPF_PRIORITY     = 0x0008,  
   TPF_NAME         = 0x0010,  
   TPF_LOCATION     = 0x0020,  
   TPF_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD THREADPROPERTY_FIELDS;  
```  
  
```csharp  
public enum enum_THREADPROPERTY_FIELDS {   
   TPF_ID           = 0x0001,  
   TPF_SUSPENDCOUNT = 0x0002,  
   TPF_STATE        = 0x0004,  
   TPF_PRIORITY     = 0x0008,  
   TPF_NAME         = 0x0010,  
   TPF_LOCATION     = 0x0020,  
   TPF_ALLFIELDS    = 0xffffffff  
};  
```  
  
## <a name="members"></a>Členové  
 TPF_ID  
 Inicializace nebo použití `dwThreadId` pole z [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) struktury.  
  
 TPF_SUSPENDCOUNT  
 Inicializace nebo pomocí `dwSuspendCount` pole z `THREADPROPERTIE`struktura S.  
  
 TPF_STATE  
 Inicializace nebo pomocí `dwThreadState` pole z `THREADPROPERTIE`struktura S.  
  
 TPF_PRIORITY  
 Inicializace nebo pomocí `bstrPriority` pole z `THREADPROPERTIE`struktura S.  
  
 TPF_NAME  
 Inicializace nebo pomocí `bstrName` pole z `THREADPROPERTIE`struktura S.  
  
 TPF_LOCATION  
 Inicializace nebo pomocí `bstrLocation` pole z `THREADPROPERTIE`struktura S.  
  
 TPF_ALLFIELDS  
 Určuje všechna pole.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předávány jako argument pro [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md) metoda označíte, které pole [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) struktura mají být inicializován.  
  
 Tyto hodnoty se také používají v `dwFields` členem `THREADPROPERTIES` struktura označuje pole, která je platná a použitá.  
  
 Tyto příznaky mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)   
 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)