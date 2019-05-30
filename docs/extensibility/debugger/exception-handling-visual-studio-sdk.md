---
title: Zpracování (Visual Studio SDK) výjimek | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], exception handling
ms.assetid: 7279dc16-db14-482c-86b8-7b3da5a581d2
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7fdb309c01979985d1c00eedab9c496d0af44e07
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66315268"
---
# <a name="exception-handling-visual-studio-sdk"></a>Zpracování výjimek (Visual Studio SDK)
Následující část popisuje proces, který nastane, pokud jsou výjimky vyvolány.

## <a name="exception-handling-process"></a>Proces zpracování výjimek

1. Když je nejprve vyvolána výjimka, ale předtím, než je zpracována obslužnou rutinu výjimky v programu, který se právě ladí, odešle ladicího stroje (DE) [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) do Správce ladění relace (SDM) jako událostí ukončení. `IDebugExceptionEvent2` Se odešle, pokud jen nastavení pro výjimku (zadané v dialogovém okně výjimky ladění balíčku) zadejte, že uživatel chce, aby k zastavení na oznámení o první odpovídající výjimce.

2. Volání SDM [IDebugExceptionEvent2::GetException](../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) GET pro vlastnost výjimky.

3. Ladění balíčku volání [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) k určení, jaké možnosti pro konkrétního uživatele.

4. Ladění balíčku žádá uživatele, jak zpracovat výjimky tak, že otevřete dialogové okno první odpovídající výjimce.

5. Pokud uživatel zvolí možnost pokračovat, zavolá SDM [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md).

    - Pokud metoda vrátí hodnotu S_OK, zavolá [IDebugExceptionEvent2::PassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-passtodebuggee.md).

         -nebo-

         Pokud metoda vrátí S_FALSE, program laděn dostane druhou šanci zpracování výjimky.

6. Pokud se laděný program nemá žádná obslužná rutina pro sekundu odpovídající výjimce, DE odešle `IDebugExceptionEvent2` k SDM jako **EVENT_SYNC_STOP**.

7. Ladění balíčku žádá uživatele, jak zpracovat výjimky tak, že otevřete dialogové okno první odpovídající výjimce.

8. Ladění balíčku volání [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) k určení, jaké možnosti pro konkrétního uživatele.

9. Ladění balíčku žádá uživatele, jak zpracovat výjimky tak, že otevřete dialogové okno sekundu odpovídající výjimce.

10. Pokud metoda vrátí hodnotu S_OK, zavolá `IDebugExceptionEvent2::PassToDebuggee`.

## <a name="see-also"></a>Viz také:
- [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)