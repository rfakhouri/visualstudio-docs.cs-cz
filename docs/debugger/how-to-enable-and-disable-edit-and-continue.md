---
title: "Postupy: povolení a zakázání upravit a pokračovat (C#, VB, C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- Apply Code Changes command
- Edit and Continue, disabling
- code changes, applying in break mode
- INCREMENTAL linker option
- Edit and Continue, enabling
- break mode, applying code changes
- Edit and Continue, applying code changes
- Step command
- Go command
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
caps.latest.revision: "26"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 724851fcd78050d3502cdec4369c7c6a79c9419f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-enable-and-disable-edit-and-continue-c-vb-c"></a>Postupy: povolení a zakázání upravit a pokračovat (C#, VB, C++)
Můžete zakázat nebo povolit upravit a pokračovat v **možnosti** dialogové okno v době návrhu. Nelze změnit, tato nastavení při ladění.  
  
Upravit a pokračovat funguje pouze v sestavení pro ladění. Nativní C++, upravit a pokračovat, vyžaduje použití / incremental – možnost. Další informace o požadavcích na funkci v jazyce C++ najdete [příspěvku na blogu](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/) a [upravit a pokračovat (Visual C++)](../debugger/edit-and-continue-visual-cpp.md).
  
#### <a name="to-enabledisable-edit-and-continue"></a>Povolení a zakázání upravit a pokračovat  
  
1.  Pokud jste v relaci ladění, zastavte ladění (**Shift + F5**).

2.  Otevřete stránku ladění možnosti (**nástroje > Možnosti > ladění**).
  
3.  Vyberte **Obecné**a přejděte dolů k položce **upravit a pokračovat** kategorie (pravé podokno).  
  
4.  Chcete-li povolit, vyberte **povolit upravit a pokračovat** zaškrtávací políčko. Chcete-li zakázat, zrušte zaškrtnutí políčka.  
  
    > [!NOTE]
    >  Pokud je povolená IntelliTrace a shromažďovat události IntelliTrace a informací o voláních, upravit a pokračovat, je zakázané. Další informace najdete v tématu [IntelliTrace](../debugger/intellitrace.md).

5. (C++) Chcete-li povolit, vyberte **Povolit nativní upravit a pokračovat**. Chcete-li zakázat, zrušte zaškrtnutí políčka.

6. (C++) Nastavte další možnosti pro nativní kód.

    - **Změny na pokračovat (pouze Native)**  
        Visual Studio automaticky zkompiluje a platí všechny zbývající kód změny, které jste provedli při pokračování procesu ze stavu pozastavení. Pokud není vybrána, můžete použít změny pomocí "Použít změny kódu" položky v nabídce ladění.  
  
    - **Upozornění na starý kód (jenom Native)**  
        Získáte upozornění na starý kód. 
  
7.  Click **OK**.    
  
## <a name="see-also"></a>Viz také  
 [Upravit a pokračovat](../debugger/edit-and-continue.md)