---
title: 'Postupy: podpora osnovy ve službě starší verze jazyka | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], collapse to definitions command
- language services, supporting Collapse to Definitions command
- hidden text, Collapse to Definitions command
ms.assetid: bb6e74c3-93e4-4ef7-afc7-1c9b342f083b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f9880c5c255118478d15f34f9a9245a1c25d97fd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31130242"
---
# <a name="how-to-support-outlining-in-a-legacy-language-service"></a>Postupy: podpora osnovy ve službě starší verze jazyka
Osnova se používá k rozbalit nebo sbalit různých oblastech textu. Osnova způsobem je použít určeny jinak různé jazyky. Další informace najdete v tématu [Osnova](../../ide/outlining.md).  
  
 Starší verze jazyka služby jsou implementovány jako součást VSPackage, ale novější způsob implementace funkce služby jazyk je použití MEF rozšíření. Další informace o nový způsob implementace osnovy, najdete v tématu [návod: vytvoření přehledu](../../extensibility/walkthrough-outlining.md).  
  
> [!NOTE]
>  Doporučujeme vám, že začnete používat co nejdříve editoru nové rozhraní API. Tím zvýšit výkon služby jazyk a umožňují využívat výhod nových funkcí editoru.  
  
 Následující ukazuje, jak pro podporu tohoto příkazu pro vaši službu jazyka.  
  
### <a name="to-support-outlining"></a>Pro podporu osnovy  
  
1.  Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage> na jazyk objektu služby.  
  
2.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> na aktuální objekt popisující relace pro přidání nových outline oblastí.  
  
## <a name="robust-programming"></a>Robustní programování  
 Když uživatel vybere **sbalit do definice** na **Osnova** nabídky, volání IDE <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage.CollapseToDefinitions%2A> na vaše služba jazyka.  
  
 Když tato metoda je volána, rozhraní IDE předá v <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> ukazatele (ukazatel na textovou vyrovnávací paměť) a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession> (ukazatel s aktuální relací osnovy).  
  
 Můžete volat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> metodu pro více oblastí outline zadáním těchto oblastí v `rgOutlnReg` parametr. `rgOutlnReg` Parametr <xref:Microsoft.VisualStudio.TextManager.Interop.NewOutlineRegion> struktury. Tento proces vám umožňují určit různé vlastnosti Skrytá oblast, například jestli je konkrétní oblasti rozbalit nebo sbalit.  
  
> [!NOTE]
>  Dávejte pozor, o skrývání znaky nového řádku. Skrytý text by měl rozšířit od začátku první řádek na poslední znak poslední řádek v části, a poslední znak nového řádku viditelné.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: podporují skrytého textu ve službě jazyk starší verze](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)   
 [Postupy: Rozšířená podpora osnovy ve službě starší verze jazyka](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)