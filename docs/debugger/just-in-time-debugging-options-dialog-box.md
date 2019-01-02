---
title: Just-In-Time, ladění, dialogové okno Možnosti | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Debugger.JIT
- vs.debug.options.JIT
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Just-In-Time debugging, setting options
- Options dialog box, debugging
ms.assetid: 7f11b2e3-3fb5-449d-b07c-6ecf1d6a487d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 05a1cc9e4847b9ffa2c873b137c35bfbf6f83f83
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53968112"
---
# <a name="just-in-time-debugging-options-dialog-box"></a>Za běhu, ladění, dialogové okno Možnosti
Pro přístup **Just-In-Time** stránky, přejděte na **nástroje** nabídky a klikněte na tlačítko **možnosti**. V **možnosti** dialogového okna rozbalte **ladění** uzel a vyberte možnost **Just-In-Time**. Tato stránka umožňuje povolit Just-In-Time ladění pro spravovaný kód, nativního kódu a skriptů. Další informace najdete v tématu [ladění za běhu](../debugger/just-in-time-debugging-in-visual-studio.md).  
  
 Můžete povolit Just-In-Time ladění pro tyto typy programu:  
  
- Spravovaní  
  
- Nativní  
  
- Skript  
  
  Ladění Just-In-Time je postup pro ladění programu, který je spuštěn mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Můžete spustit aplikaci vytvořen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] prostředí. Pokud jste povolili Just-in-time ladění, chyby se zobrazí dialogové okno s dotazem, zda chcete ladit.  
  
## <a name="associated-warnings"></a>Související upozornění  
 Při návštěvě této stránky **možnosti** dialogové okno, může se zobrazit zpráva s upozorněním takto:  
  
 **Jiný ladicí program se registroval jako Just-In-Time debugger. Pokud chcete opravit, povolte Just-In-Time ladění nebo spuštěním opravy sady Visual Studio.**  
  
 Tato zpráva se zobrazí, pokud máte jiný ladicí program, případně starší verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ladicího programu, nastavit jako Just-In-Time debugger.  
  
 Další zprávu, zobrazí se pravděpodobně vypadá takto:  
  
 **Just-In-Time ladění registrace byly zjištěny chyby. Pokud chcete opravit, povolte Just-In-Time ladění nebo spuštěním opravy sady Visual Studio.**  
  
 Pokud se zobrazí některá z těchto upozornění Just-In-Time ladění pomocí [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] vyžaduje oprávnění správce, dokud nebude tento problém opravili. Pokud se pokusíte povolit pouze – jako bez oprávnění správce za těchto podmínek, zobrazí se následující chybová zpráva:  
  
 **Přístup byl odepřen. Nemáte povolení Just-In-Time správce ladění nebo opravte instalaci sady Visual Studio.**  
  
## <a name="see-also"></a>Viz také  
 [Ladění, dialogové okno Možnosti](../debugger/debugging-options-dialog-box.md)   
 [Postupy: Určení nastavení ladicího programu](../debugger/how-to-specify-debugger-settings.md)