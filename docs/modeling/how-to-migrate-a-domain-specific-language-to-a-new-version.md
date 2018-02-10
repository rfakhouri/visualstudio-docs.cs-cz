---
title: "Postupy: migrace na novou verzi jazyka domény | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 7f6aa84a55e629f003a1d9b896a5c095dc2d19ac
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-migrate-a-domain-specific-language-to-a-new-version"></a>Postupy: Migrace jazyka specifického pro doménu na novou verzi
Můžete migrovat projekty, které definice a používání jazyka specifické pro doménu [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] z verze [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] který byl distribuován s [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)].  
  
 Nástroj pro migraci k dispozici jako součást [!INCLUDE[vssdk_current_long](../misc/includes/vssdk_current_long_md.md)]. Nástroj převede [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projekty a řešení, které používají nebo definovat DSL nástroje.  
  
 Je nutné spustit nástroj pro migraci explicitně: není spuštěna jako automaticky při otevření řešení v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Nástroj a dokumentu podrobné pokyny najdete v této cestě:  
  
 **%Program Files%\Microsoft Visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**  
  
## <a name="before-you-migrate-your-dsl-projects"></a>Před migrací DSL projekty  
 Nástroj pro migraci upraví [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] soubory projektu (**.csproj**) a soubory řešení (**.sln**).  
  
#### <a name="to-prepare-projects-for-migration"></a>Projekty přípravy na migraci.  
  
-   Zajistěte, aby **.csproj** a **.sln** lze zapisovat soubory. Pokud jsou v části Správa zdrojového kódu, ujistěte se, že je rezervovaný.  
  
-   Vytvořte kopii složky, které máte v úmyslu migrovat.  
  
## <a name="migrating-a-collection-of-projects"></a>Migrace kolekce projektů  
  
#### <a name="to-migrate-dsl-projects-and-solutions-to-visual-studio-2010"></a>K migraci DSL projekty a řešení Visual Studio 2010  
  
1.  Spusťte nástroj pro migraci DSL.  
  
    -   Můžete dvakrát klikněte na nástroj v Průzkumníku Windows (nebo v Průzkumníku souborů) nebo spusťte nástroj z příkazového řádku. Tento nástroj je v tomto umístění:  
  
         **%ProgramFiles%\Microsoft Visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**  
  
2.  Vyberte složku, která obsahuje řešení a projektů, které chcete převést.  
  
    -   Zadejte do pole v horní části nástroj cestu nebo klikněte na tlačítko **Procházet**.  
  
     Nástroj pro migraci zobrazí strom projektů, které definují nebo použít DSL, linky. Každý projekt, který používá zahrnuje stromu **Microsoft.VisualStudio.Modeling.Sdk** nebo **TextTemplating** sestavení.  
  
3.  Zkontrolujte stromu projekty a zrušte zaškrtnutí políčka projekty, které nechcete převést.  
  
    -   Vyberte projekt nebo řešení zobrazíte seznam změn, které bude nástroj.  
  
        > [!NOTE]
        >  Zaškrtávací políčka, které se zobrazují vedle názvy složek nemají žádný vliv. Je třeba rozbalit složky, které chcete zkontrolovat projekty a řešení.  
  
4.  Převod projektů.  
  
    1.  Klikněte na tlačítko **převést**.  
  
         Před převodu každý soubor projektu, kopie *projektu *** .csproj** je uloženo jako *projektu ***.vs2008.csproj**  
  
         Kopírování jednotlivých *řešení *** .sln** je uloženo jako *řešení ***.vs2008.sln**  
  
    2.  Prozkoumejte všechny neúspěšné převody, které jsou hlášeny.  
  
         Selhání oznamuje v okně text. Kromě toho stromovém zobrazení zobrazí červený příznak na každém uzlu, který se nepodařilo převést. Můžete kliknout na uzlu, chcete-li získat další informace o této chybě.  
  
5.  **Proveďte transformaci všech šablon** v řešení obsahující úspěšně převést projekty.  
  
    1.  Otevřete řešení.  
  
    2.  Klikněte **transformaci všech šablon** tlačítko v hlavičce Průzkumníku řešení.  
  
        > [!NOTE]
        >  Tento krok můžete provést zbytečné. Další informace najdete v tématu [jak automatizovat transformaci všech šablon](http://msdn.microsoft.com/b63cfe20-fe5e-47cc-9506-59b29bca768a).  
  
6.  Aktualizujte vlastní kódu v projektech převeden.  
  
    -   Pokus o sestavení projektů a zjistěte jeho selhání.  
  
    -   Testování vašeho návrháře.  
  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>Viz také  
 [Příspěvky blogu související](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)

