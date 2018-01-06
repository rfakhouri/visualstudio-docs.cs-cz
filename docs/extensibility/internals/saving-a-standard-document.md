---
title: "Uložení dokumentu standardu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], saving standard documents
- projects [Visual Studio SDK], saving standard documents
- persistence, saving standard documents
ms.assetid: d692fedf-b46e-4d60-84bd-578635042235
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0cdfb4631420f6803e6434bd67b93bd713cfd1f7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="saving-a-standard-document"></a>Ukládání standardní dokumentu
Prostředí zajišťuje uložit, uložit jako a uložte všechny příkazy. Když uživatel vybere **Uložit**, **uložit jako**, nebo **Uložit vše** z **soubor** nabídky nebo ukončí řešení, což vede k  **Uložte všechny**, se spustí následující proces.  
  
 ![Standard Editor](../../extensibility/internals/media/public.gif "veřejné")  
Uložit, uložit jako a Uložit vše příkaz zpracování standardního editoru  
  
 Tento proces je podrobně popsaná v následující kroky:  
  
1.  Když **Uložit** a **uložit jako** příkazy jsou vybrané, používá prostředí <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> služby k určení aktivního okna dokumentu, a proto co položky by měly být uloženy. Jakmile se označuje aktivního okna dokumentu, prostředí vyhledá ukazatel hierarchie a identifikátor položky (itemID) pro dokument ve spuštěné tabulce dokumentu. Další informace najdete v tématu [systémem dokumentu tabulky](../../extensibility/internals/running-document-table.md).  
  
     Když **Uložit vše** příkaz je vybraná, prostředí používá informace ve spuštěné tabulce dokumentu zkompilovat seznam všech položek uložit.  
  
2.  Při řešení obdrží <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> volání, která ji provádí iteraci sadu vybrané položky (tedy více výběrů, které jsou zveřejněné <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> služby).  
  
3.  Na každou položku ve výběru řešení používá hierarchie ukazatele k volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IsItemDirty%2A> metoda k určení zda **Uložit** příkazu nabídky by měla být povolená. Pokud jeden nebo více položek jsou chybná, pak se **Uložit** příkaz je povolen. Pokud v hierarchii používá standardní editor, pak hierarchie delegáty dotazování nesprávné stav do editoru voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.IsDocDataDirty%2A> metoda.  
  
4.  Na všech vybraných položek je nekonzistentní, toto řešení využívá hierarchie ukazatele k volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> metodu na příslušné hierarchií.  
  
     Je běžné pro hierarchii použití standardního editoru k provádění úprav. V takovém případě data dokumentu objektu pro tuto editoru by měly podporovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> rozhraní. Po přijetí <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> volání metody projektu informovat editor, který dokument se ukládá voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.SaveDocData%2A> metodu na datový objekt dokumentu. Editor můžete povolit prostředí pro zpracování **uložit jako** dialogové okno, voláním `Query Service` pro <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> rozhraní. Tento příkaz vrátí ukazatel <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> rozhraní. Pak musí volat editoru <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A> metodu předáním ukazatel na editor <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> implementace prostřednictvím `pPersistFile` parametr. Pak provede operaci uložit a poskytuje prostředí **uložit jako** dialogové okno pro editor. Prostředí poté zavolá zpátky do editoru s <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>.  
  
5.  Pokud se uživatel pokouší uložte dokument bez názvu (to znamená, dříve neuloženého dokumentu), příkazu Uložit jako ve skutečnosti provedena.  
  
6.  Pro příkaz Uložit jako prostředí zobrazí dialogové okno Uložit jako, do výzvy pro uživatele k zadání názvu souboru.  
  
     Pokud došlo ke změně názvu souboru, pak hierarchii zodpovídá za informací z aktualizace dokumentu rámečku mezipaměti voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetProperty%2A>(VSFPROPID_MkDocument).  
  
 Pokud **uložit jako** příkaz přesune umístění dokumentu a hierarchii je citlivá na umístění dokumentu, pak v hierarchii je zodpovědná za předání vlastnictví okno otevřít dokument do jiné hierarchie. Například k tomu dojde, pokud projekt sleduje, zda soubor je interní nebo externí soubor aplikace (různé) ve vztahu k projektu. Následujícím postupem změnit vlastnictví souboru na různé soubory projektu.  
  
## <a name="changing-file-ownership"></a>Změna vlastnictví souboru  
  
#### <a name="to-change-file-ownership-to-the-miscellaneous-files-project"></a>Chcete-li změnit vlastnictví souboru do projektu ostatní soubory  
  
1.  Služba pro dotaz <xref:Microsoft.VisualStudio.Shell.Interop.SVsExternalFilesManager> rozhraní.  
  
     Ukazatel na <xref:Microsoft.VisualStudio.Shell.Interop.IVsExternalFilesManager2> je vrácen.  
  
2.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsExternalFilesManager2.TransferDocument%2A> (`pszMkDocumentNew`, `punkWindowFrame`) způsob přenosu dokumentu do nové hierarchie. Provedení příkazu Uložit jako hierarchii volá tuto metodu.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [Otevření a uložení položek projektu](../../extensibility/internals/opening-and-saving-project-items.md)