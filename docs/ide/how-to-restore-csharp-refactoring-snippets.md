---
redirect_url: /visualstudio/csharp-ide/refactoring-csharp
ms.openlocfilehash: cb4e45847008d99aa17b5ce3dde83da036a53dbb
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
Title: "postupy: obnovení fragmentů kódu Refactoring C# | Microsoft Docs"ms.custom:" "ms.date: ms.reviewer" 11/04/2016":" "ms.suite:" "ms.technology: 
  - ms.tgt_pltfrm "vs-ide Obecné": "" ms.topic: "článku" helpviewer_keywords: 
  - "nebezpečné rozšíření"
  - "rozšíření, unsafe" ms.assetid: 12114273-7f2f-43d0-abcb-2d4711a3a68d caps.latest.revision: 20 Autor: ms.author "gewarren": "gewarren" správce: ghogen
---
# <a name="how-to-restore-c-refactoring-snippets"></a>Postupy: Obnovení fragmentů kódu refaktoringu jazyka C#
Operace refaktoringu jazyka C# využívají fragmenty kódu, které najde v adresáři následující:  
  
 *Instalační adresář*\Microsoft Visual Studio 15.0\VC#\Snippets\\*ID jazyka*\Refactoring  
  
 Pokud tento adresář Refactoring nebo všechny soubory v tomto adresáři odstraněny nebo poškozený, pak operace refaktoringu jazyka C# nemusí fungovat v prostředí IDE. Následující postupy můžete obnovit fragmentů kódu refaktoringu jazyka C#.  
  
### <a name="to-verify-c-refactoring-snippets-are-available-through-the-code-snippet-manager"></a>Ověření C# jsou k dispozici prostřednictvím Správce fragmentů kódu refaktoringu fragmenty kódu  
  
1.  V **nástroje** nabídce vyberte možnost **Správce fragmentů kódu**.  
  
2.  V **Správce fragmentů kódu** dialogové okno, vyberte **Visual C#** z **jazyk** rozevíracího seznamu.  
  
     A **Refactoring** složky by se měla objevit v seznamu stromové zobrazení složky.  
  
### <a name="to-restore-refactoring-see-comment-in-code-snippet-manager"></a>Chcete-li obnovit refaktoring najdete v článku komentář ve Správci fragmentu kódu  
  
1.  Pokud **Refactoring** složky neobsahuje zobrazí v seznamu složek zobrazení stromu Správce fragmentů kódu, a pomocí tohoto postupu můžete přidat fragmentů kódu refaktoringu zpět do kódu fragment kódu správce.  
  
2.  V **nástroje** nabídce vyberte možnost **Správce fragmentů kódu**.  
  
3.  V **Správce fragmentů kódu** dialogové okno, vyberte **Visual C#** z **jazyk** rozevíracího seznamu.  
  
4.  Klikněte na tlačítko **přidat**. **Adresář fragmenty kódu** se zobrazí dialogové okno, které vám pomůže najít a určete adresář, který chcete přidat zpět do správce fragment kódu,.  
  
5.  Vyhledejte **Refactoring** složky, jejichž cesta adresáře je:  
  
     *Instalační adresář*\Microsoft Visual Studio 15.0\VC#\Snippets\\*ID jazyka*\Refactoring  
  
     Skutečné cesty je podobný následujícímu pro výchozí instalaci:  
  
     C:\Program Files\Microsoft 15.0\VC#\Snippets\1033\Refactoring sady Visual Studio.  
  
6.  Klikněte na tlačítko **otevřete** v **adresář fragmenty kódu** dialogové okno a pak klikněte na tlačítko **OK** ve Správci fragmentů kódu.  
  
## <a name="see-also"></a>Viz také  
 [Fragmenty kódu jazyka Visual C#](../ide/visual-csharp-code-snippets.md)   
 [Refaktoring (C#)](../csharp-ide/refactoring-csharp.md)   
 [Fragmenty kódu](../ide/code-snippets.md)