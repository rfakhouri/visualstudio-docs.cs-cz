---
title: 'Postupy: Aktualizace stavového řádku | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - update status bar
ms.assetid: 7500c8a7-4913-4818-a88b-bfd1b9887cb6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 49661e379c81bac935e2d2ae2279e32d548eb698
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54929871"
---
# <a name="how-to-update-the-status-bar"></a>Postupy: Aktualizace stavového řádku
**Stavový řádek** se ovládací panel nachází v dolní části mnoho aplikace pro windows, který obsahuje jeden nebo více řádků textu stavu nebo ukazatele.  
  
## <a name="to-update-the-status-bar"></a>Aktualizace stavového řádku  
  
1.  Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> na každém objektu jednotlivých zobrazení (DocView), která poskytuje editoru, jako je například zobrazení formuláře a zobrazení kódu.  
  
2.  Když se volá rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>, aktualizovat informace v **stavový řádek** voláním metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>.  
  
    > [!NOTE]
    >  Volání rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> pouze když vaše okno dokumentu prvotní aktivaci. Pro zbývající čas, který je aktivní okno dokumentu, je nutné aktualizovat **stavový řádek** informací jako stav editoru změny.  
  
## <a name="robust-programming"></a>Robustní programování  
 A **stavový řádek** obsahuje čtyři samostatné pole:  
  
- Stavový text  
  
- Indikátor průběhu  
  
- Animovaný ikonu  
  
- Editor informací  
  
  Další informace najdete v tématu [stavové řádky](/cpp/mfc/status-bars).  
  
  Rozhraní IDE automaticky volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> metodu vaše <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> implementace při aktivaci okno dokumentu.  
  
  Implementátor VSPackage je zodpovědný za automatickou aktualizaci stavový text ve stavovém řádku. Rozhraní IDE obnoví tento řetězec na hodnotu "PŘIPRAVENO" Pokud textové pole Stav je nastaven na prázdný text ("") v době nečinnosti.  
  
## <a name="see-also"></a>Viz také:  
 [Stavové řádky](/cpp/mfc/status-bars)