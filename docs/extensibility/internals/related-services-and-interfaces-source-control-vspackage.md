---
title: Související služby a rozhraní (řízení zdrojového balíčku VSPackage) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control packages, interfaces
- interfaces, source control packages
ms.assetid: 3e96e838-5675-46bb-99cf-40d420086038
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a9aa9dd59a568ae766a7cd0939c41a4bcd97f640
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337302"
---
# <a name="related-services-and-interfaces-source-control-vspackage"></a>Související služby a rozhraní (balíček VSPackage správy zdrojového kódu)
Tato část obsahuje seznam všech zdroj řídit VSPackage související rozhraní [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]. Ovládací prvek zdroje balíčku VSPackage implementuje některé z těchto rozhraní a ostatní používá k provádění úkolů správy zdrojového.

## <a name="interfaces-implemented-by-and-for-source-control-vspackages"></a>Rozhraní implementovaná a pro balíčky VSPackage správy zdrojového
 Následující rozhraní jsou popsány v [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], a správy zdrojového kódu VSPackage implementuje jen některé z nich v závislosti na sadou požadovaných funkcí. Některá rozhraní jsou označené jako povinné a musí být implementované každý ovládací prvek zdroje balíčku VSPackage.

 Pro tato rozhraní, které balíček neimplementuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] poskytuje výchozí implementaci. Všimněte si, že výchozí implementace je navržen pro případ, pokud je registrován žádný VSPackage možnosti jsou dané žádný projekt. Správně vytvořené zdrojového balíčku VSPackage implementuje všechna potřebná rozhraní spíše než v něm pro výchozí implementace těchto rozhraní.

 Balíčku VSPackage správy zdrojového kódu musí implementovat privátní služby, který zapouzdřuje některé nebo všechny z následujících rozhraní.

 Rozhraní jsou:

- Požadováno: Odpovídající entity (projektu správy zdrojového kódu VSPackage zdrojového ovládacího prvku se zakázaným inzerováním) musí implementovat rozhraní.

- Doporučené: Entita musí implementovat toto rozhraní; funkce správy zdrojového kódu v opačném případě může být omezená.

- Volitelné: entita může toto rozhraní implementují poskytnout bohatší sadu funkcí.

