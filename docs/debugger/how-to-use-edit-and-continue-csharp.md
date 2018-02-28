---
title: "Postupy: použití operace upravit a pokračovat (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [C#], about Edit and Continue
ms.assetid: 40e136d8-a08c-43bd-b313-fb821c55eb3c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: fe77428d1d9cfb5ff12554e87ec9afe15d6c86b8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-edit-and-continue-c"></a>Postupy: Použití operace Upravit a pokračovat (C#)
Upravit a pokračovat pro jazyk C# můžete provést změny kódu v režimu pozastavení při ladění. Změny lze použít bez nutnosti zastavit a restartovat relaci ladění.  
  
 Upravit a pokračovat se vyvolává automaticky při proveďte změny v režimu pozastavení a pak vyberte ladicí program provádění příkazu, například **pokračovat**, **krok**, nebo **další příkaz Set**, nebo vyhodnocení funkce v okně ladicí program.  
  
> [!NOTE]
>  Upravit a pokračovat není podporováno při ladění optimalizován kódu, smíšené nativní nebo spravovaný kód nebo kód integrace modulu runtime (CLR) běžné jazyka SQL Server. Informace o dalších nepodporované scénáře, najdete v části [podporované (C# a Visual Basic) změn kódu](../debugger/supported-code-changes-csharp.md). Pokud se pokusíte použít změny kódu v jednom z těchto scénářů, zobrazí ladicí program, dialogové okno s vysvětlením, upravit a pokračovat není podporována.  
  
### <a name="to-invoke-edit-and-continue-automatically"></a>K vyvolání upravit a pokračovat automaticky  
  
1.  V režimu pozastavení proveďte změnu zdrojového kódu.  
  
2.  Z **ladění** nabídky, klikněte na tlačítko **pokračovat**, **krok**, nebo **další příkaz Set** nebo vyhodnocení funkce v okně ladicí program.  
  
     Nové kódu a ladění pokračuje nový kód. Některé změny nejsou podporovány upravit a pokračovat. Další informace najdete v tématu [podporované (C# a Visual Basic) změn kódu](../debugger/supported-code-changes-csharp.md).  
  
### <a name="to-enabledisable-edit-and-continue"></a>Povolení a zakázání upravit a pokračovat  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
2.  V **možnosti** dialogové okno, rozbalte seznam **ladění** uzel a vyberte možnost **upravit a pokračovat**.  
  
3.  V **možnosti** dialogové okno **upravit a pokračovat** vyberte nebo zrušte zaškrtnutí **povolit upravit a pokračovat** zaškrtávací políčko.  
  
     Nastavení se projeví při dalším spuštění relace ladění.  
  
## <a name="see-also"></a>Viz také  
 [Upravit a pokračovat (Visual C#)](../debugger/edit-and-continue-visual-csharp.md)   
 [Podporované změny kódu (C# a Visual Basic)](../debugger/supported-code-changes-csharp.md)   