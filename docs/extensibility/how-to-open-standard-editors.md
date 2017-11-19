---
title: "Postupy: otevření standardní editory | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], opening
- projects [Visual Studio SDK], opening standard editors
ms.assetid: d5ce10f9-047a-4b74-aa1d-295128898b89
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bd3e3b8da06e6846c8c6adc6ddc3f65873c1e2bb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-open-standard-editors"></a>Postupy: otevření standardní editory
Když otevřete standardního editoru, umožníte IDE určit standardní editor pro určený typ souboru, místo zadání editor projektu specifické pro soubor.  
  
 Proveďte následující postup k implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> metoda. Otevře se soubor projektu v standardního editoru.  
  
### <a name="to-implement-the-openitem-method-with-a-standard-editor"></a>Implementovat metodu OpenItem s standardního editoru  
  
1.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable> (`RDT_EditLock`) k určení, zda soubor dokumentu data objektu je již otevřen.  
  
2.  Pokud soubor je již spuštěna, resurface soubor voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> metoda, zadáte třeba hodnotu `IDO_ActivateIfOpen` pro `grfIDO` parametr.  
  
     Pokud je otevřený soubor a na jiný projekt než volajícím projekt vlastní dokument, projekt obdrží upozornění, které je editor otevíráte z jiného projektu. Okno souboru je pak prezentované.  
  
3.  Pokud dokument není otevřené nebo není ve spuštěné tabulce dokumentu volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> – metoda (`OSE_ChooseBestStdEditor`) otevřete standardního editoru souboru.  
  
     Při volání metody rozhraní IDE provede následující úlohy:  
  
    1.  Prostředí IDE kontrol editorech / {guidEditorType} / rozšíření podklíč registru k určení které editor můžete otevřít soubor a má nejvyšší prioritu tohoto postupu.  
  
    2.  Po IDE určil, které editor můžete otevřít soubor, zavolá rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>. Editoru implementace této metody vrátí informace, které je požadované pro prostředí IDE volat <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> a lokality nově otevřené dokumentu.  
  
    3.  Nakonec IDE načte dokument pomocí rozhraní obvyklé trvalost <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>.  
  
    4.  Pokud IDE dříve určil, že je k dispozici hierarchie nebo hierarchie položek, zavolá rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.GetItemContext%2A> metoda na projektu získat místní úrovni projektu <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> ukazatel na předat zpět s <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> volání metody.  
  
4.  Vrátí <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> ukazatel na IDE při volání rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.GetItemContext%2A> v projektu, pokud chcete umožnit kontext editor get ze svého projektu.  
  
     Provedením tohoto kroku umožňuje další služby v rámci nabídky projektu do editoru.  
  
     Pokud dokument zobrazení nebo objekt zobrazení dokumentu byl úspěšně umístěný v rámec okna, objekt je inicializován s jeho data voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.LoadDocData%2A>.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [Otevření a uložení položky projektu](../extensibility/internals/opening-and-saving-project-items.md)   
 [Postupy: otevření projektu konkrétní editory](../extensibility/how-to-open-project-specific-editors.md)   
 [Postupy: otevření editory pro otevřené dokumenty](../extensibility/how-to-open-editors-for-open-documents.md)   
 [Zobrazení souborů pomocí příkaz pro otevření souboru](../extensibility/internals/displaying-files-by-using-the-open-file-command.md)