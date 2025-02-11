---
title: 'Postupy: Podpora osnovy ve službě starší verze jazyka | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], collapse to definitions command
- language services, supporting Collapse to Definitions command
- hidden text, Collapse to Definitions command
ms.assetid: bb6e74c3-93e4-4ef7-afc7-1c9b342f083b
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d92baa824dbb70dd591cadef99775f943c651aef
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63436147"
---
# <a name="how-to-support-outlining-in-a-legacy-language-service"></a>Postupy: Podpora osnovy ve službě starší verze jazyka
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Sbalení se používá k rozbalit nebo sbalit různé oblasti textu. Sbalování stejně, jako se používá mohou být definovány rozdílně v různých jazycích. Další informace najdete v tématu [Osnova](../../ide/outlining.md).  
  
 Služby starší verze jazyka jsou implementovány jako součást sady VSPackage, ale novější způsob implementace funkce služba jazyka je pro použití rozšíření MEF. Další informace o nový způsob implementace sbalování najdete v tématu [názorný postup: Sbalování](../../extensibility/walkthrough-outlining.md).  
  
> [!NOTE]
> Doporučujeme vám, že začnete používat nový editor API co nejdříve. Tím vylepšíme výkonu vaší služby jazyka a umožňují využívat nové funkce editoru.  
  
 Následující ukazuje, jak podporovat tento příkaz pro vaši službu jazyka.  
  
### <a name="to-support-outlining"></a>Pro podporu osnovy  
  
1. Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage> na váš objekt služby jazyka.  
  
2. Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> u aktuálního objektu relace sbalování přidávat nové oblasti osnovy.  
  
## <a name="robust-programming"></a>Robustní programování  
 Když uživatel vybere **sbalit do definic** na **Osnova** nabídky, volání IDE <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage.CollapseToDefinitions%2A> na službě jazyka.  
  
 Když tato metoda je volána, rozhraní IDE předá <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> ukazatel (ukazatel na textové vyrovnávací paměti) a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession> (ukazatel na aktuální relace sbalování).  
  
 Můžete volat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> metodu pro více oblastí osnovy tak, že zadáte v těchto oblastech `rgOutlnReg` parametr. `rgOutlnReg` Parametr je <xref:Microsoft.VisualStudio.TextManager.Interop.NewOutlineRegion> struktury. Tento proces vám umožňují určit různé vlastnosti skryté oblasti, jako je například, jestli je konkrétní oblasti rozbalená nebo sbalená.  
  
> [!NOTE]
> Buďte opatrní skrytí znaky nového řádku. Skrytý text by měl rozšířit od samého začátku první řádek poslední znak na posledním řádku oddíl, zanechá viditelný posledním znakem nového řádku.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Poskytování podpory skrytého textu ve službě starší verze jazyka](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)   
 [Postupy: Poskytování rozšířené podpory osnovy ve službě starší verze jazyka](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)
