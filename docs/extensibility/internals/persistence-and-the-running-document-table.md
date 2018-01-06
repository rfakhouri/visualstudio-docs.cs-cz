---
title: "Trvalost a spuštění dokumentu tabulky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- persistence, managing
- IVsPersistHierarchyItem interface, implementing
- architecture, persistence
- running document table (RDT), architecture
ms.assetid: 27117eae-6c58-4189-a61a-1397a43b5ecf
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7f48a1acdad3856e7334ce6a86b48e67c880f9c1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="persistence-and-the-running-document-table"></a>Trvalosti a tabulce dokument spuštěná
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE, projekty jsou zcela zodpovědní za správu trvalost jejich položky projektu, které se toho dosáhnout pomocí služby, <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>. Dokumenty jsou základní jednotkou trvalost v prostředí Visual Studio. Projekty koordinovat otevření, uložení a přejmenování dokumentů s spuštěné tabulce dokumentu r. (..), na prostředek, který sleduje stav všechny otevřené dokumenty.  
  
## <a name="managing-persistence"></a>Správa trvalost  
 Projekty řídit v prostředí trvalost služby pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem> rozhraní. Když prostředí nikdy přímo požádá dokumentu trvání, požádá vlastnícím projektu (nebo hierarchie) k uložení dokumentu. To umožňuje projekt, který má-li uložit data položky projektu do místních souborů, vzdálené soubory, databáze, úložiště nebo jiné médium.  
  
 Globální prostředí udržuje r.... Prostředí udržuje položky pro všechna otevřená okna a dokumenty v r..., která vám umožní, aby přijímat speciální oznámení, například při uzavření řešení. Kromě toho r... umožňuje sledovat jejich odpovídajících uzlů v prostředí **Průzkumníku řešení**. R... udržuje jeden záznam za otevřený, trvalá objektu, včetně souborů projektu a položek projektů dokumenty.  
  
## <a name="see-also"></a>Viz také  
 [Spuštěné tabulce dokumentu](../../extensibility/internals/running-document-table.md)   
 [Výběr a měna v prostředí IDE](../../extensibility/internals/selection-and-currency-in-the-ide.md)