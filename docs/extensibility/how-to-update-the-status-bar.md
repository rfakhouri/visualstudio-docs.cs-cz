---
title: 'Postupy: aktualizace stavového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - update status bar
ms.assetid: 7500c8a7-4913-4818-a88b-bfd1b9887cb6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1b5f7e6849736f0fc226c51f69a1526aca8e971a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134493"
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