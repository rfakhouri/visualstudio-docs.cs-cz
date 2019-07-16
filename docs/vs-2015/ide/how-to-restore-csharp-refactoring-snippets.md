---
title: 'Postupy: Obnovení C# fragmentů kódu refaktoringu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- unsafe expansion
- expansions, unsafe
ms.assetid: 12114273-7f2f-43d0-abcb-2d4711a3a68d
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9f81514db881ad26a5fa827b0bde11df2467f23d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68186272"
---
# <a name="how-to-restore-c-refactoring-snippets"></a>Postupy: Obnovení fragmentů kódu refaktoringu jazyka C#
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Operace refaktoringu jazyka C# využívají fragmenty kódu v následujícím adresáři:  
  
 *Instalační adresář*\Microsoft Visual Studio 14.0\VC#\Snippets\\*ID jazyka*\Refactoring  
  
 Pokud tento adresář refaktoringu, nebo všechny soubory v tomto adresáři je odstraněn nebo poškozen, pak operací refaktoringu jazyka C# nemusí fungovat v integrovaném vývojovém prostředí. Následující postupy vám umožňují obnovení fragmentů kódu refaktoringu jazyka C#.  
  
### <a name="to-verify-c-refactoring-snippets-are-available-through-the-code-snippet-manager"></a>Ověření jazyka C# jsou k dispozici prostřednictvím Správce fragmentů kódu refaktoringu fragmenty kódu  
  
1. V **nástroje** nabídce vyberte možnost **Správce fragmentů kódů**.  
  
2. V **Správce fragmentů kódů** dialogu **Visual C#** z **jazyk** rozevíracího seznamu.  
  
     A **refaktoringu** složky by se měla zobrazit v seznamu stromu zobrazení složek.  
  
### <a name="to-restore-refactoring-see-comment-in-code-snippet-manager"></a>K obnovení refaktoring viz komentář ve Správci fragmentů kódu  
  
1. Pokud **refaktoringu** složka není se zobrazí v seznamu složek zobrazení stromu Správce fragmentů kódů a pak pomocí tohoto postupu můžete přidat fragmentů kódu refaktoringu zpět do Správce fragmentů kódů.  
  
2. V **nástroje** nabídce vyberte možnost **Správce fragmentů kódů**.  
  
3. V **Správce fragmentů kódů** dialogu **Visual C#** z **jazyk** rozevíracího seznamu.  
  
4. Klikněte na **Přidat**. **Složka fragmentů kódů** zobrazí se dialogové okno, které vám pomůže najít a zadejte adresář, který chcete přidat zpět do Správce fragmentů kódů,.  
  
5. Vyhledejte **refaktoringu** složku, jehož cesta k adresáři je:  
  
     *Instalační adresář*\Microsoft Visual Studio 14.0\VC#\Snippets\\*ID jazyka*\Refactoring  
  
     Skutečné cesty je podobný následujícímu výchozí instalaci:  
  
     C:\Program Files\Microsoft Visual Studio 14.0\VC#\Snippets\1033\Refactoring.  
  
6. Klikněte na tlačítko **otevřít** v **složka fragmentů kódů** dialogové okno a potom klikněte na **OK** ve Správci fragmentů kódu.  
  
## <a name="see-also"></a>Viz také  
 [Fragmenty kódu jazyka Visual C#](../ide/visual-csharp-code-snippets.md)   
 [Refaktoring (C#)](../csharp-ide/refactoring-csharp.md)   
 [Fragmenty kódu](../ide/code-snippets.md)
