---
title: "Ukládání vlastní dokumentu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- persistence, saving custom documents
- projects [Visual Studio SDK], saving custom documents
- editors [Visual Studio SDK], saving custom documents
ms.assetid: 040b36d6-1f0a-4579-971c-40fbb46ade1d
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2b19c6ba222644bc9d5fb97874f50bf6a6aa59d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="saving-a-custom-document"></a>Ukládání vlastní šablony dokumentů
Obslužné rutiny prostředí **Uložit**, **uložit jako**, a **Uložit vše** příkazy. Když uživatel klikne **Uložit**, **uložit jako**, **nebo uložit všechny** na **souboru** nabídky nebo ukončí řešení, což vede Uložit vše, následující Spustí se proces.  
  
 ![Editor zákazníka Uložit](../../extensibility/internals/media/private.gif "privátní")  
Uložit, uložit jako a Uložit vše příkaz pro vlastní editor zpracování  
  
 Tento proces je podrobně popsaná v následující kroky:  
  
1.  Pro **Uložit** a **uložit jako** příkazy, používá prostředí <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> služby k určení aktivního okna dokumentu, a proto co položky by měly být uloženy. Jakmile se označuje aktivního okna dokumentu, prostředí vyhledá ukazatel hierarchie a identifikátor položky (itemID) pro dokument ve spuštěné tabulce dokumentu. Další informace najdete v tématu [systémem dokumentu tabulky](../../extensibility/internals/running-document-table.md).  
  
     Pro příkaz Uložit vše prostředí používá informace ve spuštěné tabulce dokumentu zkompilovat seznam všech položek uložit.  
  
2.  Při řešení obdrží <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> volání, která ji provádí iteraci sadu vybrané položky (tedy více výběrů, které jsou zveřejněné <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> služby).  
  
3.  U každé položky ve výběru řešení používá hierarchie ukazatele k volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IsItemDirty%2A> metoda k určení, zda se má povolit příkaz nabídky Uložit. Pokud jeden nebo více položek jsou chybná, je povoleno příkaz Uložit. Pokud v hierarchii používá standardní editor, pak hierarchie delegáty dotazování nesprávné stav do editoru voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.IsDocDataDirty%2A> metoda.  
  
4.  Na všech vybraných položek je nekonzistentní, toto řešení využívá hierarchie ukazatele k volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> metodu na příslušné hierarchií.  
  
     V případě vlastního editoru komunikace mezi datový objekt dokumentu a projekt je soukromé. Proto žádné zvláštní trvalost otázky jsou zpracovávány mezi tyto dva objekty.  
  
    > [!NOTE]
    >  Pokud budete implementovat vlastní trvalost, je nutné volat <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A> metoda šetří čas. Tato metoda prověří, abyste měli jistotu, že je bezpečné k uložení souboru (například soubor není jen pro čtení).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [Otevření a uložení položek projektu](../../extensibility/internals/opening-and-saving-project-items.md)