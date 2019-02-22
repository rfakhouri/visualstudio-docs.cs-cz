---
title: IDebugGenericFieldDefinition::ConstructInstantiation | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- ConstructInstantiation
- IDebugGenericFieldDefinition::ConstructInstantiation
ms.assetid: ef8ae261-a98b-4dc2-93b3-7c5191818ba2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8c2fc6b9b7683180c3a9c3f2aa967ba171a48097
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56690679"
---
# <a name="idebuggenericfielddefinitionconstructinstantiation"></a>IDebugGenericFieldDefinition::ConstructInstantiation
Vytvoří instanci pole zadané pole argumentů typu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT ConstructInstantiation(
   ULONG32       cArgs,
   IDebugField** ppArgs,
   IDebugField** ppConstructedField
);
```

```csharp
int ConstructInstantiation(
   uint            cArgs,
   IDebugField[]   ppArgs,
   out IDebugField ppConstructedField
);
```

#### <a name="parameters"></a>Parametry
 `cArgs`

 [in] Počet argumentů `ppArgs` pole.

 `ppArgs`

 [in] Pole, které obsahuje argumenty typu. Argumenty typu musí být uzavřený typy (obecné nebo zcela vytvořenou instanci obecné typy).

 `ppConstructedField`

 [out] Vrátí [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní, které představuje nové pole.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Omezení nekontrolují.

## <a name="see-also"></a>Viz také
- [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)