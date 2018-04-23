---
title: V běhu, ladění, dialogové okno Možnosti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: 7be7dacbe7b3b89b8bdc09515c23d7597e7e55e5
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="just-in-time-debugging-options-dialog-box"></a>Za běhu, ladění, dialogové okno Možnosti
Pro přístup k **pouze za běhu** stránky, přejděte na **nástroje** nabídky a klikněte na tlačítko **možnosti**. V **možnosti** dialogové okno, rozbalte seznam **ladění** uzel a vyberte možnost **pouze za běhu**. Tato stránka umožňuje povolit pouze za běhu ladění pro spravovaný kód, nativního kódu a skript. Další informace najdete v tématu [ladění JIT](../debugger/just-in-time-debugging-in-visual-studio.md).  
  
 Můžete povolit pouze za běhu ladění pro tyto typy program:  
  
-   Spravované  
  
-   Nativní  
  
-   Skript  
  
 Ladění za běhu je technika pro ladění programu, který je spuštěn mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Můžete spustit program vytvořené v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] prostředí. Pokud je povolena pouze za běhu ladění, havárie se zobrazí dialogové okno s dotazem, pokud chcete ladit.  
  
## <a name="associated-warnings"></a>Přidružené upozornění  
 Při návštěvě této stránce **možnosti** dialogové okno, může se zobrazit zpráva s upozorněním takto:  
  
 **Ladicí program jiné zaregistroval jako pouze v době ladicí program. Chcete-li opravit, povolte pouze za běhu ladění nebo spustit opravu Visual Studio.**  
  
 Tato zpráva se zobrazí, pokud máte jiný ladicího programu, které by mohly mít starší verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ladicí program, nastavte jako pouze v době ladicí program.  
  
 Další zprávu, může se zobrazit vypadá takto:  
  
 **Za běhu ladění registrace byly zjištěny chyby. Chcete-li opravit, povolte pouze za běhu ladění nebo spustit opravu Visual Studio.**  
  
 Pokud tato upozornění se zobrazí pouze za běhu ladění pomocí [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] vyžaduje oprávnění správce, dokud opravě problému. Pokud se pokusíte povolit jenom-jako bez oprávnění správce v těchto podmínkách, zobrazí se následující chybová zpráva:  
  
 **Přístup byl odepřen. Máte povolit pouze za běhu správce ladění, nebo opravte instalaci sady Visual Studio.**  
  
## <a name="see-also"></a>Viz také  
 [Ladění, dialogové okno Možnosti](../debugger/debugging-options-dialog-box.md)   
 [Postupy: určení nastavení ladicího programu](../debugger/how-to-specify-debugger-settings.md)