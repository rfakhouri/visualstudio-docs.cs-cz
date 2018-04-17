---
title: Řízení glyfy (Zdroj ovládacího prvku VSPackage) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- glyphs, source control packages
- source control packages, glyphs
ms.assetid: b9413b08-b3c3-4fc3-a6e0-3dc0db3652d7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c3787b0afad7f89743950a922d5b19c2d204bdd9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="glyph-control-source-control-vspackage"></a>Glyfy řízení (řízení VSPackage zdroje)
Součást těsná integrace, které jsou k dispozici pro ovládací prvek VSPackages zdroje je možnost zobrazit vlastní glyfů udávajících stav položek v části Správa zdrojového kódu.  
  
## <a name="levels-of-glyph-control"></a>Úroveň kontroly nad glyfy  
 Stav glyf je ikonu, která indikuje aktuální stav položky při zobrazení, například v **Průzkumníku řešení** nebo v **zobrazení tříd**. Správa zdrojového kódu VSPackage mohou vykonávat dvě úrovně řízení glyfů. Ho můžete omezit možnost glyfů předdefinovanou sadu glyfů poskytované [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE, nebo můžete definovat vlastní sadu glyfů, který se má zobrazit.  
  
### <a name="default-set-of-glyphs"></a>Výchozí sadu glyfů  
 K určení stavu glyfů, které jsou přidruženy položku v **Průzkumníku řešení**, projektu požadavky glyfy stavu pomocí ovládacího prvku zdroje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.GetSccGlyph%2A>. Správa zdrojového kódu VSPackage rozhodnout zachovat výběr glyfů omezena na předdefinované glyfů poskytované rozhraní IDE. V takovém případě VSPackage předá zpět pole hodnot představující výčty glyfy, které jsou definovány v vsshell.idl. Další informace najdete v tématu <xref:Microsoft.VisualStudio.Shell.Interop.VsStateIcon> . Toto je předdefinovanou sadu glyfů nastavit pomocí rozhraní IDE, jako je například visací zámek pro glyfy "Zaškrtnutí v" a zaškrtnutí jako glyfy "Rezervováno".  
  
### <a name="custom-set-of-glyphs"></a>Vlastní sada glyfů  
 Správa zdrojového kódu VSPackage můžete použít vlastní glyfů pro jedinečný "vzhled a chování", při instalaci. Při aktivním nové zdrojového kódu VSPackage by mělo být možné začít používat i v případě, že předchozí zdroj řízení VSPackage je načtena stále vlastní glyfů ale neaktivní. V tomto režimu se správa zdrojového kódu VSPackage stále můžete použít existující ikony pro zachování konzistentní se podívejte [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Pokud se vybere.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager> Služba podporuje rozhraní, <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>, která VSPackage můžete volitelně implementovat a které se dotaz pro zařízení IDE. Když prostředí IDE odešle žádost, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] naopak se pokusí získat toto rozhraní z ovládacího prvku aktuálně registrovaný zdroj VSPackage. Pokud v registrovaných VSPackage existuje rozhraní, rozhraní IDE pro vlastní glyfů neproběhne; jinak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE používá jeho výchozí sadu glyfů.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs.GetCustomGlyphList%2A> Metoda používá [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] získat seznam obrázky znázorňující různé zdrojového kódu stavy. Správa zdrojového kódu VSPackage vrátí k prostředí IDE popisovač pro seznam obrázků pro své vlastní glyfů. Prostředí IDE v tomto okamžiku vytvoří kopii seznamu obrázků a používá je později zvolit glyfů pro zobrazení. Pokud nové rozhraní není podporován nebo `IVsSccGlyphs::GetCustomGlyphList` metoda vrátí E_NOTIMPL, pak IDE získá jeho glyfů ze seznamu výchozích glyfů poskytl [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>   
 <xref:Microsoft.VisualStudio.Shell.Interop.VsStateIcon>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>