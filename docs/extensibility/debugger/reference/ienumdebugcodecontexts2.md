---
title: IEnumDebugCodeContexts2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugCodeContexts2
helpviewer_keywords:
- IEnumDebugCodeContexts2
ms.assetid: 72915146-215f-4c99-a034-131b2b474e0e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cd05ffc383e4b2e37280f7b8967915675dec69b9
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65223350"
---
# <a name="ienumdebugcodecontexts2"></a>IEnumDebugCodeContexts2
Toto rozhraní zobrazí kód kontexty přidružené relace ladění nebo s konkrétní aplikaci nebo dokumentu.

## <a name="syntax"></a>Syntaxe

```
IEnumDebugCodeContexts2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní představující seznam kontexty kód pro konkrétní text pozice v programu, nebo seznam kontexty kód pro kontext určitého dokumentu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md) získat toto rozhraní představující seznam kontexty kódu pro určitý text pozice v programu zdrojový dokument.

 Volání [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md) získat toto rozhraní představující seznam všech kód kontextech v konkrétní zdrojový dokument.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugCodeContexts2`.

|Metoda|Popis|
|------------|-----------------|
|[Next](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-next.md)|Načte zadaný počet kontextů kód v sekvenci výčtu.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-skip.md)|Vynechá zadaný počet kontextů kód v sekvenci výčtu.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-reset.md)|Návrat na začátek sekvence výčtu.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-getcount.md)|Získá počet kontextů kód v enumerátor.|

## <a name="remarks"></a>Poznámky
 Visual Studio volání [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md) k naplnění seznamu kontextů kód může uživatel vybrat z při nastavení dalšího příkazu nebo zobrazení zpětného překladu pro zdrojový soubor. Kontexty více kódu může dojít například při existuje více instancí šablony stylu C++.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)
- [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)