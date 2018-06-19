---
title: Související služby a rozhraní (Zdroj ovládacího prvku VSPackage) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control packages, interfaces
- interfaces, source control packages
ms.assetid: 3e96e838-5675-46bb-99cf-40d420086038
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1f9e8e90fdda61524a9af107df452bc2b13cd90c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31135349"
---
# <a name="related-services-and-interfaces-source-control-vspackage"></a>Rozhraní (Zdroj ovládacího prvku VSPackage) a související služby
Tato část obsahuje všechny zdrojové řízení VSPackage související rozhraní [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]. Správa zdrojového kódu VSPackage implementuje některé z těchto rozhraní a jiné používá k provádění úkolů správy zdrojového.  
  
## <a name="interfaces-implemented-by-and-for-source-control-vspackages"></a>Rozhraní implementované a pro VSPackages zdroj ovládacího prvku  
 Následující rozhraní jsou popsané v [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], a Správa zdrojového kódu VSPackage implementuje jen některé z nich, v závislosti na jeho sady požadované funkce. Některé rozhraní jsou označeny jako požadovaný a musí být implementované VSPackage každých zdrojového kódu.  
  
 Pro tyto rozhraní, které balíček neimplementuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] poskytuje výchozí implementaci. Všimněte si, že výchozí implementace je navržen pro případ, pokud žádné VSPackage je zaregistrován a řídí žádný projekt. Správně vytvořené zdrojového kódu VSPackage implementuje rozhraní všechny potřebné místo ponechat výchozí implementaci těchto rozhraní.  
  
 Správa zdrojového kódu VSPackage musí implementovat privátní služby, který zapouzdřuje některé nebo všechny z následujících rozhraní.  
  
 Rozhraní jsou:  
  
-   Požadováno: Příslušná entita (Správa zdrojového kódu VSPackage zdroj ovládacího prvku se zakázaným inzerováním projektu) musí implementovat rozhraní.  
  
-   Doporučená: Entita má toto rozhraní implementovat; funkce správy zdrojového, jinak hodnota může být omezený.  
  
-   Volitelné: entita může toto rozhraní implementovat zajistit bohatší sada funkcí.  
  
