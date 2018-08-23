---
title: Upravit a pokračovat (Visual Basic) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
helpviewer_keywords:
- Edit and Continue, 64-bit
- Edit and Continue [Visual Basic]
- debugging [Visual Basic], Edit and Continue
- Visual Basic, Edit and Continue
- 64-bit Edit and Continue
ms.assetid: 7e90f34f-e699-45ab-a4c9-a4b527c498c8
caps.latest.revision: 43
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 825eac4ab53e95904e85a794b665ce6f6b11f873
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42665884"
---
# <a name="edit-and-continue-visual-basic"></a>Upravit a pokračovat (Visual Basic)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [upravit a pokračovat (Visual Basic)](https://docs.microsoft.com/visualstudio/debugger/edit-and-continue-visual-basic).  
  
Upravit a pokračovat je funkce pro [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ladění, která umožňuje změnit kód, zatímco je spuštěn v režimu pozastavení. Po použití úprav kódu, můžete pokračovat v provádění kódu pomocí nové úpravy na místě a vidět její účinek.  
  
 Můžete použít upravit a pokračovat funkci pokaždé, když zadáte režim přerušení. V režimu přerušení, ukazatele na instrukci, žlutá šipka v okně zdroje odkazuje na řádek, který se má provést a umístí na spustitelný soubor výpisu v těle metody nebo vlastnosti. Spustitelné příkazy v režimu pozastavení můžete provést téměř jakýkoli druh změn, a tato změna se začlení do základního projektu. V režimu přerušení, ale obecně nelze změnit příkazy deklarace, jako jsou veřejné metody, veřejná pole nebo deklarace tříd.  
  
 Pokud provedete úpravy neoprávněným, tato změna je označené fialovou vlnovkou a úlohy se zobrazí v seznamu úkolů. Pokud chcete pokračovat v používání funkce upravit a pokračovat, musíte vrátit neoprávněné úpravy. Některé úpravy, neoprávněným může být povoleno v případě aktivace mimo funkce upravit a pokračovat. Pokud chcete zachovat výsledky neoprávněné upravit, musíte Zastavit ladění a restartujte aplikaci.  
  
 Upravit a pokračovat je podporována pro projekty 64-bit, které jsou cíleny na rozhraní .NET Framework 4.5.1.  
  
 Upravit a pokračovat není podporována při spuštění ladění pomocí **připojit k procesu**. Upravit a pokračovat není podporována pro optimalizovaný kód, smíšené spravovaného a nativního kódu nebo projekty Compact Framework (Smart Device).  
  
 Témata v této části poskytují další podrobnosti o tom, jak používat tuto funkci a jaké druhy změny nejsou povoleny.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: použití úprav v režimu pozastavení pomocí operace upravit a pokračovat](../debugger/how-to-apply-edits-in-break-mode-with-edit-and-continue.md)  
 Vysvětluje, jak použít kód úprav v režimu pozastavení.  
  
 [Nepodporované úpravy v jazyce Visual Basic operaci upravit a pokračovat](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md)  
 Popisuje, jaké typy úprav nelze provádět v [!INCLUDE[vb_current_short](../includes/vb-current-short-md.md)] upravit a pokračovat.  
  
## <a name="related-sections"></a>Související oddíly  
 [Upravit a pokračovat](../debugger/edit-and-continue.md)  
 Obsahuje seznam témat, upravit a pokračovat.



