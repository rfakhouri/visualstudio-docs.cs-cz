---
title: IDebugMessageEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMessageEvent2
helpviewer_keywords:
- IDebugMessageEvent2 interface
ms.assetid: a9ff3d00-e9ac-4cd6-bda9-584a4815aff8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 49224ad0018286fffd365857364bf1b37300788f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56720442"
---
# <a name="idebugmessageevent2"></a>IDebugMessageEvent2
Toto rozhraní používá ladicí stroj (DE) k odeslání zprávy do sady Visual Studio, který vyžaduje odpověď od uživatele.

## <a name="syntax"></a>Syntaxe

```
IDebugMessageEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 DE implementuje toto rozhraní pro odeslání zprávy do sady Visual Studio, která vyžaduje odpověď uživatele. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) na stejný objekt jako toto rozhraní musí implementovat rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) přístup `IDebugEvent2` rozhraní.

 Implementace tohoto rozhraní musí komunikovat volání sady Visual Studio [SetResponse](../../../extensibility/debugger/reference/idebugmessageevent2-setresponse.md) na DE. Například to můžete udělat a zobrazí se zpráva pošle zprávu je DE zpracování vláken, nebo objekt implementující toto rozhraní může obsahovat odkaz na DE a zpětné volání DE s odpovědí předaná do `IDebugMessageEvent2::SetResponse`.

## <a name="notes-for-callers"></a>Poznámky pro volající
 DE vytvoří a odešle tento objekt události pro zobrazení zprávy pro uživatele, který vyžaduje odpověď. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který je poskytnut pomocí SDM, když je připojen k laděnému programu.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugMessageEvent2`.

|Metoda|Popis|
|------------|-----------------|
|[GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)|Získá zprávu, která se zobrazí.|
|[SetResponse](../../../extensibility/debugger/reference/idebugmessageevent2-setresponse.md)|Nastaví odpověď, a pokud některý z okna se zprávou.|

## <a name="remarks"></a>Poznámky
 DE bude používat toto rozhraní, pokud vyžaduje konkrétní odpověď od uživatele pro konkrétní zprávu. Například pokud DE dostane zprávu "Přístup byl odepřen" po pokus o vzdálené připojení k programu, DE odešle tuto konkrétní zprávu do sady Visual Studio v `IDebugMessageEvent2` událost s poli styl zprávy `MB_RETRYCANCEL`. To mu umožní opakovat nebo ukončit operaci připojení.

 DE Určuje, jak tuto zprávu zpracovat konvencemi funkce Win32 `MessageBox` (viz [AfxMessageBox](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox) podrobnosti).

 Použití [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md) rozhraní pro odesílání zpráv do Visual Studio, které nevyžadují odpověď od uživatele.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
- [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)