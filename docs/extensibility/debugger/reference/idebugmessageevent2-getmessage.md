---
title: IDebugMessageEvent2::GetMessage | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMessageEvent2::GetMessage
helpviewer_keywords:
- GetMessage method
- IDebugMessageEvent2::GetMessage method
ms.assetid: 9fca7285-f7f1-422d-8565-92bf0e0db60a
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 758b3b860167ed8c2db8bb20c0d76ab289e39a0f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346895"
---
# <a name="idebugmessageevent2getmessage"></a>IDebugMessageEvent2::GetMessage
Získá zprávu, která se zobrazí.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetMessage( 
   MESSAGETYPE* pMessageType,
   BSTR*        pbstrMessage,
   DWORD*       pdwType,
   BSTR*        pbstrHelpFileName,
   DWORD*       pdwHelpId
);
```

```csharp
int GetMessage( 
   out enum_MESSAGETYPE pMessageType,
   out string           pbstrMessage,
   out uint             pdwType,
   out string           pbstrHelpFileName,
   out uint             dwHelpId
);
```

## <a name="parameters"></a>Parametry
`pMessageType`\
[out] Vrátí hodnotu z [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md) výčet, který popisuje typ zprávy.

`pbstrMessage`\
[out] Odpovídá na zprávu.

`pdwType`\
[out] Vrátí typ zprávy, pomocí konvencí Win32 `MessageBox` funkce. Zobrazit [AfxMessageBox](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox) funkce podrobnosti.

`pbstrHelpFileName`\
[out v] Vrátí název souboru nápovědy. Může být s hodnotou null (C++) nebo prázdná hodnota (C#), pokud neexistuje žádný soubor nápovědy.

`pdwHelpId`\
[out v] Vrátí identifikátor nápovědy. Může být 0, pokud není žádná nápověda přidružené k této zprávě.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)
- [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)
- [AfxMessageBox](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox)