---
title: IDebugPortSupplier3 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier3
helpviewer_keywords:
- IDebugPortSupplier3 interface
ms.assetid: e458cd02-2370-4435-8953-17d7a60ce152
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ca7113a1b108713b5dd7cf0f17511cec39a1b8b6
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56695489"
---
# <a name="idebugportsupplier3"></a>IDebugPortSupplier3
Toto rozhraní umožňuje volajícímu určit, zda dodavatele portu můžete zachovat porty mezi vyvolání ladicího programu (podle jejich zápis na disk) a potom získá seznam těchto zachovaných portů.

## <a name="syntax"></a>Syntaxe

```
IDebugPortSupplier3 : IDebugPortSupplier2
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Dodavatel port. Tento vlastní port implementuje toto rozhraní pro podporu uchování nebo ukládání informací o portu na disk. Toto rozhraní musí být implementováno na stejný objekt jako [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [QueryInterface](/cpp/atl/queryinterface) na `IDebugPortSupplier2` rozhraní k získání tohoto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod zděděných z [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) rozhraní, toto rozhraní podporuje následující:

|Metoda|Popis|
|------------|-----------------|
|[CanPersistPorts](../../../extensibility/debugger/reference/idebugportsupplier3-canpersistports.md)|Vrátí, zda dodavatele portu můžete zachovaly porty (je zápis na disk) mezi vyvolání ladicího programu.|
|[EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md)|Vrátí objekt, který je možné vytvořit výčet prostřednictvím všechny porty, které byly vytvořeny na disku podle dodavatele tohoto portu.|

## <a name="remarks"></a>Poznámky
 Pokud dodavatele portu můžete zachovat porty ve volání, musí implementovat toto rozhraní. Porty by měly být načteny při dodavatele portu je vytvořena instance a zapíšou na disk při zničení dodavatele portu.

 Ladicí stroj obvykle nekomunikuje s dodavatele portu a nebude mít žádný použijte pro toto rozhraní.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)