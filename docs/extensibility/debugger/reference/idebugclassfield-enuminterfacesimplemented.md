---
title: IDebugClassField::EnumInterfacesImplemented | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: bffae40f1e5212132c89b6b71b7fc83cca6ebb42
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877022"
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
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)