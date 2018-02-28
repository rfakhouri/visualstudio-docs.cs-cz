---
title: "Podpora více zobrazení dokumentu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], custom - multiple document views
ms.assetid: c7ec2366-91c4-477f-908d-e89068bdb3e3
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4efd76830356996bdf75c923f457d19d2381763c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="supporting-multiple-document-views"></a>Podpora více zobrazení dokumentu
Můžete zadat více než jedno zobrazení dokumentu tak, že vytvoříte samostatné dokumentu data a objekty zobrazení dokumentu pro vaše editor. Jsou některé případy, ve kterých by být užitečné zobrazení dalších dokumentu:  
  
-   Nová podpora okno: vaše editor, který poskytuje dvě nebo více zobrazení stejného typu, chcete, aby uživatel, který již má okno otevře v editoru můžete výběrem otevřete nové okno **nové okno** příkaz **okno** nabídky.  
  
-   Formuláře a kódu zobrazit podporu: Chcete, aby vaše editor, který poskytuje různé typy zobrazení. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], například poskytuje zobrazení formuláře a zobrazení kódu.  
  
 Další informace o tom najdete v postupu CreateEditorInstance v souboru EditorFactory.cs v projektu vlastního editoru vytvořených šablonou balíček Visual Studio. Další informace o tomto projektu najdete v tématu [návod: vytvoření vlastního editoru](../extensibility/walkthrough-creating-a-custom-editor.md).  
  
## <a name="synchronizing-views"></a>Probíhá synchronizace zobrazení.  
 Pokud implementujete více zobrazení, je datový objekt dokumentu odpovídá za pořízení všechna zobrazení synchronizována s daty. Můžete použít zpracování rozhraní na událostí <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> synchronizovat více zobrazení s daty.  
  
 Pokud použijete <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objekt, který chcete synchronizovat více zobrazení, pak musí implementovat vlastní událostí systému a zpracovat změny provedené v dokumentu datový objekt. Chcete-li zachovat aktuální více zobrazení můžete různou úrovní členitosti. S nastavením maximální členitosti, jako typ v jednom zobrazení ostatní zobrazení se aktualizují okamžitě. S minimální rozlišením nejsou aktualizovány ostatních zobrazení, dokud se aktivují.  
  
## <a name="determining-whether-document-data-is-already-open"></a>Určení, zda dokument dat je již otevřený  
 Integrované vývojové prostředí (IDE) spuštěné dokumentu tabulce (r...) pomáhá sleduje, zda data pro dokument je již otevřeno, jak je znázorněno v následujícím diagramu.  
  
 ![DocDataView – grafika](../extensibility/media/docdataview.gif "DocDataView –")  
Více zobrazení  
  
 Ve výchozím nastavení, jednotlivých zobrazení (objekt zobrazení dokumentu) je součástí vlastního rámce okna (<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame>). Jak je již uvedeno ale data dokumentu lze zobrazit více zobrazení. Chcete-li povolit, Visual Studio kontroluje r... k určení, zda v dokumentu je již otevřen v editoru. Při volání rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> vytvořit editoru, vrátí hodnotu než NULL v `punkDocDataExisting` parametr označuje, že dokument je již otevřen v jiném editoru. Další informace o tom, najdete v části funkce r... [systémem dokumentu tabulky](../extensibility/internals/running-document-table.md).  
  
 Ve vaší <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> implementace, zkontrolujte dokumentu datový objekt vrácený v `punkDocDataExisting` k určení, zda je vhodné pro vaše editor data dokumentu. (Například pouze data HTML mají být zobrazeny HTML editor.) Pokud je vhodné, pak vaše objekt factory editoru by měl poskytovat druhý zobrazení pro data. Pokud `punkDocDataExisting` parametr není `NULL`, je možné buď že datový objekt dokumentu je otevřený v jiném editoru, nebo, pravděpodobnější, data dokumentu je již otevřen v jiné zobrazení se stejnou editoru. Pokud jsou data dokument otevřít v jiný editor, který nepodporuje vaše objekt factory editoru, Visual Studio selže otevřete váš objekt factory editoru. Další informace najdete v tématu [postupy: zobrazení připojit k datům dokumentu](../extensibility/how-to-attach-views-to-document-data.md).