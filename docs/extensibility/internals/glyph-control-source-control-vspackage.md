---
title: Správa piktogramů (řízení zdrojového balíčku VSPackage) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- glyphs, source control packages
- source control packages, glyphs
ms.assetid: b9413b08-b3c3-4fc3-a6e0-3dc0db3652d7
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d30682a85551aab062824688b635260c30df63f9
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66321351"
---
# <a name="glyph-control-source-control-vspackage"></a>Správa piktogramů (řízení zdrojového balíčku VSPackage)
Součástí Tato těsná integrace do balíčků VSPackage správy zdrojového kódu k dispozici je možnost zobrazit své vlastní Glyph označuje stav položky pod správou zdrojových kódů.

## <a name="levels-of-glyph-control"></a>Úroveň kontroly nad glyfů
 Glyf stavu je ikona, která označuje aktuální stav položky při zobrazení, například v **Průzkumníka řešení** nebo v **zobrazení tříd**. Balíčku VSPackage správy zdrojového kódu můžete využít dvě úrovně ovládacího prvku glyfů. Volba glyfů pro předdefinovanou sadu glyfy poskytované může být omezena [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí, nebo můžete definovat vlastní sadu glyfy, který se má zobrazit.

### <a name="default-set-of-glyphs"></a>Výchozí sadu piktogramy
 K určení, které jsou spojeny s položkou v glyfy stavu **Průzkumníka řešení**, projekt požadavků piktogram stav zdroje pomocí ovládacího prvku <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.GetSccGlyph%2A>. VSPackage správy zdrojového kódu rozhodnout zachovat volba glyfy omezena na předdefinované glyfy poskytované rozhraní IDE. V takovém případě předá sady VSPackage zpět celou řadu hodnot, které reprezentují piktogram výčty, které jsou definovány v *vsshell.idl*. Další informace naleznete v tématu <xref:Microsoft.VisualStudio.Shell.Interop.VsStateIcon>. Toto je předdefinovanou sadu glyfy nastavit integrovaným vývojovým prostředím, jako visací zámek pro piktogram vrácené se změnami a zaškrtávací políčko pro piktogram rezervovat.

### <a name="custom-set-of-glyphs"></a>Vlastní sada piktogramy
 Balíčku VSPackage správy zdrojového kódu můžete použít vlastní glyfy jedinečný vzhled a chování při instalaci. Při aktivním nový ovládací prvek zdroje balíčku VSPackage by mělo být možné začít používat i v případě, že předchozí zdrojových kódů VSPackage je načtena stále svou vlastní glyfy ale neaktivní. V tomto režimu správy zdrojového kódu VSPackage stále můžete použít existující ikony pro zachování konzistentní s podívat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Pokud zvolí.

 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager> Služba podporuje rozhraní, <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>, který může volitelně implementovat sady VSPackage a které budou vyzváni k zadání integrovaným vývojovým prostředím. Pokud rozhraní IDE odešle požadavek, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] se pak pokusí získat toto rozhraní z aktuálně zaregistrovaných zdrojového balíčku VSPackage. Pokud rozhraní existuje v registrovaných VSPackage, rozhraní IDE pro vlastní glyfy neproběhne; v opačném případě [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE používá jeho výchozí sadu glyphs.

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs.GetCustomGlyphList%2A> Používá metoda [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] získat seznam imagí, které zobrazuje různé správy zdrojových kódů stavy. Ovládací prvek zdroje balíčku VSPackage vrátí popisovač pro seznam obrázků pro své vlastní glyfy integrovaného vývojového prostředí. Rozhraní IDE vytvoří kopii tohoto seznamu obrázků v tomto okamžiku a použije ho později zvolit glyfů pro zobrazení. Pokud nové rozhraní není podporovaná nebo `IVsSccGlyphs::GetCustomGlyphList` vrátí metoda `E_NOTIMPL`, pak integrované vývojové prostředí získá jeho glyfy ze seznamu výchozích glyfů poskytnutých [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="see-also"></a>Viz také:
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>
- <xref:Microsoft.VisualStudio.Shell.Interop.VsStateIcon>
- <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>