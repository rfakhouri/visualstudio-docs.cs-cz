---
title: 'Postupy: Použití operace upravit a pokračovat (C#) | Dokumentace Microsoftu'
ms.date: 10/04/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [C#], about Edit and Continue
ms.assetid: 40e136d8-a08c-43bd-b313-fb821c55eb3c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 515068f29045ef92ee7d2323f752ba2185f28cac
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56696347"
---
# <a name="how-to-use-edit-and-continue-c"></a>Postupy: Použití operace Upravit a pokračovat (C#)
S upravit a pokračovat můžete provést a použít změny kódu v režimu pozastavení během ladění, bez nutnosti zastavit a restartovat ladicí relaci.

Upravit a pokračovat pro C# dojde automaticky při provedení změny kódu v režimu přerušení, pokračujte v ladění s použitím **pokračovat**, **krok**, nebo **nastavit další příkaz**, nebo Vyhodnoťte funkci v okně ladicího programu.

Další informace najdete v tématu [upravit a pokračovat (Visual C#)](../debugger/edit-and-continue-visual-csharp.md).

>[!NOTE]
>Upravit a pokračovat není podporována pro optimalizaci, smíšené, nebo systému SQL Server common language runtime (CLR) integrace kódu. Informace o dalších nepodporované scénáře, naleznete v tématu [podporované změny kódu (C# a Visual Basic)](../debugger/supported-code-changes-csharp.md). Pokud se pokusíte upravit a pokračovat v jednom z těchto scénářů, zobrazí se okno se zprávou s informacemi o tom, že funkce upravit a pokračovat není podporována.

**K povolení nebo zakázání funkce upravit a pokračovat:**

1. Pokud jste v relaci ladění, zastavte ladění (**ladění** > **Zastavit ladění** nebo **Shift**+**F5**) .

1. V **nástroje** > **možnosti** (nebo **ladění** > **možnosti**) > **ladění**  >  **Obecné**zaškrtněte nebo zrušte **Povolit Editovat a pokračovat** zaškrtávací políčko.

Nastavení se projeví při spuštění nebo restartování relace ladění.

**Chcete-li použít funkci upravit a pokračovat:**

1. Při ladění v režimu pozastavení změňte zdrojový kód.

1. Z **ladění** nabídky, klikněte na tlačítko **pokračovat**, **krok**, nebo **nastavit další příkaz**, nebo vyhodnotíte funkci v okně ladicího programu.

   Ladění pokračuje s novou, zkompilovaný kód.

Některé typy změn kódu nejsou podporovány funkcemi upravit a pokračovat. Další informace najdete v tématu [podporované změny kódu (C# a Visual Basic)](../debugger/supported-code-changes-csharp.md).
