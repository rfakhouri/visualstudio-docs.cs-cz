---
title: "Scénáře instalace VSPackage | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, deployment considerations
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 452a5cfee55bd314bb062d2d1ddd8496593190fa
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="vspackage-setup-scenarios"></a>Instalační program VSPackage scénáře

Je důležité při návrhu instalačním programem vaší VSPackage flexibilitu. Například možná budete muset v budoucnu vydání opravy zabezpečení, nebo můžete změnit obchodní strategii, který vyžaduje podporu správy verzí důkladné vedle sebe.

V [podpora více verzí aplikace Visual Studio](../../extensibility/supporting-multiple-versions-of-visual-studio.md), další informace o výhody a problémy podporu instalace vedle sebe [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] s sdílené nebo vedle sebe instalací vaší VSPackage. Stručně řečeno, vedle sebe VSPackages získáte nejvíce flexibilitu na podporu nových funkcí technologie [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

Scénářích popsaných v tomto tématu nejsou vaší jedinou možností, ale jsou uvedeny jako navrhované osvědčené postupy.

## <a name="components-privacy-and-sharing"></a>Součásti, ochrany osobních údajů a sdílení

### <a name="make-your-components-independent"></a>Aby vaše komponenty pro nezávislý

Po identifikaci a naplnit komponentu, přiřadit `GUID`a nasadíte komponentu, nelze změnit jeho složení. Pokud změníte složení komponenty, výsledná součásti musí být nové komponenty s novou `GUID`. Zadána tyto skutečnosti nejvyšší flexibilitu Správa verzí je zaměřena tak, že jednotlivé jednotky nezávislé, běžných součástí. Další informace o pravidlech, kterými se řídí součásti najdete v tématu [Změna kódu součást](http://msdn.microsoft.com/library/aa367849\(VS.85\).aspx) a [co se stane, když je součást pravidla rozděluje?](http://msdn.microsoft.com/library/aa372795\(VS.85\).aspx).

### <a name="do-not-mix-shared-and-private-resources-in-a-component"></a>Nemíchat zdroje sdílené a privátní v komponentě

Počítání odkazů probíhá na úrovni součásti. V důsledku toho kombinování sdílené a privátní prostředky v jedna součást znemožňuje aktualizovat privátní prostředky, například spustitelný soubor, bez také přepsal sdílených prostředků. V tomto scénáři vytvoří zpětné kompatibility problémy a brání vytváření schopností vedle sebe.

Například hodnoty registru používá k registraci vaší VSPackage s [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] by měl být udržovány v komponentě odděleně od jednoho používá k registraci vaší VSPackage pomocí sady Visual Studio. Sdílené soubory nebo hodnoty registru, přejděte v ještě jiné součásti.

## <a name="scenario-1-shared-vspackage"></a>Scénář 1: Sdílené VSPackage

V tomto scénáři sdílené VSPackage (jednoho binárního souboru, který podporuje více verzí sady Visual Studio je dodáván v balíčku Instalační služby systému Windows. Registrace s jednotlivými verzemi sady Visual Studio je řízena uživatelem volitelných funkcí. Je také znamená, že když přiřazuje samostatným funkce, jednotlivé komponenty můžete vybrat jednotlivě pro instalace nebo odinstalace, zajišťuje uživatelům vyšší kontrolu nad integraci VSPackage do různých verzích [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. (Viz [funkce Instalační služby systému Windows](http://msdn.microsoft.com/library/aa372840\(VS.85\).aspx) Další informace o používání funkcí v balíčky Instalační služby systému Windows.)

![Instalační program VSPackage sdílené VS](../../extensibility/internals/media/vs_sharedpackage.gif "VS_SharedPackage")

Jak je znázorněno na obrázku, sdílené komponenty jsou součástí Feat_Common funkci, která je vždy nainstalován. Tím, že funkce Feat_VS2002 a Feat_VS2003 viditelné, mohli uživatelé vybrat během instalace, do které verze sady Visual Studio chtějí VSPackage integrovat. Uživatelé mohou také používat režim údržby Instalační služby systému Windows přidat nebo odebrat funkce, které v tomto případě přidá nebo odebere VSPackage registrační informace z různých verzí sady Visual Studio.

> [!NOTE]
> Sloupec zobrazení funkce nastavení na hodnotu 0 skryje ho. Hodnota sloupce nízké úrovně, například 1, zajišťuje, že bude vždy nainstalován. Další informace najdete v tématu [INSTALLLEVEL vlastnost](http://msdn.microsoft.com/library/aa369536\(VS.85\).aspx) a [funkce tabulky](http://msdn.microsoft.com/library/aa368585.aspx).

## <a name="scenario-2-shared-vspackage-update"></a>Scénář 2: Sdílené VSPackage aktualizace

V tomto scénáři je dodáván aktualizovanou verzi Instalační služby VSPackage ve scénáři 1. Z důvodu výkladu aktualizace přidává podporu pro sadu Visual Studio, ale může také být jednodušší opravy zabezpečení nebo oprava chyby aktualizace service pack. Pravidla Instalační služby systému Windows pro instalaci novější verze součástí vyžadovat, že nejsou překopírovat beze změny součásti již v systému. Systém s verze 1.0 již existuje v tomto případě přepíše aktualizované součásti Comp_MyVSPackage.dll a umožnit uživatelům vybrat novou funkci Feat_VS2005 se jeho součástí Comp_VS2005_Reg přidat.

> [!CAUTION]
> Vždy, když je VSPackage sdílen více verzí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], je nezbytné, aby následujících verzích VSPackage udržovat zpětnou kompatibilitu s předchozí verzí sady Visual Studio. Kde nelze udržovat zpětnou kompatibilitu, je nutné použít vedle sebe, privátní VSPackages. Další informace najdete v tématu [podpora více verzí aplikace Visual Studio](../../extensibility/supporting-multiple-versions-of-visual-studio.md).

![Instalační program aktualizace balíčku sdílené VS VS](../../extensibility/internals/media/vs_sharedpackageupdate.gif "VS_SharedPackageUpdate")

Tento scénář uvede novým instalačním programem VSPackage využití výhod podpory Instalační služby systému Windows pro menší upgrady. Uživatelé jednoduše nainstalovat verze 1.1 a upgradu verze 1.0. Však není nutné mít verze 1.0 v systému. Stejný instalační program nainstaluje verze 1.1 v systému bez verze 1.0. Výhody zajistit menší upgrady tímto způsobem je, že není potřeba projít práci při vývoji upgradu instalační program a instalační program produktu úplné. Jeden instalační program nemá obě úlohy. Opravy zabezpečení nebo service pack může místo využít výhody oprav Instalační služby systému Windows. Další informace najdete v tématu [oprav a upgrady](http://msdn.microsoft.com/library/aa370579\(VS.85\).aspx).

## <a name="scenario-3-side-by-side-vspackage"></a>Scénář 3: VSPackage vedle sebe

Tento scénář představuje dva instalační programy VSPackage – jeden pro každou verzi Visual Studio .NET 2003 a Visual Studio. Každý instalační program nainstaluje vedle sebe, nebo privátní, VSPackage (ten, který je specificky vytvořené a nainstalovaných pro konkrétní verzi sady Visual Studio). Každý VSPackage je ve své vlastní součásti. V důsledku toho každý jednotlivě zpracováním opravy nebo údržby uvolní. Protože VSPackage DLL je nyní specifické pro verzi, je bezpečné zahrnují informace o jeho registraci v komponentě stejné jako knihovnu DLL.

![Instalační program balíčku VS vedle sebe VS](../../extensibility/internals/media/vs_sbys_package.gif "VS_SbyS_Package")

Každý instalační služba systému také obsahuje kód, jež jsou sdílena mezi dvěma instalační programy. Pokud kód sdílený je nainstalován do společného umístění, instalace oba soubory .msi nainstaluje kód sdílený pouze jednou. Druhý instalační program právě zvýší počet odkazů na komponentu. Počet odkazů zaručuje, že pokud jeden z VSPackages odinstalována, kód sdílený budou zachovány pro jiné VSPackage. Pokud také odinstalaci druhý VSPackage sdíleného kódu se odeberou.

## <a name="scenario-4-side-by-side-vspackage-update"></a>Scénář 4: Vedle sebe VSPackage aktualizace

V tomto scénáři vaše VSPackage pro sadu Visual Studio vyskytla z ohrožení zabezpečení a budete muset vydání aktualizace. Jako scénář 2 můžete vytvořit nový soubor .msi, který aktualizuje existující instalaci zahrnovat opravy zabezpečení a také nasadit nové instalace s opravy zabezpečení již na místě.

V takovém případě VSPackage je spravovaný VSPackage nainstalované v globální mezipaměti sestavení (GAC). Když znovu vytvoříte tak, aby obsahovala opravy zabezpečení, je nutné změnit číslo revize část číslo verze sestavení. Informace o registraci pro nové číslo verze sestavení přepíše předchozí verzi, která způsobila [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] k načtení pevné sestavení.

![Instalační program aktualizace balíčku VS vedle sebe VS](../../extensibility/internals/media/vs_sbys_packageupdate.gif "VS_SbyS_PackageUpdate")

Další informace o nasazení souběžně sdílená sestavení najdete v tématu [zjednodušit nasazení a řešení DLL a tím zlepšují s rozhraním .NET Framework](http://msdn.microsoft.com/library/ms973843.aspx).

## <a name="see-also"></a>Viz také

[Instalační služba systému Windows](http://msdn.microsoft.com/library/cc185688\(VS.85\).aspx)  
[Podpora více verzí sady Visual Studio](../../extensibility/supporting-multiple-versions-of-visual-studio.md)