---
title: ADDRESS_KIND | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ADDRESS_KIND
helpviewer_keywords: ADDRESS_KIND enumeration
ms.assetid: 3a12fbec-7088-4cf9-8f6f-ad8ddec6009a
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c5b35864a7a4e6d5aa0882ac9c0492e0e160ad53
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="addresskind"></a>ADDRESS_KIND
Určuje typy adresy.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_ADDRESS_KIND {  
   ADDRESS_KIND_NATIVE                  = 0x0001,  
   ADDRESS_KIND_UNMANAGED_THIS_RELATIVE = 0x0002,  
   ADDRESS_KIND_UNMANAGED_PHYSICAL      = 0x0005,  
   ADDRESS_KIND_METADATA_METHOD         = 0x0010,  
   ADDRESS_KIND_METADATA_FIELD          = 0x0011,  
   ADDRESS_KIND_METADATA_LOCAL          = 0x0012,  
   ADDRESS_KIND_METADATA_PARAM          = 0x0013,  
   ADDRESS_KIND_METADATA_ARRAYELEM      = 0x0014,  
   ADDRESS_KIND_METADATA_RETVAL         = 0x0015,  
};  
typedef DWORD ADDRESS_KIND;  
```  
  
```csharp  
public enum enum_ADDRESS_KIND {  
   ADDRESS_KIND_NATIVE                  = 0x0001,  
   ADDRESS_KIND_UNMANAGED_THIS_RELATIVE = 0x0002,  
   ADDRESS_KIND_UNMANAGED_PHYSICAL      = 0x0005,  
   ADDRESS_KIND_METADATA_METHOD         = 0x0010,  
   ADDRESS_KIND_METADATA_FIELD          = 0x0011,  
   ADDRESS_KIND_METADATA_LOCAL          = 0x0012,  
   ADDRESS_KIND_METADATA_PARAM          = 0x0013,  
   ADDRESS_KIND_METADATA_ARRAYELEM      = 0x0014,  
   ADDRESS_KIND_METADATA_RETVAL         = 0x0015,  
};  
```  
  
## <a name="terms"></a>Podmínky  
 ADDRESS_KIND_NATIVE  
 Nativní adresy, reprezentována [NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md) struktury.  
  
 ADDRESS_KIND_UNMANAGED_THIS_RELATIVE  
 Nespravované adresu vzhledem k `this` (`Me` v jazyce Visual Basic) ukazatel a reprezentována [UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md) struktury.  
  
 ADDRESS_KIND_UNMANAGED_PHYSICAL  
 Nespravované fyzickou adresu reprezentována [UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md) struktury.  
  
 ADDRESS_KIND_METHOD  
 Metody třídy reprezentována [METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md) struktury.  
  
 ADDRESS_KIND_FIELD  
 Pole třídu reprezentována [METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md) struktury.  
  
 ADDRESS_KIND_LOCAL  
 Adresa je pro místní proměnné a je reprezentována [METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md) struktury.  
  
 ADDRESS_KIND_PARAM  
 Parametr metody nebo funkce, která je reprezentována [METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md) struktury.  
  
 ADDRESS_KIND_ARRAYELEM  
 K elementu pole reprezentována [METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md) struktury.  
  
 ADDRESS_KIND_RETVAL  
 Návratové hodnoty, představované [METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md) struktury.  
  
## <a name="remarks"></a>Poznámky  
 [Getaddress –](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) metoda vrátí [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) struktura, která obsahuje spojení možné struktur, [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) struktury. `dwKind` Pole z `DEBUG_ADDRESS_UNION` struktury blokování `ADDRESS_KIND` hodnotu a popisuje, jak interpretovat pole union.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Getaddress –](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)