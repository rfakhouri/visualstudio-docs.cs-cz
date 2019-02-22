---
title: Po dosažení dialogové okno zarážky | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.whenbreakpointishit
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
ms.assetid: 476e3d98-cf35-4338-b124-cd0f3010d854
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d4cc3c2366ca20328f591b0661e8c2b3e5af1e45
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717699"
---
# <a name="when-breakpoint-is-hit-dialog-box"></a>Dialogové okno Při průchodu zarážkou
V tomto dialogovém můžete přizpůsobit akci, která nastane, pokud je dosaženo zarážky.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Vytisknout zprávu** vytiskne zprávu pomocí syntaxe DebuggerDisplay. Další informace najdete v tématu [pomocí atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md).

 Tomuto textovému poli podporuje také klíčová slova (jako je například $ADDRESS), které můžete použít samostatně nebo ve složených závorkách DebuggerDisplay výrazu. K dispozici klíčová slova jsou uvedeny v dialogovém okně.

 **Pokračovat v provádění** tento ovládací prvek je povolená pouze tehdy, když **vytisknout zprávu** zaškrtnuto. Pro tento ovládací prvek vybrán zarážky můžete použít jako trasování pro trasování provádění programu, místo zastavení, když je nalezeno umístění.

## <a name="see-also"></a>Viz také
- [Použití zarážek](../debugger/using-breakpoints.md)
- [Používání atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)