---
title: "Představení mezinárodních aplikací založené na rozhraní .NET Framework | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strings [Visual Studio], localizing
- Web applications [.NET Framework], globalization
- Windows Forms, globalization
- localization [Visual Studio], culture setting
- fallback resources
- culture, setting
- globalization [Visual Studio], culture setting
- resources [Visual Studio], localization
- localization [Visual Studio], .NET localization model
- Assembly Resource file template
- resources [Visual Studio], fallback system
- international applications [Visual Studio], about international applications
- globalization [Visual Studio], international applications
- ASP.NET, globalization
- resource files, fallback processes
- user interface, culture setting
ms.assetid: b0788993-e62d-4f68-8235-5f87b1d48525
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 9acc8f2e015b6ca2ad26881eeb1f53012d96e56d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="introduction-to-international-applications-based-on-the-net-framework"></a>Představení mezinárodních aplikací založených na prostředí .NET Framework
V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], k vytvoření aplikace připravených skládá ze dvou částí: globalizace, proces návrhu aplikace, které můžete přizpůsobit pro jiné kultury a lokalizace, proces překladu prostředky pro konkrétní jazykové verze. Obecné informace o navrhování aplikací pro mezinárodní cílovou skupinu najdete v tématu [osvědčené postupy pro vývoj aplikací připravených](http://msdn.microsoft.com/Library/f08169c7-aad8-4ec3-9a21-9ebd3b89986c).  
  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] – Model lokalizace se skládá z hlavní sestavení, který obsahuje kódu aplikace a nouzové prostředky – řetězce, obrázky a další objekty pro jazyk, ve kterém se aplikace původně vytvořen. Jednotlivé lokalizované aplikace bude mít satelitní sestavení nebo sestavení, které obsahují pouze lokalizované prostředky. Protože hlavní sestavení vždy obsahuje nouzové prostředky, pokud prostředek nebyl nalezen v sestavení lokalizovaná satelitní <xref:System.Resources.ResourceManager> se pokusí načíst hierarchické uspořádání, nakonec návratem zpět k prostředku v hlavní sestavení. Záložní systém prostředků je vysvětlené podrobněji na [hierarchická organizace zdrojů pro lokalizaci](../ide/hierarchical-organization-of-resources-for-localization.md).  
  
 Jeden prostředek lokalizace, měli byste zvážit použití je Glosář pro všechny Microsoft lokalizované produkty. Tento soubor CSV obsahuje více než 12 000 anglické podmínky plus překlady podmínkami až 59 různé jazyky. Je k dispozici ke stažení na glosáři [Microsoft terminologie překlady](http://go.microsoft.com/fwlink/?LinkId=128146) webové stránky.  
  
 Systém projektu pro Windows Forms aplikace můžete vygenerovat zdrojové soubory nouzové situaci a všechny potřeby další jazyková verze uživatelského rozhraní. Soubor prostředků záložní je integrovaná do hlavní sestavení a soubory prostředků specifické pro jazykovou verzi jsou pak součástí satelitní sestavení, jeden pro každou jazykovou verzi uživatelského rozhraní. Při sestavování projektu, soubory prostředků kompilovány z formátu Visual Studio XML (RESX) do zprostředkující binárního formátu (.resources), které se pak vloží do satelitní sestavení.  
  
 Systém projektu pro Windows Forms a webových formulářů umožňuje vytvářet soubory prostředků pomocí šablony souboru prostředku sestavení, přístup k prostředkům a sestavení projektu. Satelitní sestavení bude vytvořen společně s hlavní sestavení.  
  
 Když provede lokalizovanou aplikaci, její vzhled je určen podle dvě hodnoty jazykové verze. (A *jazykovou verzi* je sada uživatelské předvolby informace související s jazyk uživatele, prostředí a kulturního konvence.) Nastavení jazykové verze uživatelského rozhraní určuje prostředky, ke kterým budou načteny. Jazyková verze uživatelského rozhraní je nastaven jako `UICulture` v souborech Web.config a direktivy stránky a <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> v kódu Visual Basic a Visual C#. Nastavení jazykové verze Určuje formátování hodnot například data, čísla, měny a tak dále. Jazyková verze je nastaven jako `Culture` v souborech Web.config a direktivy stránky <xref:System.Globalization.CultureInfo.CurrentCulture%2A> v kódu Visual Basic a Visual C#.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Globalization>   
 <xref:System.Resources>   
 [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)   
 [Zabezpečení a lokalizovaná satelitní sestavení](../ide/security-and-localized-satellite-assemblies.md)