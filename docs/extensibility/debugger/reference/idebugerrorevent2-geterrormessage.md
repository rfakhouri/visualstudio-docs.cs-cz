---
title: IDebugErrorEvent2::GetErrorMessage | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugErrorEvent2::GetErrorMessage
helpviewer_keywords:
- IDebugErrorEvent2::GetErrorMessage
ms.assetid: 9e3b0d74-a2dd-4eaa-bd95-21b2f9c79409
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 049f7a78a414df8202d64c1f25eaba854818c88d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66327717"
---
# <a name="idebugerrorevent2geterrormessage"></a>IDebugErrorEvent2::GetErrorMessage
Vrátí informace, které umožňuje tvorbu čitelné chybovou zprávu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetErrorMessage(
   MESSAGETYPE* pMessageType,
   BSTR*        pbstrErrorFormat,
   HRESULT*     hrErrorReason,
   DWORD*       pdwType,
   BSTR*        pbstrHelpFileName,
   DWORD*       pdwHelpId
);
```

```csharp
int GetErrorMessage(
   out enum_MESSAGETYPE   pMessageType,
   out string             pbstrErrorFormat,
   out int                phrErrorReason,
   out uint               pdwType,
   out string             pbstrHelpFileName,
   out uint               pdwHelpId
);
```

## <a name="parameters"></a>Parametry
`pMessageType`\
[out] Vrátí hodnotu z [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md) výčet popisující typ zprávy.

`pbstrErrorFormat`\
[out] Formát závěrečná zpráva uživateli (podrobnosti viz "Poznámky").

`hrErrorReason`\
[out] Kód chyby zprávy je o.

`pdwType`\
[out] Závažnost chyby (použijte MB_XXX konstanty pro `MessageBox`; například `MB_EXCLAMATION` nebo `MB_WARNING`).

`pbstrHelpFileName`\
[out] Cesta k souboru nápovědy (nastavena na hodnotu null, pokud neexistuje žádný soubor nápovědy).

`pdwHelpId`\
[out] ID tématu nápovědy k zobrazení (nastavena na 0, pokud není žádná Nápověda).

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Chybová zpráva musí být formátována podle `"What I was doing.  %1"`. `"%1"` By pak vyměnit volajícím s chybovou zprávou, odvozený z kódu chyby (kterou vrací `hrErrorReason`). `pMessageType` Určuje parametr volající zobrazení poslední chybová zpráva.

## <a name="see-also"></a>Viz také:
- [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)
- [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)