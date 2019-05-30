---
title: IDebugContainerField::EnumFields | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugContainerField::EnumFields
helpviewer_keywords:
- IDebugContainerField::EnumFields method
ms.assetid: 9e5e681b-ad49-4c62-bd95-4afa11d61a57
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a6d3edeb677af728b1a0fd0e9cf8685e7919d79e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66317934"
---
# <a name="idebugcontainerfieldenumfields"></a>IDebugContainerField::EnumFields
Vytvoří čítač pro pole kontejneru.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumFields( 
   FIELD_KIND         dwKindFilter,
   FIELD_MODIFIERS    dwModifiersFilter,
   LPCOLESTR          pszNameFilter,
   NAME_MATCH         nameMatch,
   IEnumDebugFields** ppEnum
);
```

```csharp
int EnumFields(
   enum_ FIELD_KIND      dwKindFilter,
   enum_ FIELD_MODIFIERS dwModifiersFilter,
   string                pszNameFilter,
   NAME_MATCH            nameMatch,
   out IEnumDebugFields  ppEnum
);
```

## <a name="parameters"></a>Parametry
`dwKindFilter`\
[in] Kombinace [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) konstanty, které vyberte pole pro provedení výčtu. Typy pole můžete popsat typy úložišť, jako je například třídy nebo primitivní nebo konkrétní informace, jako jsou místní, parametr nebo ukazatel "this".

`dwModifiersFilter`\
[in] Kombinace [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md) konstanty, které vyberte pole pro provedení výčtu. Modifikátory pole může být přístupová oprávnění, jako jsou veřejné, privátní nebo úložiště informace, jako je například virtuální, statické nebo konečné.

`pszNameFilter`\
[in] Název pole, které chcete vytvořit výčet. To může být hodnota null, pokud všechna pole se mají vrátit.

`nameMatch`\
[in] Hodnota z [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md) výčet, který určuje, jestli hledání je velká a malá písmena, nebo ne.

`ppEnum`\
[out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam polí. Vrátí hodnotu null, pokud nejsou žádná pole.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK nebo S_FALSE, pokud nejsou žádná pole. V opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 `dwKindFilter`, `dwModifiersFilter`, A `pszNameFilter` parametry je možné kombinovat například, chcete-li vybrat všechny veřejné virtuální metody s názvem "MyMethod".

## <a name="see-also"></a>Viz také:
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)
- [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)
- [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md)