|Rozhraní|Účel|Implementované|Implementovat?|  
|---------------|-------------|--------------------|----------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|Editory volání toto rozhraní před změnou nebo ukládání souboru. Správa zdrojového kódu VSPackage můžete rezervovat soubor nebo odepřít operaci Pokud rezervaci selže.|Správa zdrojového kódu VSPackage|Doporučeno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|Toto rozhraní poskytuje funkce správy základní zdrojového pro projekty, jako je registrace a zrušení registrace projekty se správa zdrojového kódu a zajištění podpory pro základní zdroj ovládacího prvku glyfů.|Správa zdrojového kódu VSPackage|Požadováno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|Toto rozhraní se získávají z <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> pomocí <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> funkce, nebo jednoduše přetypování implementace objektu `IVsHierarchy` k `IVsSccProject2`. Používá se pro získávání souborů ve správě zdrojového kódu v projektu nebo k informování projektu aktuální stav zdroje ovládací prvek nebo umístění.|Projekt|Požadováno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>|Modul integrace používá k nastavení aktuální aktivní VSPackage toto rozhraní.|Správa zdrojového kódu VSPackage|Požadováno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>|Toto rozhraní je založená na modelu předplatného. Všechny VSPackage mohou signalizovat, že chce přijímat události dokumentu a poradí s prostředí na události, které se chystáte dojít. Je implementována a zpracovává [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], který pak předá události implementace `IVsTrackProjectDocumentsEvents2` k VSPackage.|Zdroj ovládacího prvku se zakázaným inzerováním|Požadováno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments3>|Toto rozhraní poskytuje dávkové zpracování, operace synchronizované čtení a zápisu a rozšířené `OnQueryAddFiles` metoda.|Zdroj ovládacího prvku se zakázaným inzerováním|Požadováno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>|**Průzkumník řešení** a projekty volání toto rozhraní, když jsou přidávány nové soubory k projektům, nebo když soubory a složky, přejmenován nebo odstraněn z projektů. Správa zdrojového kódu VSPackage může rezervovat soubor projektu nebo operaci zrušte.|Správa zdrojového kódu VSPackage|Doporučeno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents3>|**Průzkumník řešení** a projekty volání toto rozhraní v reakci na volání do metody IVstrackProjectDocuments3 rozhraní. Správa zdrojového kódu VSPackage můžete sledovat dávkové operace, které jsou synchronizované operace čtení/zápisu a pracovat s více pokročilé `OnQueryAddFiles` metoda.|Správa zdrojového kódu VSPackage|Doporučeno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccEnlistmentPathTranslation>|Toto rozhraní poskytuje podporu správy zařazení pro webové projekty.|Správa zdrojového kódu VSPackage|Doporučeno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManagerTooltip>|Toto rozhraní se používá k načtení popisy tlačítek pro řízenou zdrojové soubory v projektech.|Správa zdrojového kódu VSPackage|Nepovinné|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccOpenFromSourceControl>|Toto rozhraní poskytuje podporu rozšíření oboru názvů.|Správa zdrojového kódu VSPackage|Nepovinné|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccControlNewSolution>|VSPackage používá toto rozhraní pro integraci rozšíření oboru názvů do **nový**, **otevřete**, nebo **Uložit** dialogová okna. V důsledku toho projekty lze automaticky přidán do správy zdrojového kódu na vytváření, nebo přidat k řízení zdrojů při uložení operace je v platnosti.|Správa zdrojového kódu VSPackage|Nepovinné|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>|VSPackage používá toto rozhraní se definovat další glyfů zdroj ovládacího prvku glyfů pro uzly ve **Průzkumníku řešení**.|Správa zdrojového kódu VSPackage|Nepovinné|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccAddWebProjectFromSourceControl>|**Přidat** dialogové okno pro webové projekty používá toto rozhraní. Poskytuje metody pro procházení pro řízení zdrojového umístění a pro otevření webového projektu dříve přidali v úložišti správy zdrojů v tomto umístění.|Správa zdrojového kódu VSPackage|Doporučeno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromScc>|Toto rozhraní poskytuje podporu pro načítání asynchronní (pozadí) projekty od správy zdrojového kódu.|Správa zdrojového kódu VSPackage|Nepovinné|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromSccProjectEvents>|Toto rozhraní umožňuje projektů se mají sledovat průběh asynchronní načítání iniciovaná <xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromScc>.|Projekt|Nepovinné|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccToolsOptions>|Toto rozhraní umožňuje IDE k dotazování VSPackage active zdrojového kódu. Prostředí IDE dotazuje hodnotu nastavení správy zdrojů, které mají význam i v případě, že žádná aktivní zdrojová ovládací prvek neexistuje VSPackage registrována. Toto rozhraní je implementováno a zpracovává [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].|Zdroj ovládacího prvku se zakázaným inzerováním|Požadováno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider>|Toto rozhraní se používá v registraci VSPackage zdrojového kódu.|Zdroj ovládacího prvku se zakázaným inzerováním|Požadováno|  
|<xref:EnvDTE.SourceControl>|Toto rozhraní se používá v automatizace. Jako takový zpřístupní jenom funkce, které může být provedena bez zobrazení uživatelského rozhraní.|Správa zdrojového kódu VSPackage|Nepovinné|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>|Toto rozhraní se používá pro uložení zdroj nastavení ovládacího prvku v souboru řešení (.sln). Nastavení zahrnuje řízení umístění zdroje a příznaky stavu ovládacích prvků zdroje.|Správa zdrojového kódu VSPackage|Doporučeno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>|Toto rozhraní se používá pro uložení nastavení správy zdrojů v řešení možnosti (.suo) souboru. To může zahrnovat zdroj specifický pro uživatele určit nastavení pro umístění zařazení aktuálního uživatele.|Správa zdrojového kódu VSPackage|Doporučeno|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>|Toto rozhraní se používá k monitorování událostí, abyste mohli provádět operace, jako je kontrola v souborech projektu před zavřením řešení, nebo při otevření projektu získávání nových souborů od správy zdrojového kódu.|Správa zdrojového kódu VSPackage|Doporučeno|  
  
## <a name="see-also"></a>Viz také  
 [Prvky návrhu](../../extensibility/internals/source-control-vspackage-design-elements.md)