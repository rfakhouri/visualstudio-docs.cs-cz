---
title: Cílí na předchozí verze rozhraní .NET Framework proF#
description: Další informace o cílení na starší verzi rozhraní .NET Framework při použití F# v sadě Visual Studio.
ms.date: 07/11/2018
ms.topic: troubleshooting
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
monikerRange: vs-2017
ms.openlocfilehash: 2e0d580ac18142010a306d3fb4de19eb69b0b91b
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66746705"
---
# <a name="target-older-versions-of-net-f"></a>Cíleny na starší verze rozhraní .NET (F#)

Pokud se pokusíte cílit na rozhraní .NET Framework 2.0, 3.0 nebo 3.5 v se může objevit následující chyba F# projektu při instalaci sady Visual Studio na Windows 8.1:

**Tento projekt vyžaduje rozhraní příkazového řádku 2.0 F# modulu runtime, ale tento modul runtime není nainstalována.**

Tato chyba se ví, že dojde k pod následující kombinace podmínek:

- Instalaci sady Visual Studio na Windows 8.1.

- Před instalací sady Visual Studio jste nepovolili rozhraní .NET Framework 3.5.

- Váš projekt cílí na .NET Framework 2.0, 3.0 nebo 3.5.

Při instalaci sady Visual Studio zjistí nainstalovaných verzí rozhraní .NET Framework. Visual Studio nainstaluje F# 2.0 runtime pouze v případě, že je nainstalované a povolené rozhraní .NET Framework 3.5.

## <a name="resolve-the-error"></a>Pokud chcete chybu vyřešit

Chcete-li vyřešit tuto chybu, můžete buď:

- Cílení na novější verzi rozhraní .NET Framework.

- Povolte rozhraní .NET Framework 3.5 ve Windows 8.1 a potom nainstalujte F# 2.0 runtime tak, že opravíte instalaci sady Visual Studio. Postupujte podle kroků provedete to tak.

### <a name="to-enable-the-net-framework-35-on-windows-81"></a>Chcete-li povolit rozhraní .NET Framework 3.5 ve Windows 8.1

1. Na **Start** zadejte **ovládací panely**.

   Při psaní **ovládací panely** ikona se zobrazuje v části **aplikace** záhlaví.

2. Zvolte **ovládací panely** ikonu, zvolte **programy** ikony a klikněte na tlačítko **Windows zapnout nebo vypnout funkce** odkaz.

3. Ujistěte se, že **rozhraní .NET Framework 3.5 (zahrnuje .NET 2.0 a 3.0)** zaškrtávací políčko zaškrtnuto a klikněte na tlačítko **OK** tlačítko. Není nutné zaškrtněte políčka pro všechny podřízené uzly pro volitelné součásti rozhraní .NET Framework.

   Rozhraní .NET Framework 3.5 je povolená, pokud ho ještě nebyl.

### <a name="to-install-the-f-20-runtime"></a>Chcete-li nainstalovat F# 2.0 modulu runtime

Postupujte podle [kroky pro opravu sady Visual Studio](../install/repair-visual-studio.md).

## <a name="see-also"></a>Viz také:

- [F#Průvodce (.NET Framework)](/dotnet/fsharp/)
- [F#v sadě Visual Studio](fsharp-visual-studio.md)