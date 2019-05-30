---
title: IDebugProgramPublisher2::PublishProgram | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramPublisher2::PublishProgram
helpviewer_keywords:
- IDebugProgramPublisher2::PublishProgram
ms.assetid: 92ff63f0-e869-4040-b3ae-b2c899e708ff
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5d4f0b279bafe5291679237efdaada7907ddc515
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66343373"
---
# <a name="idebugprogrampublisher2publishprogram"></a>IDebugProgramPublisher2::PublishProgram
Tato metoda provádí program, který je k dispozici pro ladicí stroj (DEs) a správce ladění relace.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT PublishProgram(
   CONST_GUID_ARRAY Engines,
   LPCOLESTR        szFriendlyName,
   IUnknown*        pDebuggeeInterface
);
```

```csharp
int PublishProgram(
   CONST_GUID_ARRAY Engines,
   string           szFriendlyName,
   object           pDebuggeeInterface
);
```

## <a name="parameters"></a>Parametry
`Engines`\
[in] Pole identifikátorů GUID pro DEs, které můžete spustit nebo připojit k tomuto programu.

`szFriendlyName`\
[in] Popisný název pro program (tím se zobrazí v nabídkách a dialogová okna, které budou zobrazovat uživateli).

`pDebuggeeInterface`\
[in] `IUnknown` rozhraní programu (Tato hodnota se používá jako soubor cookie k jednoznačné identifikaci program; tato stejná hodnota se používá program "publikování")

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Chcete-li již nejsou k dispozici pro ladění programu, volání [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md).

## <a name="see-also"></a>Viz také:
- [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)
- [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)