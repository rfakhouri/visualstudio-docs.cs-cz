---
title: "Postupy: aktualizace stavového řádku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - update status bar
ms.assetid: 7500c8a7-4913-4818-a88b-bfd1b9887cb6
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 76801810aafa3bd4048776ca38385ad1cf508d94
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-update-the-status-bar"></a>Postupy: aktualizace stavového řádku
**Stavový řádek** je umístěný ovládací prvek panelu v dolní části mnoho aplikací systému windows, který obsahuje jeden nebo více řádků textu stavu nebo indikátory.  
  
### <a name="to-update-the-status-bar"></a>Aktualizace stavového řádku  
  
1.  Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> na každém objektu jednotlivých zobrazení (DocView), poskytující svém editoru, například zobrazení formuláře a zobrazení kódu.  
  
2.  Při volání rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>, aktualizovat informace v **stavový řádek** voláním metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>.  
  
    > [!NOTE]
    >  Volání IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> pouze když okně dokumentu prvotní aktivaci. Pro zbývající doba, kterou vaše okna dokumentu je aktivní, musíte aktualizovat **stavového řádku** informace o stavu změny editor.  
  
## <a name="robust-programming"></a>Robustní programování  
 A **stavový řádek** obsahuje čtyři samostatné pole:  
  
-   Stav textu  
  
-   Indikátor průběhu  
  
-   Animovaný ikonu  
  
-   Editor informací  
  
 Další informace najdete v tématu [stavové řádky](/cpp/mfc/status-bars).  
  
 Prostředí IDE automaticky zavolá <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> metodu vaší <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> implementace, když je aktivován vaší okna dokumentu.  
  
 Implementátor VSPackage zodpovídá za aktualizace stavu textu ve stavovém řádku. Prostředí IDE resetuje tento řetězec "Připravené", pokud stav textové pole je nastaven na prázdný text ("") v době nečinnosti.  
  
## <a name="see-also"></a>Viz také  
 [Stavové řádky](/cpp/mfc/status-bars)