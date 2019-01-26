---
title: IDebugClassField::EnumInterfacesImplemented | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugClassField::EnumInterfacesImplemented
helpviewer_keywords:
- IDebugClassField::EnumInterfacesImplemented method
ms.assetid: e5523e45-d350-491e-a92c-fe0ca97d2052
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: da72bcbe32a4de2760d7b42a580c0550b5cfa17f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54944732"
---
# <a name="idebugclassfieldenuminterfacesimplemented"></a>IDebugClassField::EnumInterfacesImplemented
Vytvoří čítač pro rozhraní implementována touto třídou.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumInterfacesImplemented(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumInterfacesImplemented(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam rozhraní implementovaná. Vrátí hodnotu null, pokud nejsou žádná rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě, že neexistují žádná rozhraní implementované na této třídě. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každý prvek výčtu je [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) objekt popisující rozhraní. Všimněte si, že nespravované [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)] kódu nepoužívá rozhraní jako samostatné entity, takže tato metoda vždy vrátí hodnotu null pro nespravované [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)] kódu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)