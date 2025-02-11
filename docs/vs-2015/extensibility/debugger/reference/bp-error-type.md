---
title: BP_ERROR_TYPE | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- BP_ERROR_TYPE
helpviewer_keywords:
- BP_ERROR_TYPE enumeration
ms.assetid: c483eaab-db29-46de-bfdb-5c2a9a9cfb68
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2317fafe410cacfca1c77b669a54669ea6e2224a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68153537"
---
# <a name="bperrortype"></a>BP_ERROR_TYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Určuje typ chyby zarážky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_BP_ERROR_TYPE {   
   BPET_NONE            = 0x00000000,  
   BPET_TYPE_WARNING    = 0x00000001,  
   BPET_TYPE_ERROR      = 0x00000002,  
   BPET_SEV_HIGH        = 0x0F000000,  
   BPET_SEV_GENERAL     = 0x07000000,  
   BPET_SEV_LOW         = 0x01000000,  
   BPET_TYPE_MASK       = 0x0000ffff,  
   BPET_SEV_MASK        = 0xffff0000,  
   BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,  
   BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,  
   BPET_ALL             = 0xffffffff  
};  
typedef DWORD BP_ERROR_TYPE;  
```  
  
```csharp  
public enum enum_BP_ERROR_TYPE {   
   BPET_NONE            = 0x00000000,  
   BPET_TYPE_WARNING    = 0x00000001,  
   BPET_TYPE_ERROR      = 0x00000002,  
   BPET_SEV_HIGH        = 0x0F000000,  
   BPET_SEV_GENERAL     = 0x07000000,  
   BPET_SEV_LOW         = 0x01000000,  
   BPET_TYPE_MASK       = 0x0000ffff,  
   BPET_SEV_MASK        = 0xffff0000,  
   BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,  
   BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,  
   BPET_ALL             = 0xffffffff  
};  
```  
  
## <a name="members"></a>Členové  
 BPET_NONE  
 Určuje žádná chyba zarážky.  
  
 BPET_TYPE_WARNING  
 Určuje Chyba zarážky upozornění style.  
  
 BPET_TYPE_ERROR  
 Určuje chybu stylu chyby zarážky.  
  
 BPET_SEV_HIGH  
 Určuje Chyba zarážky vysokou závažností.  
  
 BPET_SEV_GENERAL  
 Určuje střední závažností zarážky chyb.  
  
 BPET_SEV_LOW  
 Určuje chybu s nízkou závažností zarážku.  
  
 BPET_TYPE_MASK  
 Určuje chybu maska – vizuální styl zarážku.  
  
 BPET_SEV_MASK  
 Určuje závažnost. maska stylu zarážky chyb.  
  
 BPET_GENERAL_WARNING  
 Určuje Obecné upozornění stylu zarážky chyb.  
  
 BPET_GENERAL_ERROR  
 Určuje obecné stylu chyby zarážky chyb.  
  
 BPET_ALL  
 Určuje všechny typy chyb zarážku.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty lze kombinovat pomocí logické bitové `OR` a používá se pro `dwType` člena [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) struktury. Předán jako parametr [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md) metody.  
  
 Typ chyby zarážky se skládá z typu a závažnosti. To znamená, že je typ chyby zarážky nikdy pouze typ (například `BPET_TYPE_ERROR`,) nebo závažnosti (například `BPET_SEV_GENERAL`) samostatně. `BPET_GENERAL_WARNING` a `BPET_GENERAL_ERROR` poskytují předem definovaných hodnot pro obecné upozornění a chyby zarážky.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)
