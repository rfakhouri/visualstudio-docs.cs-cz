---
title: "Přehled nástroje jazyka domény | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language
ms.assetid: 50d93ea2-8c88-4522-853b-40ab194953db
caps.latest.revision: "54"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 20d4222f96958a730c563ff9bc84b2b5d0b08538
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="overview-of-domain-specific-language-tools"></a>Přehled Jazykových nástrojů specifických pro doménu
Domény jazykové nástroje specifické (DSL Tools), které jsou hostované v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], umožňují návrh jazyka domény a pak generovat vše, co uživatelé musí mít k vytváření modelů, které jsou založeny na jazyce.  
  
 Tyto nástroje jsou součástí nástrojů DSL:  
  
-   Průvodce projektu, který používá jiné řešení šablony můžete začít vyvíjet jazyka specifické pro doménu.  
  
-   Grafický návrhář pro vytváření a úpravy vaší definice jazyka domény.  
  
-   Modul ověřování, který zajišťuje, že je ve správném formátu definici jazyka domény a zobrazí chyby a upozornění, pokud dochází k problémům.  
  
-   Generátor kódu, který přebírá definici jazyka domény jako vstup a vytvoří zdrojový kód jako výstup.  
  
## <a name="the-dsl-tools-solution"></a>Řešení nástroje DSL  
 Průvodce specifické pro doménu Návrhář poskytuje následující řešení šablony:  
  
-   Tok úkolů  
  
-   Diagramy tříd  
  
-   Minimální jazyk  
  
-   Součást modely  
  
-   Minimální WPF  
  
-   Minimální Windows.Forms  
  
-   Knihovna DSL  
  
 Další informace najdete v tématu [výběr šablony řešení jazyk specifické pro doménu](../modeling/choosing-a-domain-specific-language-solution-template.md).  
  
 Průvodce vytvoří [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení, která má následující projekty:  
  
-   DSL  
  
     Projekt Dsl definuje jazyka domény a jeho nástroje pro úpravy a zpracování.  
  
-   **DslPackage**  
  
     Projekt DslPackage Určuje, jak integrovat nástroje jazyk [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="the-dsl-tools-graphical-interface"></a>Grafické rozhraní nástroje DSL  
 Grafické rozhraní nástroje DSL můžete přidat elementů a vztahů pro váš jazyk specifické pro doménu. Po přidání elementy, můžete definovat jejich vzhled mapování je do tvarů, přizpůsobení barev a přidáním dekorátory. Elementy můžete také přidat do sady nástrojů.  
  
## <a name="validation-in-dsl-tools"></a>Ověření v nástrojích DSL  
 DSL poskytuje jednu úroveň ověření, abyste měli jistotu, že model domény splňuje základní požadavky pro generování kódu. Obvykle při vytváření jazyka specifické pro doménu, měli byste přidat vlastní ověření, který má express vaše obchodní logiku pravidla. Další informace o vlastního ověřování najdete v tématu [ověření v jazyce specifické pro doménu](../modeling/validation-in-a-domain-specific-language.md).  
  
 Doporučujeme, abyste ověřili jazyka specifické pro doménu často při navrhování. Pokud váš jazyk specifické pro doménu došlo k chybám ověřování, nelze generovat zdrojového kódu. Generování zdrojového kódu z šablon proces se provádí kliknutím **transformaci všech šablon** na panelu nástrojů Průzkumníka řešení. Vždy, když upravíte definici jazyka, ujistěte se také k **transformaci všech šablon**. Další informace najdete v tématu [postupy: vytvoření řešení jazyk specifické pro doménu](../modeling/how-to-create-a-domain-specific-language-solution.md).  
  
## <a name="customization-of-dsl-tools"></a>Přizpůsobení nástroje DSL  
 Můžete zadat další kód pro upřesnění nastavení modelu a definování omezení přes svůj jazyk. V případě potřeby můžete provést změnou textové šablony významné změny.  
  
## <a name="distributing-your-dsl-solution"></a>Distribuce řešení DSL  
 Nástroje pro DSL generuje balíček, který je hostován v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Balíček zobrazí sady nástrojů, DSL explorer a další prvky uživatelského rozhraní, které umožní uživatelům vytvářet modely pomocí jazyka specifické pro doménu.  
  
 Při sestavení a spuštění řešení DSL nástroje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], druhé instance [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ukazuje, jak vypadá jazyka specifické pro doménu pro uživatele jazyka. Po ověření, že všechno funguje správně, můžete distribuovat `.vsix` soubor, který najdete ve složce sestavení projektu DslPackage. Tento soubor lze použít k instalaci DSL jako [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření na jiných počítačích.  Další informace najdete v tématu [nasazení řešení jazyk specifické pro doménu](../modeling/deploying-domain-specific-language-solutions.md).  
  
## <a name="see-also"></a>Viz také  
 [Experimentální instanci](../extensibility/the-experimental-instance.md)   
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)