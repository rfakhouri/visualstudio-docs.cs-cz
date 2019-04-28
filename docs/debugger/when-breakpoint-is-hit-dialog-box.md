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
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62929196"
---
# <a name="when-breakpoint-is-hit-dialog-box"></a>Dialogové okno Když je volána zarážka
V tomto dialogovém můžete přizpůsobit akci, která nastane, pokud je dosaženo zarážky.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Vytisknout zprávu** vytiskne zprávu pomocí syntaxe DebuggerDisplay. Další informace najdete v tématu [pomocí atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md).

 Tomuto textovému poli podporuje také klíčová slova (jako je například $ADDRESS), které můžete použít samostatně nebo ve složených závorkách DebuggerDisplay výrazu. K dispozici klíčová slova jsou uvedeny v dialogovém okně.

 **Pokračovat v provádění** tento ovládací prvek je povolená pouze tehdy, když **vytisknout zprávu** zaškrtnuto. Pro tento ovládací prvek vybrán zarážky můžete použít jako trasování pro trasování provádění programu, místo zastavení, když je nalezeno umístění.

## <a name="see-also"></a>Viz také
- [Použití zarážek](../debugger/using-breakpoints.md)
- [Používání atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)