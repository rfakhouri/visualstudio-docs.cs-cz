---
title: Struktura VSPackage (Zdroj ovládacího prvku VSPackage) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, structure
- source control packages, VSPackage overview
ms.assetid: 92722be7-b397-48c3-a7a7-0b931a341961
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 13b811b504259bf10440419b3cb4029a4c239c5e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="vspackage-structure-source-control-vspackage"></a>Struktura VSPackage (Zdroj ovládacího prvku VSPackage)
Sada zdroj ovládacího prvku balíček SDK poskytuje pokyny pro vytváření VSPackage, který povolí zdroj ovládacího prvku implementátor integrovat své funkce správy zdrojového s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí. VSPackage je komponenty COM, která je obvykle načtena na vyžádání pomocí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE) podle služby, které mají být inzerovány balíček v jeho položky registru. Každý VSPackage musí implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>. VSPackage obvykle využívá službách nabízených [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE a proffers některé služby.  
  
 VSPackage deklaruje jeho položek nabídky a vytvoří výchozí položku stav přes .vsct soubor. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE zobrazí položky nabídky v tomto stavu, dokud VSPackage je načtena. Následně VSPackage implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda je volána k povolení nebo zakázání položky nabídky.  
  
## <a name="source-control-package-characteristics"></a>Vlastnosti balíčku zdroj ovládacího prvku  
 Správa zdrojového kódu VSPackage je úzce integrována do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Sémantika VSPackage patří:  
  
-   Rozhraní k implementaci titulu VSPackage ( `IVsPackage` rozhraní)  
  
-   Implementace příkaz uživatelského rozhraní (.vsct souborů a provádění <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní)  
  
-   Registrace VSPackage s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Správa zdrojového kódu VSPackage musí komunikovat pomocí těchto dalších [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] entity:  
  
-   Projekty  
  
-   Editory  
  
-   Řešení  
  
-   Windows  
  
-   Spuštěné tabulce dokumentu  
  
### <a name="visual-studio-environment-services-that-may-be-consumed"></a>Služby prostředí sady Visual Studio, které mohou být využívány.  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>  
  
 SVsRegisterScciProvider služby  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>  
  
### <a name="vsip-interfaces-implemented-and-called"></a>VSIP rozhraní implementované a s názvem  
 Zdroj balíčku ovládací prvek je VSPackage, a proto může spolupracovat přímo s další VSPackages, která jsou zaregistrovaná ve službě [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Chcete-li poskytovat úplného spektra funkce správy zdrojového, Správa zdrojového kódu VSPackage můžete řešit rozhraní poskytované projekty nebo prostředí.  
  
 Všechny projekty v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] musí implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3> k rozpoznat jako projekt v rámci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. Však není toto rozhraní specializuje dost pro řízení zdrojů. Implementujte řízení projektů, které se měl pod zdrojem <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>. Toto rozhraní je používán zdrojového kódu VSPackage k dotazování na projekt pro její obsah a k tomu glyfů a informace o vazbě (informace potřebné k navázání připojení mezi umístění serveru a na místo na disku z projektu, který je v části Správa zdrojového kódu).  
  
 Správa zdrojového kódu VSPackage implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>, která zase umožňuje projekty tak, aby se zaregistrovat pro správy zdrojového kódu a načíst jejich stav glyfů.  
  
 Úplný seznam rozhraní, která se správa zdrojového kódu VSPackage musíte zvážit, najdete v části [souvisejících služeb a rozhraní](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md).  
  
## <a name="see-also"></a>Viz také  
 [Prvky návrhu](../../extensibility/internals/source-control-vspackage-design-elements.md)   
 [Související služby a rozhraní](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)