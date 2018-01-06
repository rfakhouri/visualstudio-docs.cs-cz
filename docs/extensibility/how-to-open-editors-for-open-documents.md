---
title: "Postupy: otevření editory pro otevřené dokumenty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], opening for open documents
ms.assetid: 1a0fa49c-efa4-4dcc-bdc0-299b7052acdc
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c4c6321644cb59f55ad1335249aec5b071aef4ab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-open-editors-for-open-documents"></a>Postupy: otevření editory pro otevřené dokumenty
Předtím, než na projekt se otevře okno dokument, projekt nejprve musí určit, zda soubor je již otevřete v okně dokumentu pro jiný editor. Soubor může být buď otevřete v editoru specifické pro projekt nebo jeden z standardní editory zaregistrován v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="opening-a-project-specific-editor"></a>Otevření editoru specifické pro projekt  
 Použijte následující postup k otevření editoru projektu specifické pro soubor, který je již otevřeno.  
  
#### <a name="to-open-a-project-specific-editor-for-an-open-file"></a>Otevřete editor projektu specifické pro otevření souboru  
  
1.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> metoda.  
  
     Toto volání vrátí ukazatele do hierarchie, položku hierarchie a rámce okna dokumentu, podle potřeby.  
  
2.  Pokud otevřete dokument, projekt musíte zkontrolovat podívat, jestli existuje pouze datový objekt dokumentu nebo pokud se objekt zobrazení dokumentu nachází také.  
  
    -   Pokud existuje objekt zobrazení dokumentu, a toto zobrazení je pro jiné hierarchie nebo hierarchie položek, projektu používá má ukazatel na rámec okna zobrazení k resurface existující okna.  
  
    -   Pokud existuje objekt zobrazení dokumentu, a toto zobrazení je stejné hierarchie a hierarchie položka, projekt můžete otevřít druhý zobrazení, pokud může připojit k základní datový objekt dokumentu. Jinak projektu, měli používat má ukazatel na rámec okna zobrazení a resurface existující okna.  
  
    -   Pokud dokument datový objekt existuje, pouze projektu měli zjistit, jestli může použít datový objekt dokumentu pro jeho zobrazení. Pokud se objekt dat dokumentu kompatibilní, dokončení kroky popsané v [otevření editoru specifické pro projekt](../extensibility/how-to-open-project-specific-editors.md).  
  
     Pokud dokument datový objekt není kompatibilní, nezobrazí se uživateli, který označuje, že soubor je aktuálně používán k chybě. Tato chyba se má zobrazit v přechodný případech pouze, jako když se kompiluje soubor ve stejnou dobu uživatel se pokusil otevřít soubor pomocí editoru, než [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] základní textový editor. Základní textového editoru můžete sdílet dokumentu datový objekt s překladačem.  
  
3.  Pokud dokument není otevřený, protože neexistuje objekt dat dokumentu nebo objekt zobrazení dokumentu, proveďte kroky v [otevření editoru specifické pro projekt](../extensibility/how-to-open-project-specific-editors.md).  
  
## <a name="opening-a-standard-editor"></a>Otevření editoru Standard  
 Pomocí následujícího postupu otevřete standardní editor pro soubor, který je již otevřete.  
  
#### <a name="to-open-a-standard-editor-for-an-open-file"></a>Chcete-li otevřít standardní editor pro otevření souboru  
  
1.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>.  
  
     Tato metoda nejprve ověří, zda dokument není otevřený voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A>. Pokud dokument je již otevřeno, je resurfaced její okno editoru.  
  
2.  Pokud dokument není otevřený, potom postupujte podle pokynů v [postupy: otevření standardní editory](../extensibility/how-to-open-standard-editors.md).  
  
## <a name="see-also"></a>Viz také  
 [Otevření a uložení položky projektu](../extensibility/internals/opening-and-saving-project-items.md)   
 [Postupy: otevření projektu konkrétní editory](../extensibility/how-to-open-project-specific-editors.md)   
 [Postupy: Otevření standardních editorů](../extensibility/how-to-open-standard-editors.md)