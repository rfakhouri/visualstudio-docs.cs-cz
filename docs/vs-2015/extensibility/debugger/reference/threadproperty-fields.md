---
title: THREADPROPERTY_FIELDS | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- THREADPROPERTY_FIELDS
helpviewer_keywords:
- THREADPROPERTY_FIELDS enumeration
ms.assetid: 5b88acb9-03ea-4c29-a788-f0087dccbe23
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: dc0e0f7cae4aed887809c22bda0cd6a9ed50307f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68204810"
---
# <a name="threadpropertyfields"></a>THREADPROPERTY_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Určuje, jaké informace o vlákno má být načtena.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_THREADPROPERTY_FIELDS {   
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
public enum enum_THREADPROPERTY_FIELDS {   
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
 Inicializace/použít `dwThreadId` pole [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) struktury.  
  
 TPF_SUSPENDCOUNT  
 Inicializace/použít `dwSuspendCount` pole `THREADPROPERTIE`struktura.  
  
 TPF_STATE  
 Inicializace/použít `dwThreadState` pole `THREADPROPERTIE`struktura.  
  
 TPF_PRIORITY  
 Inicializace/použít `bstrPriority` pole `THREADPROPERTIE`struktura.  
  
 TPF_NAME  
 Inicializace/použít `bstrName` pole `THREADPROPERTIE`struktura.  
  
 TPF_LOCATION  
 Inicializace/použít `bstrLocation` pole `THREADPROPERTIE`struktura.  
  
 TPF_ALLFIELDS  
 Určuje všechna pole.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předány jako argument [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md) indikace které pole [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) struktury mají být inicializovány.  
  
 Tyto hodnoty jsou také používány v `dwFields` člena `THREADPROPERTIES` struktury k označení pole, která se používá a je platný.  
  
 Tyto příznaky lze kombinovat pomocí logické bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)   
 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)
