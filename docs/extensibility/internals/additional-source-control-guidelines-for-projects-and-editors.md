---
title: Další zdroje řízení pokyny pro projekty a editory | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], guidelines for projects and editors
ms.assetid: 2483cce5-321c-4d3c-9c5c-ee8385263f74
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e39c8fcc78712f0f8d9b799789751c16f343ada6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129278"
---
# <a name="additional-source-control-guidelines-for-projects-and-editors"></a>Další zdroje řízení pokyny pro projekty a editory
Existuje několik pokyny, které projekty a editory by měl splňovat za účelem podpory správy zdrojového kódu.  
  
## <a name="guidelines"></a>Pokyny  
 Projekt nebo editoru vhodné provést následující pro podporu správy zdrojového kódu:  
  
|Oblast|Projekt|Editor|Podrobnosti|  
|----------|-------------|------------|-------------|  
|Privátní kopie souborů|X||Prostředí podporuje privátní kopie souborů. To znamená že každá osoba zařazen do projektu má jejich vlastní privátní kopírování souborů v tomto projektu.|  
|Trvalost ANSI nebo Unicode|X|X|Pokud napíšete kód trvalost, zachovat soubory ve formátu ANSI, protože většina zdrojové programy řízení aktuálně nepodporují kódování Unicode.|  
|Vytvoření výčtu souborů|X||Projekt musí obsahovat konkrétní seznam všech souborů v něm a musí být schopen vytvořit výčet seznamu souborů pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> (VSH_PROPID_First_Child/Next_Sibling). Projekt by měl vystavit také názvy položek prostřednictvím jeho <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.GetMkDocument%2A> implementaci a podporu vyhledávání názvu (včetně speciálních soubory) prostřednictvím jeho <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.IsDocumentInProject%2A> implementace.|  
|Textovém formátu|X|X|Pokud je to možné, soubory by měly být ve formátu textu na podporu sloučení různé verze. Soubory, které nejsou v textovém formátu nejde sloučit s jiné verze souboru později. Je upřednostňovaný textovém formátu XML.|  
|Na základě referenční dokumentace|X||Referenční dokumentace založené na projekty jsou snadno podporované ve správě zdrojového kódu. Ale na základě directory projekty jsou podporovány také ovládacím prvkem zdroje tak dlouho, dokud projektu můžete vytvořit seznam jeho soubory na vyžádání, bez ohledu na to, jestli existují tyto soubory na disku. Při otevření projektu od správy zdrojového kódu, se soubor projektu přenesou nejprve před všechny jeho soubory.|  
|Uchování objektů a vlastností v předvídatelný pořadí|X|X|Zachovat vaše soubory v předvídatelný pořadí, jako je například abecedně, aby se usnadnilo sloučení.|  
|Znovu načíst|X|X|Když se změní soubor na disku, musí být možné ji znovu načíst vaše editor. Při účasti ve správě zdrojového kódu v prostředí dojde k opětovnému načtení dat pro vás voláním vašeho <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> implementace. Nejobtížnější případ opětovného načtení je, když najdete v článku věnovaném nastane, když máte názvem IVsQueryEditQuerySave::<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> a jsou zpracování informací. Kódu opětovného načtení ale musí být možné spouštět v této situaci.<br /><br /> Prostředí automaticky znovu načte soubory projektu. Však musí implementovat projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2> Pokud má vnořené hierarchie za účelem podpory opětovném načtení vnořené soubory projektu.|  
  
## <a name="see-also"></a>Viz také  
 [Podpora správy zdrojového kódu](../../extensibility/internals/supporting-source-control.md)