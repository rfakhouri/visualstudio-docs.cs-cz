---
title: Projekt s prioritou | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: projects [Visual Studio SDK], opening items
ms.assetid: 9f707592-2fb6-4f75-9269-f6d4700a998e
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 51ed8cd351a306c3992b4b6c9fcc2231a90085f3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="project-priority"></a>Priorita projektu
Položka projektu obvykle je členem jenom jedné projekt v řešení. Proto IDE může snadno zjistit projektu, který se používá k otevření položky. Ale pokud je určitá položka členem více než jeden projekt, rozhraní IDE používá schéma s prioritou určit nejlepší projekt pro otevření položky.  
  
 Následující seznam obsahuje schéma s prioritou projektu:  
  
-   Volání IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2.IsDocumentInProject%2A> metodu pro každý projekt v řešení k určení, zda dokument je členem tohoto projektu.  
  
-   Pokud dokument je členem skupiny projektu, projektu odpovídá s prioritou, projekt přiřadí podle jeho zpracování tohoto dokumentu. Například jazyk projektu odpovídá s vysokou prioritou pro svůj jazyk zdrojové soubory, ale reaguje s nižší prioritou pro typ souboru nebyl rozpoznán, který se nepoužívá jako součást procesu jeho sestavení.  
  
-   Projekty, které poskytují vlastní, specifické pro projekt editory nebo programy Designer pro dokument zobrazit i s vysokou prioritou.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> Výčtu poskytuje dokumentu hodnoty priority.  
  
-   Projekt, který určuje nejvyšší prioritou dostane kontext o otevření dokumentu. Pokud dva projekty návratové hodnoty stejnou prioritu, aktivní projekt je upřednostňovaný. Pokud žádný projekt v řešení odpoví, že můžou otevřít dokument, rozhraní IDE převádí dokumentu na různé soubory projektu. Další informace najdete v tématu [různé soubory projektu](../../extensibility/internals/miscellaneous-files-project.md).  
  
## <a name="see-also"></a>Viz také  
 [Ostatní soubory projektu](../../extensibility/internals/miscellaneous-files-project.md)   
 [Postupy: otevření editory pro otevřené dokumenty](../../extensibility/how-to-open-editors-for-open-documents.md)   
 [Přidání projektů a šablon položek projektu](../../extensibility/internals/adding-project-and-project-item-templates.md)