---
title: "Přehled nástrojů Visual Studio Tools for Unity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4231bb9-45c4-4c77-ac3c-d05033b26393
caps.latest.revision: "4"
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload: unity
ms.openlocfilehash: d7d692ba1ee1bf2eb0fda5430b2576edc9646ebf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="overview-of-visual-studio-tools-for-unity"></a>Přehled Visual Studio Tools for Unity
V této části se dozvíte více o funkcích nástroje Visual Studio Tools pro Unity nabízí, a jak je můžete využít k efektivnější s Unity.  

 S nástroji Visual Studio Tools for Unity (*VSTU*), můžete použít Visual Studio psaní herní a editor skriptů v jazyce C# a pak použijte jeho výkonný ladicí program k vyhledání a opravte chyby. Nejnovější verze VSTU zahrnuje pro Unity na ShaderLab shaderu jazyka, lepší vizualizace ladicího programu a generování kódu vylepšené pro Průvodce MonoBehavior zvýrazňování syntaxe. VSTU přináší také soubory projektu Unity, zprávy konzoly a možnost spuštění vaše hra do sady Visual Studio, takže může trávit méně času přepnutí do a z editoru Unity při psaní kódu.  

 Pokračujte ve čtení Další informace o těchto funkcích.  

## <a name="integration-with-unity"></a>Integrace s Unity  
 Visual Studio Tools for Unity nebude vůni produktivitu, pokud jste museli přepínat mezi Unity editor a Visual Studio vždy. To je důvod, proč Visual Studio Tools for Unity usnadňuje zachovat věnovat práci, aniž byste museli opustit Visual Studio.  

-   **Unity Project Exploreru** zobrazí celý projekt Unity v sadě Visual Studio pomocí stejné hierarchie zobrazí v editoru Unity.  

-   Integrace konzoly Unity zobrazí výstup z konzoly Unity právo uvnitř okno chyb v sadě Visual Studio.  

-   Spusťte ladění vaše hra ze sady Visual Studio - není nutné přepnout zpět na Unity, stačí stisknout klávesu F5.  

## <a name="superior-debugging"></a>Pseudoelement ladění  
 Připojení výkonné ladicího programu sady Visual Studio pro vaše hra Unity k ladění skriptů jazyka C# a knihovny DLL, bez ohledu na to, zda je spuštěna samostatná nebo v editoru Unity. Můžete použít všechny funkce ladění, které očekáváte ze sady Visual Studio.  

-   Zarážky, včetně podmíněné zarážky.  

-   Vyhodnoťte složité výrazy v okně sledovat.  

-   Zkontrolujte a změňte hodnotu proměnné a argumenty.  

-   Přejděte do struktury komplexní objekty a data.  

 Vaše hra Unity můžete ladit i při běhu na jiném počítači v síti.  

## <a name="productivity"></a>Produktivita  
 Kromě zavedených produktivity Visual Studio pro psaní a refaktoring kódu v jazyce C# a Visual Studio Tools for Unity poskytuje navíc produktivitu funkce pro vývojáře, Unity.  

-   Pro jazyk ShaderLab Unity zvýrazňování syntaxe umožňuje přímé chyb ve vašem shadery dřív, než narostou chyby. Stačí otevřete ShaderLab soubory v sadě Visual Studio.  

-   Průvodce MonoBehavior umožňuje procházet seznam chování Unity a vytvoří často používaný kód pro chování, které nemusí být obeznámeni s. Stiskněte kombinaci kláves CTRL + SHIFT + M.  

-   Jakmile se seznámíte s Unity chování, které používají většinu, umístí je Průvodce rychlé MonoBehavior přímo na dosah ruky. Stisknutím kombinace kláves CTRL + ALT + Q.  

-   Přístup k dokumentaci Unity ze sady Visual Studio. Zvýrazněte právě volání rozhraní API, které chcete další informace o, a stiskněte CTRL + ALT + M, CTRL + H.  

-   Všechny tyto funkce a další činnosti pomocí klávesové zkratky přístup.  

## <a name="visual-studio-tools-for-unity-api"></a>Nástroje sady Visual Studio pro rozhraní API Unity  
 Přizpůsobit a rozšířit chování Visual Studio Tools for Unity pomocí zadaného rozhraní API.  

-   Visual Studio Tools for Unity zaregistruje zpětné volání protokolu, takže se dá Streamovat konzole Unity k sadě Visual Studio. Pokud máte editor skriptů, které protokolování informací, můžete je zařadit do stejné zpětného volání k odesílání zpráv pro Visual Studio. Další informace podívejte se na příklad zpětné volání protokolu.  

-   Jak Visual Studio Tools for Unity generuje soubory projektu pomocí zpětného volání styl Unity ProjectFileGeneration, můžete změnit. Další informace podívejte se na příklad generování souboru projektu.  

## <a name="see-also"></a>Viz také  
 [Domovská stránka Unity](http://unity3d.com)
