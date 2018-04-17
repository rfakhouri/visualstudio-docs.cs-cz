---
title: Určení, které Editor otevře soubor v projektu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], determining which editor opens a file
- projects [Visual Studio SDK], determining which editor opens file
- project types, determining which editor opens a file
- persistence, determining which editor opens a file
ms.assetid: acbcf4d8-a53a-4727-9043-696a47369479
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d8fe054fa8e630b2f6c54cb78ef75b6c10ff74d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="determining-which-editor-opens-a-file-in-a-project"></a>Určení Editor otevře soubor v projektu
Když uživatel otevře soubor v projektu, prostředí projde procesu dotazování, nakonec otevřete editor odpovídající nebo návrháře pro tento soubor. Počáteční postup zaměstnaní prostředí je stejný pro standardní a vlastní editory. Prostředí používá celou řadu kritéria při dotazování které editoru otevřete soubor a VSPackage musí koordinaci s prostředím během tohoto procesu.  
  
 Když uživatel například vybere **otevřete** příkaz **soubor** nabídce a potom vybere `filename`.rtf (nebo jakýkoli jiný soubor s příponou .rtf), volání prostředí <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> implementace pro každý projekt, nakonec prosté prostřednictvím všechny instance projektu v řešení. Projekty vrátit sadu příznaky, které identifikují deklarace identity na dokument podle priority. Použití nejvyšší prioritou, prostředí volání odpovídající <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> metoda. Další informace o procesu dotazování [přidání projektů a šablon položek projektu](../../extensibility/internals/adding-project-and-project-item-templates.md).  
  
 Ostatní soubory projektu deklarací všechny soubory, které nejsou vyžádal další projekty. Tímto způsobem vlastní editory můžete otevřít dokumenty, než je standardní editory otevřít. Pokud různé soubory projektu deklarací soubor, zavolá prostředí <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> metoda se standardního editoru otevřete soubor. Prostředí kontroluje svůj vnitřní seznam registrovaných editory pro jednu, která zpracovává soubory .rtf. Tento seznam je umístěn v registru v následujícím klíči:  
  
 [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\\<`version`> \Editors\\{<`editor factory guid`>} \Extensions]  
  
 Prostředí také zkontroluje identifikátory v klíči HKEY_CLASSES_ROOT\CLSID pro všechny objekty, které mají dílčí klíče DocObject třídy. Pokud přípona souboru je zde nalezen, embedded verzi aplikace, jako je například Microsoft Word, vytvoří se v místě v sadě Visual Studio. Tyto objekty dokumentu musí být složené soubory, které implementují <xref:Microsoft.VisualStudio.OLE.Interop.IPersistStorage> musí implementovat rozhraní, nebo objekt <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> rozhraní.  
  
 Pokud neexistuje žádný objekt factory editoru pro soubory .rtf v registru, pak prostředí hledá v HKEY_CLASSES_ROOT \\.rtf klíč a otevře editor zadané existuje. Pokud přípona souboru nebyla nalezena v HKEY_CLASSES_ROOT, prostředí používá Visual Studio základní textového editoru otevřete soubor, pokud je textový soubor.  
  
 Pokud selže základní textový editor, který nastane, že pokud soubor není textový soubor, pak prostředí používá jeho binární editor pro soubor.  
  
 Pokud prostředí najít editor pro rozšíření .rtf v jeho registru, načte VSPackage, který implementuje tento objekt factory editoru. Volání prostředí <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> metodu na nové VSPackage. Volání VSPackage `QueryService` pro `SID_SVsRegistorEditor`pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors.RegisterEditor%2A> metody pro registraci objekt factory editoru s prostředím.  
  
 Prostředí nyní znovu ověří jeho vnitřní seznam registrovaných editory najít objekt factory editoru nově zaregistrovaný pro soubory .rtf. Prostředí volá vaši implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metody předávání v souboru názvu a zobrazit typ k vytvoření.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>   
 <xref:Microsoft.VisualStudio.OLE.Interop.IPersistStorage>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>