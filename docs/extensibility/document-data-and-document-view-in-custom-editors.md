---
title: "Data dokumentu a dokument zobrazit vlastní editorů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], custom - document data and document view
ms.assetid: 71eea623-f566-4feb-84cd-ca1ba71bc493
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7c7e24ed2db4538ab0fd38dbb85930452611f0ee
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="document-data-and-document-view-in-custom-editors"></a>Data dokumentu a zobrazení dokumentu vlastní editorů
Vlastní editor se skládá ze dvou částí: objekt dat dokumentu a objekt zobrazení dokumentu. Jako názvy naznačují, dokumentu datový objekt představuje textových dat, který se má zobrazit, a objekt zobrazení dokumentu (nebo "Zobrazit") představuje jeden nebo více windows, ve kterém chcete zobrazit data objektu dokumentu.  
  
## <a name="document-data-object"></a>Datový objekt dokumentu  
 Datový objekt dokumentu je znázornění dat textu v textová vyrovnávací paměť. Je objekt COM, který ukládá text dokumentu a další informace, zpracovává trvalost dokumentu a umožňuje více zobrazení jeho data. Další informace naleznete v tématu  
  
 <xref:EnvDTE80.Window2.DocumentData%2A>a [dokumentu Windows](../extensibility/internals/document-windows.md).  
  
 Vlastní editory a návrhářů, se můžete rozhodnout pro použití <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objekt nebo vlastní vlastní vyrovnávací paměti. <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>Následuje zjednodušené vnoření modelu pro standardní editor, podporuje více zobrazení a poskytuje rozhraní událostí, které se používají ke správě více zobrazení.  
  
## <a name="document-view-object"></a>Objekt zobrazení dokumentu  
 Okno, které zobrazí kódu a další text se označuje jako dokument zobrazení nebo zobrazení. Když vytvoříte editoru, můžete jednoho zobrazení, ve kterém text se zobrazuje v okně jednoho nebo více zobrazení, ve kterém se zobrazí text ve více než jeden interval. Výběr závisí na vaší aplikace. Například pokud potřebujete úpravy vedle sebe, vyberte více zobrazení. Každé zobrazení je přidružená položce v integrovaném vývojovém prostředí na (IDE) spuštěna dokumentu tabulky (r...). Zobrazení windows patří do projektu nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objektu.  
  
 Pokud vaše editor podporuje více zobrazení dokumentu datový objekt, pak dokument data a objekty zobrazení dokumentu musí být samostatné. Jinak že je možné seskupit. Další informace najdete v tématu [podpora více zobrazení dokumentu](../extensibility/supporting-multiple-document-views.md).  
  
 Prostředí IDE upozorní zobrazení o událostech (například při zavření řešení obsahující dokumentu) pomocí odpovídajících identifikátor položky (ItemID) pro každou položku ve spuštěné tabulce dokumentu. Další informace najdete v tématu [systémem dokumentu tabulky](../extensibility/internals/running-document-table.md).  
  
 Existují dvě možnosti pro vytvoření zobrazení pro vlastní editor. Jeden je model aktivace na místě, je hostitelem zobrazení v okně pomocí ovládacího prvku ActiveX nebo datový objekt dokumentu. Druhá je zjednodušené vnoření modelu, kde je hostován zobrazení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> je implementována pro zpracování příkazy okna. Informace týkající se aktivace na místě modelu najdete v tématu [aktivace na místě](../extensibility/in-place-activation.md). Informace o modelu zjednodušené vnoření najdete v tématu [zjednodušené vložení](../extensibility/simplified-embedding.md).  
  
## <a name="see-also"></a>Viz také  
 [Podpora více zobrazení dokumentu](../extensibility/supporting-multiple-document-views.md)   
 [Zjednodušená vložení](../extensibility/simplified-embedding.md)   
 [Postupy: zobrazení dokumentů datové připojení](../extensibility/how-to-attach-views-to-document-data.md)   
 [Správa vlastníka zámku dokumentu](../extensibility/document-lock-holder-management.md)   
 [Zobrazení jeden a více karta](../extensibility/single-and-multi-tab-views.md)   
 [Ukládání standardní dokumentu](../extensibility/internals/saving-a-standard-document.md)   
 [Trvalosti a tabulce dokument spuštěná](../extensibility/internals/persistence-and-the-running-document-table.md)   
 [Určení Editor otevře soubor v projektu](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)   
 [Objekty Factory editoru](../extensibility/editor-factories.md)