| Rozhraní | Účel | Implementováno | Implementovat? |
| - | - |--------------------------|-------------|
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> | Editory volat toto rozhraní před úpravou nebo uložení souboru. Modul správy zdrojových kódů VSPackage můžete rezervovat soubor nebo odepřít operaci, pokud rezervace nezdaří. | Balíčku VSPackage správy zdrojového kódu | Doporučené |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2> | Toto rozhraní poskytuje funkce správy základní zdrojového kódu pro projekty, jako je například registrace a zrušení registrace projekty se správou zdrojového kódu a poskytují podporu pro základní zdroj glyfy ovládacího prvku. | Balíčku VSPackage správy zdrojového kódu | Požadováno |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2> | Toto rozhraní se získávají z <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> pomocí <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> funkce, nebo přetypováním jednoduše implementace objektu `IVsHierarchy` k `IVsSccProject2`. Používá se, jak získat soubory pod správou zdrojových kódů v projektu nebo pro informování projektu se aktuální stav správy zdrojových kódů nebo umístění. | Project | Požadováno |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider> | Modul integrace používá k nastavení aktuální aktivní VSPackage toto rozhraní. | Balíčku VSPackage správy zdrojového kódu | Požadováno |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> | Toto rozhraní je založena na modelu předplatného. Žádné VSPackage mohou signalizovat, že chce přijímat události dokumentu a být prostředí informován o události, které se chystáte stát. Je implementována a zpracovány [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], který pak předá události implementace `IVsTrackProjectDocumentsEvents2` do sady VSPackage. | Zdrojový ovládací prvek se zakázaným inzerováním | Požadováno |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments3> | Toto rozhraní poskytuje dávkové zpracování, operace čtení a zápisu synchronizované a moderní `OnQueryAddFiles` metody. | Zdrojový ovládací prvek se zakázaným inzerováním | Požadováno |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2> | **Průzkumník řešení** a projekty volat toto rozhraní, když se do projektů přidají nové soubory, nebo když soubory a složky, přejmenován nebo odstraněn z projektů. Ovládací prvek zdroje balíčku VSPackage můžete rezervovat soubor projektu nebo zrušit operaci. | Balíčku VSPackage správy zdrojového kódu | Doporučené |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents3> | **Průzkumník řešení** a projekty volat toto rozhraní v reakci na volání metody IVstrackProjectDocuments3 rozhraní. Ovládací prvek zdroje balíčku VSPackage můžete sledovat dávkové operace synchronizovat operací čtení a zápis a pracovat s další rozšířené `OnQueryAddFiles` metody. | Balíčku VSPackage správy zdrojového kódu | Doporučené |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccEnlistmentPathTranslation> | Toto rozhraní poskytuje podporu správy zařazení pro webové projekty. | Balíčku VSPackage správy zdrojového kódu | Doporučené |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManagerTooltip> | Toto rozhraní se používá k načtení popisy tlačítek pro soubory spravovanými zdroji v projektech. | Balíčku VSPackage správy zdrojového kódu | volitelná, |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccOpenFromSourceControl> | Toto rozhraní poskytuje podporu rozšíření oboru názvů. | Balíčku VSPackage správy zdrojového kódu | volitelná, |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccControlNewSolution> | Sady VSPackage pomocí tohoto rozhraní integruje rozšíření oboru názvů do **nový**, **otevřít**, nebo **Uložit** dialogových oknech. V důsledku toho projekty lze automaticky přidány do správy zdrojového kódu při vytvoření, nebo přidat do správy zdrojových kódů při uložení operace je v platnosti. | Balíčku VSPackage správy zdrojového kódu | volitelná, |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs> | Sady VSPackage pomocí toto rozhraní definuje další glyfy jako zdrojový ovládací prvek glyfů pro uzly v **Průzkumníka řešení**. | Balíčku VSPackage správy zdrojového kódu | volitelná, |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccAddWebProjectFromSourceControl> | **Přidat** dialogové okno pro webové projekty používá toto rozhraní. Poskytuje metody pro procházení umístění správy zdrojových kódů a pro otevření webového projektu přidali dříve, do úložiště správy zdrojového kódu na tomto místě. | Balíčku VSPackage správy zdrojového kódu | Doporučené |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromScc> | Toto rozhraní poskytuje podporu pro asynchronní (pozadí) načítání projektů ze správy zdrojového kódu. | Balíčku VSPackage správy zdrojového kódu | volitelná, |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromSccProjectEvents> | Toto rozhraní podporuje projekty, které chcete sledovat průběh asynchronní načítání iniciovaných <xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromScc>. | Project | volitelná, |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccToolsOptions> | Toto rozhraní podporuje rozhraní IDE k dotazování aktivní zdrojového balíčku VSPackage. Hodnotu nastavení správy zdrojového kódu, které mají význam i v případě, že neexistuje žádná aktivní zdrojového balíčku VSPackage zaregistruje se dotazuje rozhraní IDE. Toto rozhraní je implementováno a zpracovány [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. | Zdrojový ovládací prvek se zakázaným inzerováním | Požadováno |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider> | Toto rozhraní se používá při registraci správy zdrojového kódu VSPackage. | Zdrojový ovládací prvek se zakázaným inzerováním | Požadováno |
| <xref:EnvDTE.SourceControl> | Toto rozhraní se používá ve službě automation. V důsledku toho zpřístupňuje pouze funkce, které může být provedena bez zobrazení uživatelského rozhraní. | Balíčku VSPackage správy zdrojového kódu | volitelná, |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> | Toto rozhraní se používá k uložení zdroj nastavení ovládacího prvku v souboru řešení (.sln). Nastavení zahrnují umístění správy zdrojových kódů a příznaky stavu ovládacího prvku zdroje. | Balíčku VSPackage správy zdrojového kódu | Doporučené |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts> | Toto rozhraní se používá k uložení nastavení správy zdrojových kódů v souboru řešení (.suo) možnosti. To může zahrnovat nastavení správy zdrojového specifické pro uživatele, jako je například umístění zařazení aktuálního uživatele. | Balíčku VSPackage správy zdrojového kódu | Doporučené |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3> | Toto rozhraní se používá k monitorování událostí, abyste mohli provádět operace, jako je například kontrola v souborech projektu před zavřením řešení nebo získávání nových souborů ze správy zdrojových kódů při otevření projektu. | Balíčku VSPackage správy zdrojového kódu | Doporučené |

## <a name="see-also"></a>Viz také
- [Prvky návrhu](../../extensibility/internals/source-control-vspackage-design-elements.md)